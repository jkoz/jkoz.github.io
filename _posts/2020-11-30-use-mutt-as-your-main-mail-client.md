---
layout: post
title: Use mutt as your main mail client
categories:
  - mutt, mbsync,gpg,jq,msmtp,fzf,surf,tmux
---

# Introduction

I know, another mutt guide!

A mail client is very important at digital workplace. As I start my day at work; first thing first, check your email. Sometimes I am really disappointed, waiting for outlook or thunderbird launching. I want something launching fast, vim-like tools, hackable, and following unix philosophy. Even though I am not in the technical field any more, I would like to share my mutt configuration.

This article aims to use different unix tools to configure plain old mutt as a modern mail client. Thus, we don't need to add extra dependencies or re-invent the wheel. The main goal is to support multiple account at a usable level.


So what are the goals that I need in a mail client ?

- Text-based mail client, so I can ssh to server and check my mail and take advantage of external tools like fzf, tmux, etc.
- Utilize tools which are already available on unix system like find, sed, curl..
- Dynamically find mailboxes, and subfolder management
- Support view html in browser
- Works with Oauth2
- Securely store your tokens
- Fast searching mails by subject, name across mailboxes with mu
- Easy view attachment

# Screenshot

Here is how it looks like

![Mutt client](/img/mutt/mutt-screenshoot.jpg)

# Tools and dependencies:

- cyrus-sasl-xoauth2
- mbsync 
- msmtp
- curl
- jq
- tmux
- fzf
- gpg

# Configurations

## Oauth2

I start with oauth2 since it is widely adopted in mail server

{% highlight shell %}

git clone https://github.com/moriyoshi/cyrus-sasl-xoauth2
cd ./cyrus-sasl-xoauth2 
./autogen.sh
./configure
make install

{% endhighlight %}

cyrus-sasl-xoauth2 provides a mechanism for authenticating with oauth2 server. Basicly, after building the code, it deploys libxoauth2.la to your
system ready for your mbsync load upon authenticating.

## Isync

Isync is just an IMAP sync tool, same as OfflineIMAP but written in C. There are two important things in mbsyncrc users need to pay attention.
Firstly, it is the last '/' in Path, without that slash, mbsync can't sync your inner mailboxes ([Gmail]/Drafts, etc.) after the first sync.
Besides, the empty line between each configuration block is important as well

[ AuthMechs "XOAUTH2" ] is available for using after install cyrus-sasl-xoauth2 library. XOAUTH2 mechs requires access_token returned by PassCmd

{% highlight shell %}

IMAPAccount gmail-phuoctaitp
Host imap.gmail.com
User phuoctaitp@gmail.com
PassCmd "gpg -dq ~/.gnupg/gmail-phuoctaitp.gpg | xargs -0 bash -c"
AuthMechs "XOAUTH2"
SSLType IMAPS

IMAPStore gmail-phuoctaitp-remote
Account gmail-phuoctaitp

MaildirStore gmail-phuoctaitp-local
SubFolders Verbatim
Path ~/Mail/phuoctaitp@gmail.com/
Inbox ~/Mail/phuoctaitp@gmail.com/Inbox

Channel gmail-phuoctaitp
Far :gmail-phuoctaitp-remote:
Near :gmail-phuoctaitp-local:
Patterns *
Create Both
SyncState *

IMAPAccount hotmail-tait
Host imap.outlook.com
User tai.t@hotmail.com
PassCmd "gpg -dq ~/.gnupg/hotmail-tait.gpg | xargs -0 bash -c"
AuthMechs "XOAUTH2"
SSLType IMAPS

IMAPStore hotmail-tait-remote
Account hotmail-tait

MaildirStore hotmail-tait-local
SubFolders Verbatim
Path  ~/Mail/tai.t@hotmail.com/
Inbox ~/Mail/tai.t@hotmail.com/Inbox

Channel hotmail-tait
Far :hotmail-tait-remote:
Near :hotmail-tait-local:
Patterns *
Create Both
SyncState *

{% endhighlight %}

## Crontab

