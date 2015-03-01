---
layout: post
title: Write Canadian format letter in latex
categories:
  - latex
---

Default Canadian letter aligns all text on the left; however, letter.sty aligns fromaddress on the right. We need to modify letter.cls to correctly align fromaddress.

```sh
sudo vim /usr/share/texmf-dist/tex/latex/base/letter.cls
```

- Find following snippet, remove the tabular. That's all!

```latex
\newcommand*{\opening}[1]{\ifx\@empty\fromaddress
    \thispagestyle{firstpage}%
    {\raggedleft\@date\par}%
    \else  % home address
        \thispagestyle{empty}%
        {\raggedleft\begin{tabular}{l@{}}\ignorespaces
            \fromaddress \\*[2\parskip]%
                \@date \end{tabular}\par}%
                \fi
                \vspace{2\parskip}%
                {\raggedright \toname \\ \toaddress \par}%
            \vspace{2\parskip}%
#1\par\nobreak}
```

- Result

```latex
\newcommand*{\opening}[1]{\ifx\@empty\fromaddress
    \thispagestyle{firstpage}%
    {\raggedleft\@date\par}%
    \else  % home address
        \thispagestyle{empty}%
        {\ignorespaces
            \fromaddress \\*[2\parskip]%
                \@date\par}%
                \fi
                \vspace{2\parskip}%
                {\raggedright \toname \\ \toaddress}%
            \vspace{2\parskip}%
#1\par\nobreak}
```
