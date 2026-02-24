---
layout: post
title: github and jekyll
categories:
  - github 
---

### installation

```
sudo pacman -S ruby
gem install jekyll
gem install bundler
gem install github-pages
```

### checkout source

```
git clone https://github.com/jkoz/jkoz.github.io
```

### serve

```
cd ~/jkoz.github.io && bundle exec jekyll serve
```

### Github auth

```
eval "$(ssh-agent -s)" && ssh-add ~/.ssh/id_ed12519
```
