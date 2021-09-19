

## `listings`

用于设置代码块

- 参考资料

[LaTeX listings 宏包使用说明（一）](https://zhuanlan.zhihu.com/p/261667944), 知乎.

### 1. 引入与使用

引入宏包

```latex
\usepackage{listings}
```

使用

```latex
\begin{lstlisting}
	codes
\end{lstlisting}
```




### 2. 设置命令

```latex
\lstset{
     columns = fixed,       
     basicstyle = \linespread{0.8} \ttfamily,             % 设置行距，字体
     numbers = left,                                      % 在左侧显示行号
     numberstyle = \tiny \color{gray},                    % 设定行号格式
     keywordstyle = \bfseries \color[RGB]{40,40,255},              
     % 设定关键字颜色
     numberstyle = \footnotesize\color{darkgray},           
     commentstyle = \color[RGB]{0,96,96},                   
     % 设置代码注释的格式
     stringstyle = \color[RGB]{128,0,0},                    
     % 设置字符串格式
     frame = single,                                        
     % 不显示背景边框
     backgroundcolor = \color[RGB]{245,245,244},          % 设定背景颜色
     showstringspaces = false,                            % 不显示字符串中的空格
     language=R                                          % 设置语言
}
```

#### 行号相关设置

| 参数                       | 说明                                | 可选值                                                       |
| -------------------------- | ----------------------------------- | ------------------------------------------------------------ |
| `numbers`                  | 行号                                | `left`：左侧显示行号<br/>`right`：右侧显示行号<br/>`none`：不显示行号 |
| `stepnumber`               | 每隔多少行显示行号                  | 整数                                                         |
| `numbersep`                | 行号与代码内容的间隔                |                                                              |
| `firstnumber`              | 行号起始数字                        | 整数：<br/>`last`：起始行数为上一段`lstlisting`环境结尾的行数·` |


#### 框架相关设置

| 参数                                                         | 说明                                                         | 可选值                                                       |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `frame`                                                      | 代码块边框设置                                               | `topline`：只有上侧有线<br/>`rightline`：只有右侧有线<br/>`bottomline`：只有底部有线<br/>`leftline`：只有左侧有线<br/>`trbl`，`tbl`，`tb`：按照top、right、bottom、left顺序，指定的任意方位设置边框<br/>`TRBL`，`TBl`，`Tb`：大写字母表示双竖线<br/>`shadowbox`：带有阴影<br/>`none`：不设置边框 |
| `frameround`                                                 | 边框圆角                                                     | `fftt`：边框右上角、右下角、左下角、左上角（顺时针方向）4个角的方角（`f`）或圆角（`t`） |
| `rulecolor`                                                  | 设置框架线条颜色                                             |                                                              |
| `rulesepcolor`                                               | 设置框架阴影颜色                                             | <br/>只有当`frame=shadowbox`才会起作用                       |
| `linewidth`                                                  | 行宽                                                         | 可与`framexrightmargin`产生相同效果                          |
| `framexleftmargin`<br/>`framexrightmargin`<br/>`framextopmargin`<br/>`framexbottommargin`<br/> | 边框往左、右、上、下扩展的距离<br/>仅改变框架，不会改变代码、行号的位置 | **距离**：可以为正数、或负数，分别表示往外、或内扩展<br/>    |
| `xleftmargin`<br/>`xrightmargin`<br/>`xtopmargin`<br/>`xbottommargin` | 调整框架整体（包括框架、代码、行号）往左、右、上、下扩展的距离。 | **距离**：可以为正数、或负数，分别表示往外、或内扩展<br/>    |
| `aboveskip`<br/>`belowskip`                                  | 框架整体与上、下方的距离                                     | **距离**：                                                   |

#### 样式相关设置

| 参数           | 说明       | 可选值 |
| -------------- | ---------- | ------ |
| `numberstyle`  | 行号样式   |        |
| `keywordstyle` | 关键字样式 |        |
| `stringstyle`  | 字符串样式 |        |
| `commentstyle` | 注释样式   |        |

#### 其他相关设置

| 参数                       | 说明                                | 可选值                                          |
| -------------------------- | ----------------------------------- | ----------------------------------------------- |
| `columns`                  | 调整字母之间的距离                  | `fixed`：<br/>`flexible`：<br/>`fullflexible`： |
| `firstline`<br/>`lastline` | 只排版`firstline`到`lastline`的代码 | 整数：                                          |
| `language`                 | 程序语言                            | `Python`，`R`，`C++`，`Jave`等                  |

### 3. 设置字体

1. 将编译器（complier）改成 XeLaTex
2. 引入宏包 `fontspec`，并通过 `\setmonofont` 命令设置等宽字体
3. 在`lstset` 或 `lstlisting` 中设置 `basicstyle = \ttfamily`

```latex
\usepackage{fontspec}
\setmonofont{Source Code Pro}

\begin{lstlisting}[basicstyle = \ttfamily]
	codes
\being{lstlisting}
```

- Overleaf [内置字体名称](https://www.overleaf.com/learn/latex/Questions/Which_OTF_or_TTF_fonts_are_supported_via_fontspec%3F)

- [Overleaf 自定义字体](https://www.overleaf.com/learn/latex/XeLaTeX)

### 参考资料

[*LaTeX listings 宏包使用说明（一）*](https://zhuanlan.zhihu.com/p/261667944). 知乎专栏.  

