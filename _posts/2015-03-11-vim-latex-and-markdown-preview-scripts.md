---
layout: post
title: Vim, Latex and Markdown preview scripts
categories:
  - vim
  - latex
  - markdown
---

Although it is easily to search for latex or markdown preview tools in github, most of them are written in viml, which is awesome. However, I personally love to solve problems by small tools in flavor of the flexibility of shell scripting.

This little trick is not generic; however, it serves my need well upon accompanied with [Tpope's vim-dispatch](https://github.com/tpope/vim-dispatch) and [Reedes's writer tools](https://github.com/reedes/vim-pencil)

#### Preview script
```sh
file $1 | grep -iq latex && pdflatex -output-directory /tmp $1

# markdown
basename $1 | grep -iq "\.md$" && pandoc --template=$PANDOC_TEMPLATES/default.latex -s $1 -o /tmp/${fn}

wid=$(xdotool search --name "${fn}")

if test -z "$wid"; then
    setsid zathura-tabbed /tmp/${fn}
    xdotool search --name "${fn}" windowactivate
else
    xdotool key --window $wid 'R'
fi
```

#### vimrc 
```vim
    autocmd FileType tex,latex
                \   call pencil#init({'wrap': 'soft', 'textwidth': 80, 'conceallevel': 3})
                \ | call litecorrect#init()
                \ | setl spell spl=en_us noru nonu nornu
                \ | setl fdo+=search
                \ | setl nocursorcolumn
                \ | let b:dispatch = 'sh /usr/local/bin/preview %:p'
    autocmd FileType markdown,mkd,md
                \   call pencil#init({'wrap': 'soft', 'textwidth': 80, 'conceallevel': 3})
                \ | call litecorrect#init()
                \ | setl spell spl=en_us noru nonu nornu
                \ | setl fdo+=search
                \ | let b:dispatch = 'sh /usr/local/bin/preview %:p'

    " headless dispatch
    nn <F9> :silent Dispatch!<CR>
```

#### zathura-tabbed
```sh
#!/bin/sh

xidfile="/tmp/tabbed-zathura.xid"
uri=""

if [ "$#" -gt 0 ];
then
    uri="$1"
fi

runtabbed() {
    tabbed -dn tabbed-zathura -r 2 zathura -e '' "$uri" >"$xidfile" \
        2>/dev/null &
}

if [ ! -r "$xidfile" ];
then
    runtabbed
else
    xid=$(cat "$xidfile")
    xprop -id "$xid" >/dev/null 2>&1
    if [ $? -gt 0 ];
    then
        runtabbed
    else
        zathura -e "$xid" "$uri" >/dev/null 2>&1 &
    fi
fi

```
