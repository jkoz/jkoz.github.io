---
layout: post
title: oauth2 with mutt
categories:
  -
---

## mutt with sidebar

git clone https://github.com/karelzak/mutt-kz && \
  cd mutt-kz && ./prepare --enable-debug --enable-imap --enable-pop --enable-sidebar --enable-hcache --enable-smtp --with-ssl

## sals2 oauth2

git clone https://github.com/jkoz/sasl2-oauth && \
  cd sasl2-oauth && ./autogen.sh && ./configure --prefix=/usr && sudo make install

## isync

pacman -S perl-timedate

git clone git://git.code.sf.net/p/isync/isync && \
  cd isync && ./autogen.sh && ./configure --with-sasl && sudo make install

## oauth2

git clone https://github.com/jkoz/OAuth2 && \
  cd OAuth2 && sudo make install

- add client id, secret id, and redirect id

## run it !

mbsync channels

mutt
