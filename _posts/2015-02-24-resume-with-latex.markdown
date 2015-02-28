---
layout: post
---

### Packages

```sh
pacman -S texlive-core
pacman -S texlive-genericextra

axel http://tug.ctan.org/macros/latex209/contrib/shading.zip 
unzip shading.zip
sudo mv shading /usr/local/share/texmf/tex/latex
```

### Original latex template

```sh
axel "http://www.davidgrant.ca/sites/www.davidgrant.ca/files/resume.tex.txt"
```

### My resume

- [PDF format]({{ site.url }}/assets/resume.pdf)

```latex

\documentclass[letterpaper,11pt]{article}

\usepackage{shading}
\usepackage{color}
\usepackage{verbatim}

%Margin setup
\setlength{\voffset}{0.1in}
\setlength{\paperwidth}{8.5in}
\setlength{\paperheight}{11in}
\setlength{\headheight}{0in}
\setlength{\headsep}{0in}
\setlength{\textheight}{11in}
\setlength{\textheight}{9.5in}
\setlength{\topmargin}{-0.25in}
\setlength{\textwidth}{7in}
\setlength{\topskip}{0in}
\setlength{\oddsidemargin}{-0.25in}
\setlength{\evensidemargin}{-0.25in}
\pagestyle{empty}
\raggedbottom{}
\raggedright{}
\setlength{\tabcolsep}{0in}
\definecolor{mygrey}{gray}{0.85}

%Custom commands
\newcommand{\resitem}[1]{\item #1 \vspace{-2pt}}
\newcommand{\resheading}[1]{\noindent\fcolorbox{mygrey}{mygrey}{\makebox[\dimexpr\textwidth-2\fboxsep-2\fboxrule][l]{\textbf{~#1}}}}
\newcommand{\ressubheading}[4]{\begin{tabular*}{6.5in}{l@{\extracolsep{\fill}}r}
		\textbf{#1} & #2 \\
		\textit{#3} & \textit{#4} \\
\end{tabular*}\vspace{-6pt}}

\begin{document}
\begin{tabular*}{7in}{l@{\extracolsep{\fill}}r}
\textbf{\Large Tai Tran}  & 587--938--8658\\
\#12025--105 Street Northwest &  tai.t@hotmail.com \\
Edmonton, AB T5G 2N6 & http://taitran.ca\\
\end{tabular*}
\\

\vspace{0.1in}

\resheading{Summary of Qualifications}
\begin{itemize}
    \resitem{Dealing with people, problems, and situations honestly}
    \resitem{Ability to work alone or as part of a team}
    \resitem{Quickly solve problems when arising}
    \resitem{Handle things in a well-organized manner}
\end{itemize}

\resheading{Education}
\begin{itemize}
\item
	\ressubheading{Macewan University}{Edmonton, AB}{B.Sc., Computer Science }{Jan. 2015 --- 2019}
	%\begin{itemize}
		%\resitem{Relevant courses: Semiconductor Devices: Physics and Modelling, Digital VLSI Design, Amorphous Silicon, Mixed-signal modelling with VHDL-AMS}
	%\end{itemize}
\item
	\ressubheading{University of Science}{HoChiMinh, Vietnam}{B.Sc., Information Technology}{2009 --- 2011}
\item
	\ressubheading{University of Science}{HoChiMinh, Vietnam}{Diploma of Information Technology}{2006 --- 2009}
\end{itemize}

\resheading{Work Experience}
\begin{itemize}
\item
	\ressubheading{TMA Solution}{HoChiMinh, Vietnam}{Senior Java Software Engineer}{Oct. 2012 --- Oct. 2014}
	\begin{itemize}
		\resitem{Lead a team of 5 people}
		\resitem{Delegate tasks to other team members}
		%\resitem{Analyze technical specifications and implement new features}
		%\resitem{Refactor and optimize performance for legacy framwork}
	\end{itemize}

\item 
	\ressubheading{TMA Solution}{HoChiMinh, Vietnam}{Java Software Engineer}{Oct. 2009 --- Oct. 2012}
	\begin{itemize}
		%\resitem{Implement non-native various commands for TL1 protocol}
		%\resitem{Perform performance testing with heavy load of TL1 requests}
		\resitem{Identify failures in software application and fix it}
		\resitem{Report technical issues and suggest solutions to technical leader}
	\end{itemize}
\end{itemize}

\begin{comment} % School Projects
\resheading{School Projects}
\begin{itemize}
\item
	\ressubheading{SpectraVu Medical}{Vancouver, BC}{Engineering Physics Project Lab, APSC 479}{Sep. 2001 - Apr. 2002}
	\begin{itemize}
		\resitem{Designed and implemented a digital video processing system for lung cancer imaging}
		\resitem{Selected components (video DAC, ADC) and created schematics in OrCAD.}
	\end{itemize}
\end{itemize}
\end{comment}

\begin{comment} %Awards
\resheading{Awards}
	\begin{tabular*}{6.5in}{l@{\extracolsep{\fill}}r}
		Faculty of Engineering Scholarship (\$2,300) & 2002\\
		Ontario Graduate Scholarship (OGS) (\$15,000) & 2002-2003\\
\end{tabular*}
\end{comment}

\begin{comment} % Skills
\resheading{Skills}
\begin{description}
\item[Languages:]
C/C++, \LaTeX, Java, SPICE, MEDICI (TCAD), VHDL/VHDL-AMS, 68000 and PIC Assembly
\item[Operating Systems:]
Linux (Debian), Solaris, UNIX, MacOS X, Windows 95/98/NT/2000/XP
\item[Applications:]
Mathematica, MatLab, GNU Octave, LabVIEW, Cadence, \LaTeX, OpenOffice, MS Office XP, OrCAD schematic capture \& PCB layout, Altera MAX+PlusII VHDL FPGA Design
\item[Lab Skils:]
Digital/Analog Scopes, Spectrum Analyzer, Function Generators
\item[Fab Skills:]
PECVD and sputtering deposition, UV lithography, wet etch, dry etch (RIE), mask aligner, step profiler, ellipsometry, infrared spectroscopy, x-ray diffraction
\item[Miscellaneous:]
software configuration management, strong verbal and written communication skills, excellent troubleshooting and debugging skills, exceptional problem solving skills, good teams skills
\end{description}
\end{comment}

\resheading{Volunteer}
\begin{itemize}
\item
	\ressubheading{Students' Association of Macewan University}{Edmonton, AB}{Assistant Coordinator}{Jan. 2014 --- April. 2014}
	\begin{itemize}
		\resitem{Help set up and take down various events in Alberta College Campus}
	\end{itemize}
\end{itemize}

\resheading{Interests}
\begin{description}
\item Playing basketball, table tennis, and swimming
%\item[Sports:] Playing basketball and swimming
%\item[Computers:] Enjoy using and learning Linux systems, writing shell scripts to faciliate technical workflow
%\item[Musical:] Playing basic guitar
%\item[Membership:] Open source member of Github since 2012 
\end{description}

\end{document}

```
