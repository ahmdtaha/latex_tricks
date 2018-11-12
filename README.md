# Latex Tricks
Some useful latex tricks when writing papers

### Compressing long equations
```
\begin{equation}
\scalebox{0.95}[1]{$ put your equation here $}
\end{equation}
```

## Latex Tables Tricks
```\cellcolor{yellow} ``` color a table cell

```\cellcolor{yellow!50}``` color with alpha

```\newcommand*\rot{\rotatebox{90}}
\rot{ rotated text}
``` 
rotate text inside table


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

## Image 
```
\setlength{\fboxsep}{0pt}
\setlength{\fboxrule}{2pt}
\fcolorbox{green}{white}{ <your image here> }
```
Add color border to image