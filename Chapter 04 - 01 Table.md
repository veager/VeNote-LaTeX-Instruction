#### 表格填充颜色

```latex
\usepackage{colortbl}

\rowcolor{<color>} 行颜色
\columncolor{<color>} 列颜色
\cellcolor{<color>} 单元格颜色
```

####  三线表

```latex
\usepackage{booktabs}
\toprule  \midrule  \bottomrule`
```

#### 表格内换行 借助`\makecell`命令

```latex
\usepackage{makecell}
\makecell[<vertical or/and horizontal alignment>]{<hcell text>}
```

#### 超宽表格居中

```Latex
\usepackage{chngpage}
\begin{adjustwidth}[]{leftmargin}{rightmargin}
	content
\end{adjustwidth}
```

