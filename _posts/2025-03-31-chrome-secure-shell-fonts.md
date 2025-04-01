---
layout: post
title: Chrome Secure Shell Fonts
categories:
 -
---

## Add Nerd font from github to Secure Shell options

- Custom CSS (inline text)

```css

@font-face {
    font-family: "Jetbrains Mono Font";
    src: url("https://raw.githubusercontent.com/ryanoasis/nerd-fonts/refs/heads/master/patched-fonts/JetBrainsMono/NoLigatures/Regular/JetBrainsMonoNLNerdFontMono-Regular.ttf");
    font-weight: normal;
    font-style: normal;
}

@font-face {
    font-family: "Terminess Nerd Font";
    src: url("https://raw.githubusercontent.com/ryanoasis/nerd-fonts/refs/heads/master/patched-fonts/Terminus/TerminessNerdFont-Regular.ttf");
    font-weight: normal;
    font-style: normal;
}

x-row {
    text-rendering: optimizeLegibility;
    font-variant-ligatures: normal;
}

```

- Text font family: 'Jetbrains Mono Font', 'Terminess Nerd Font'
