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
}

@font-face {
    font-family: "Jetbrains Mono Extra Light Font";
    src: url("https://raw.githubusercontent.com/ryanoasis/nerd-fonts/refs/heads/master/patched-fonts/JetBrainsMono/NoLigatures/ExtraLight/JetBrainsMonoNLNerdFontMono-ExtraLight.ttf");
}

@font-face {
    font-family: "Julia Mono Font";
    src: url("https://raw.githubusercontent.com/cormullion/juliamono/refs/heads/master/JuliaMono-Regular.ttf");
}

x-row {
    text-rendering: optimizeLegibility;
    font-variant-ligatures: normal;
}

```

- Text font family:  'Jetbrains Mono Extra Light Font', 'Jetbrains Mono Font', 'Julia Mono Font'