Crontab is for automatically update your mailboxes. I sync my mailboxes every minute. If this the first time you use cron, you should check this page out 
[Crontab Guru](https://crontab.guru/#*_*_*_*_*)

{% highlight shell %}

crontab -e
* * * * * /bin/bash -l -c '/usr/local/bin/mbsync gmail-phuoctaitp >> /Users/taitran/log/mbsync-gmail-phuoctaitp.log 2>&1'
* * * * * /bin/bash -l -c '/usr/local/bin/mbsync hotmail-tait >> /Users/taitran/log/mbsync-hotmail-tait.log 2>&1'

{% endhighlight %}

## Curl

I use curl to handle oauth2 with microsoft or gmail server. Curl is available in different unix system, we don't need to add an other dependency. In this article I assume you know how to register your apps with google or microsoft to obtain the client_id and secret_id. Following are script for authenticating with microsoft server. Keep in mind that the request will be slightly different upon authenticating with different servers such as google


- First, open the browser to obtain the code

{% highlight shell %}

client_id="your_client_id"
scope="https://outlook.office.com/IMAP.AccessAsUser.All%20offline_access%20https://outlook.office.com/SMTP.Send"
redirect_uri="https://login.live.com/oauth20_desktop.srf"
auth_uri="https://login.microsoftonline.com/common/oauth2/v2.0/authorize"
open "${auth_uri}?client_id=${client_id}&response_type=code&redirect_uri=${redirect_uri}&scope=${scope}"

{% endhighlight %}

- Second, after obtaining the ${code}, we trade ${code} for refresh_token and access_token. Noticed that I don't send client_secret to the server, but in google authentication, I do. I use jq to extract information


{% highlight shell %}

curl -s \
-d "client_id=${client_id}" \
-d "code=${code}" \
-d "redirect_uri=${redirect_uri}" \
-d "grant_type=authorization_code" \
${token_uri} | jq '. | .access_token'

{% endhighlight %}

As we know, we need to automate this process, and access_token will be expired. Instead checking expires_in attribute, we just use refresh_token to obtain access_token every time 
we want to do authentication. I find that this way is simplest, but it doesn't affect your overall speed much.

{% highlight shell %}

cat ~/.gnupg/gmail-phuoctaitp.gpg
curl -s \
-d "client_id=your_secret_id" \
-d "refresh_token=your_refresh_token" \
-d "grant_type=refresh_token" \
https://login.microsoftonline.com/common/oauth2/v2.0/token | jq -r '. | .access_token'

{% endhighlight %}

- Now, we need to encrypt our script with gpg

{% highlight shell %}

gpg --encrypt ~/.gnupg/gmail-phuoctaitp.gpg

{% endhighlight %}

- Finally lets pass it to mbsyncrc via PassCmd. Noted that gpg output will be piped to xargs to eval the curl command.

{% highlight shell %}

PassCmd "gpg -dq ~/.gnupg/gmail-phuoctaitp.gpg | xargs -0 bash -c"

{% endhighlight %}

gpg will ask your passcode whenever decoding your gpg file; however it has a passcode session which allows you not to provide passcode everytime you run gpg -dq. gpg-agent will expires your session per your configuration in the apg-agent.conf in seconds. My setting is set to 30 days. 

{% highlight shell %}
> cat ~/.gnupg/gpg-agent.conf
default-cache-ttl 2592000
max-cache-ttl 2592000
{% endhighlight %}

This means that after 30 days since you provide passcode for gpg, you need to explicitly enter your passcode in order to reveal you gpg file. This will not be handle automatically for you, you need to run it on terminal to provide your passcode.

## Dynamically load your mailboxes

Mutt allows you to use shell commands in muttrc which is awesome to hack around with find command to list your mailboxes.


{% highlight shell %}
find ~/Mail/phuoctaitp@gmail.com -maxdepth 5 -mindepth 1 -type d | \
sed -Ee "/\[Gmail\]$|tmp$|new$|cur$/d" \
-e "s/ /\\\\ /g" | \
awk 1 ORS=" "
{% endhighlight %}

- mindepth=1 to exclude current folder '~/Mail/phuoctaitp@gmail.com" which is not a mail box dir. Isync didn't create any cur tmp and new dir for it.
- maxdepth=5 limit how many nested mail boxes from imap server, it's 5 here
- sed is used to eliminate all folders which are not mail boxes. In this case, there are:
    - [Gmail] dir is just an aggregate folder of Spam, Drafts,etc.
    - cur, new, and tmp are meta data directories
- the last 2 things are escaping the spaced folder e.i Sent Mail, and removing \n with awk 

## Open your mail boxes with fuzzy command

Below command will list all mail boxes under your account folder with the depth of 5. I use sed to make the output of find command look nicer. The output will be piped to fzf for selection. Again, I use sed to parse result from fzf to something mutt can understand (e.i push c=[Gmail]/Inbox).

As you see, mutt is very sensitive with space, so we need to replace all space with \<quote-char\>\<space\>

{% highlight shell %}
macro index,pager ,m "<enter-command>\`cd ~/Mail/phuoctaitp@gmail.com && find . -maxdepth 5 -mindepth 1 -type d | sed -Ee \"/\\[Gmail\\]$|new$|cur$|tmp$/d\" -e \"s/^\\.//g\" -e \"s/\\//./g\" | fzf-tmux -r 25 | sed -e \"s/ /\\<quote-char\\>\\<space\\>/g\" -e \"s/^\./=/g\" -e \"s/\\./\\//g\" -e \"s/^/push c/\" -e \"s/$/\\<enter\\>/g\" \` <enter>"; \
{% endhighlight %}

To be continue....

# links

https://www.cryptomonkeys.com/2015/09/mutt-and-msmtp-on-osx/
https://www.suffix.be/blog/mutt/
http://stevelosh.com/blog/2012/10/the-homely-mutt/

