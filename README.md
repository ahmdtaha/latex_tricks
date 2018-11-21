# Latex Tricks
Some useful latex tricks when writing academic papers

### Compressing long equations
```
\begin{equation}
\scalebox{0.95}[1]{$ put your equation here $}
\end{equation}
```

## Latex Tables Tricks
[Latex Table generate](https://www.tablesgenerator.com/)

```\cellcolor{yellow} ``` color a table cell

```\cellcolor{yellow!50}``` color a table cell with alpha

```
\newcommand*\rot{\rotatebox{90}}
\rot{ rotated text}
``` 
rotate text inside table


### Row Cells Gradient Coloring

```
\newcommand*{\MinNumber}{0.0}%
\newcommand*{\MaxNumber}{35}%
\newcommand{\ApplyGradient}[1]{%
	\pgfmathsetmacro{\PercentColor}{
	max(min(100.0*(#1 -\MinNumber)/(\MaxNumber-\MinNumber),100.0),0.00)
	} 
	\edef\x{\noexpand\cellcolor{blue!\PercentColor}}\x\textcolor{white}{#1}}
```

Do gradient color based on a parameter, e.g ```\ApplyGradient{17.80}```



### Bold an entire table row

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



## Image 
```
\setlength{\fboxsep}{0pt}
\setlength{\fboxrule}{2pt}
\fcolorbox{green}{white}{ <your image here> }
```
Add color border to image


## Supplementary Material
```
\newcommand{\beginsupplement}{%
	\setcounter{table}{0}
	\renewcommand{\thetable}{S\arabic{table}}%
	\setcounter{figure}{0}
	\renewcommand{\thefigure}{S\arabic{figure}}%
}

\beginsupplement
``` 
Change tables and figures captions in supplementary material