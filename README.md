# Latex Tricks
Some useful latex tricks when writing academic papers



## 1. Latex Tables Tricks
[Latex Table generate](https://www.tablesgenerator.com/)
Follow [this guideline](./guide-tables.pdf)

```
\usepackage{xcolor,colortbl}
\cellcolor{yellow} 
``` 

color a table cell

```\cellcolor{yellow!50}``` color a table cell with alpha

```
\newcommand*\rot{\rotatebox{90}}
\rot{ rotated text}
``` 
rotate text inside table

```\setlength\tabcolsep{2.5pt} % default value: 6pt``` shrink table columns spacing


### Row Cells Gradient Coloring
Do gradient color based on a parameter, e.g ```\ApplyGradient{17.80}```

```
\newcommand*{\MinNumber}{0.0}%
\newcommand*{\MaxNumber}{35}%
\newcommand{\ApplyGradient}[1]{%
	\pgfmathsetmacro{\PercentColor}{
	max(min(100.0*(#1 -\MinNumber)/(\MaxNumber-\MinNumber),100.0),0.00)
	} 
	\edef\x{\noexpand\cellcolor{blue!\PercentColor}}\x\textcolor{white}{#1}}
```


Bold an entire table row

```
\usepackage{array}
\newcolumntype{+}{>{\global\let\currentrowstyle\relax}}
\newcolumntype{-}{>{\currentrowstyle}}
\newcommand{\rowstyle}[1]{\gdef\currentrowstyle{#1}%
	#1\ignorespaces
}
\begin{document}
......

\begin{tabular}{|+l|-l|-l|-l|-l|-l|-l|-l|-l|}
		\rowstyle{\bfseries}
		our approach & X & Y   & Z& K   & M   & N & L & Z \\ \hline
\end{tabular}

```
Hide tables during draft

```
\excludecomment{table}
\let\endtable\relax
```
or 

```
\usepackage{environ}
\RenewEnviron{table}{}
```
## 2.Images 
Add color border/outline to image

```
\setlength{\fboxsep}{0pt}
\setlength{\fboxrule}{2pt}
\fcolorbox{green}{white}{ <your image here> }
```

Hide figures during draft

```
\excludecomment{figure}
\let\endfigure\relax
```
or

```
\usepackage{environ}
\RenewEnviron{figure*}{}
\RenewEnviron{figure}{}
```

## 3.Equations
Compress long equations

```
\begin{equation}
\scalebox{0.95}[1]{$ put your equation here $}
\end{equation}
```


## 4. Math
Round numbers & mathematical mainpulation

```
\usepackage{xfp}
\usepackage{etoolbox,siunitx}

\newcommand{\round}[1]{\num[round-mode=places,round-precision=2]{\fpeval{#1*100}}}
\newcommand{\Round}[1]{\num[round-mode=places,round-precision=3]{#1}}
```



## 5.Supplementary Material
Change tables and figures captions in supplementary material

```
\newcommand{\beginsupplement}{%
	\setcounter{table}{0}
	\renewcommand{\thetable}{S\arabic{table}}%
	\setcounter{figure}{0}
	\renewcommand{\thefigure}{S\arabic{figure}}%
}

\beginsupplement
``` 

## 6.Drafting & Editing
Highlight a sentence

`
\usepackage{soul}
\hl{text}
`

## 7.Arxiv submission
* Add `\pdfoutput=1` to the main within the first 5 lines.
* Delete `missfont.log` from your submission



## 7. Misc
[Mathematical symbols by drawing](http://detexify.kirelabs.org/classify.html) 

[Quotation Marks and Dashes](https://www.maths.tcd.ie/~dwilkins/LaTeXPrimer/QuotDash.html)

[Pgfplots gallery](http://pgfplots.sourceforge.net/gallery.html)

[Online Latex Compiler] (https://www.latex4technics.com/)

Resolve CVPR infected [`eso-pic.sty`](https://github.com/ahmdtaha/latex_tricks/blob/master/eso-pic.sty) file
