---
layout: post
title: Regular Expression
categories:
 -
---

## Short hand character set

Digit | \d  [0-9] [[:digit:]]
Word | \w  [a-zA-Z0-9_] 
White space | \s  [ \t\r\n]
Not digit | \D  [^0-9]
Not Word | \W  [^a-zA-Z0-9_]
Not White space | \S  [^ \t\r\n]

[[:alpha:]] | [a-zA-Z]
[[:alnum:]] | [a-zA-Z0-9]

## Metacharacters
Any character except new line - wildcard | .
Line return, new line | \r, \n, \r\n

## Repetition mechacharacters

Preceding item, zero or more times | *
Preceding item, one or more times | +
Preceding item, zero or one time | ?

Match lower case words ending in 'ed' | \s[a-z]+ed\s

## Quanlified Repetition

Start quantified repetion of preceding item | {
End quantified repetion of preceding item | }

Match numbers with 4 to 8 digits | \d{4,8}
Match numbers with exact 4 digits | \d{4}
Match numbers with 4 or more digits | \d{4,}
{0,} same as *
{1,} same as +
{0,1} same as ?

## Greedy Expression

- Default match strategy is greedy 
- Standard repetition quantifiers are greedy
- Expression tries to match the longest string


## Lazy expression

Mark preceding quantifier lazy | ?
Change match strategy is lazy, match as little as possible

*?
+?
??

\d+\w+?\d+ > will match \w+ one time only

01_KJ_03_Mass_22_k.txt
01_KJ_07

## Grouping

(in)?dependent will match independent, dependent

- posix sed can't use \d, gotta use [[:digit:]]
echo 780-909-1111 | sed -E 's|([[:digit:]]{3})-([[:digit:]]{3}-[[:digit:]]{4})|(\1)-\2|'

Eager: peanut|peanutbutter will match only "peanut" in "peanutbutter"
Greedy: peanut(butter)? will match whole word "peanutbutter" eager

## Start and End 

start of the string | ^ or \A (in pcre regex - per compatible regular expression)
end of the string | $ or \Z (pcre only)

## Line mode & multiline

^[a-z]+$ will match only first line of the text, as carrier return is not matched as alpha characters.

Sed does not care, it's multiple line mode by default

this: sdf

printf "780-909-1111\n870-243-2312\n" | sed -E 's|([[:digit:]]{3})-([[:digit:]]{3}-[[:digit:]]{4})|(\1)-\2|'

## Word boundaries

start/end of the word | \b

\b is not available in vim, pcre only

vim use <> to define word boundaries

Search: /\v<\w{3}s> will match word end with s and it is 4 characters
Substitube: :%s//place/gc will replace any character is highlighted in that's matched & replace with place global with prompt

## Capturing group & backreferences

Backreference can be use right away in matching process

 /\v(my) oh \1 will match "my oh my"

/\v\<(ok|essm)\><\w+>\<\/\1\> will match following records
<essm>hello</essm>
<ok>hekd</ok>

Following will match below 2 words & surround with *
self-reliance
reliance
Search: ((self-)?reliance)
Run: :%s//*\1*/gc

## Supress group capturing

Disable auto capturing for the group | ?:


i (?:love|like) (.+) will not capture (love|like) group as \1

```sh
printf 'i love pizza\ni like pizza\n'  | perl -pe 's/i (love|like) (.+)/i \1/gi'
```

## Look ahead & assertions (pcre)

```sh
printf '11-2-2025\n2025\n2024-11-3\n1029-1\n1988-03-09\n' | perl -ne 'print if /(?=\d{4}-\d{2}-\d{2})\d{4}/'
```


## Some text for testing regex in vim

\d\.\s[[:alpha:]]{3,4}\n

1. a
2. ab
3. abc
4. abcd
5. abcde 
6. abcdef

\d+\w+\d+

01_KJ_03_Mass_22_k.txt
01_KJ_07

".+", ".+"

"Princess", "King", "Prince", "Queen"

Page 266

## Credit

This note is taken upon doing a online regex course in Linkedin Network from Kevin Skoglund
