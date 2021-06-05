# 插入图片和表格

## 1. 插入图片

### 1.1. 命令

```latex
% 导言区
\usepackage{graphicx}
% 语法
\includegraphics[<选项>]{<文件名>}
% 图片格式
% *.eps, *.pdf, *.png, *.jpeg, *.bmp
% 文件路径
\graphicspath{{figures/},{pics/}}
% 文件在当前目录下的 figures 和 pics 目录 
```

**帮助文档：**texdoc graphic

### 1.2. 图片设置



## 2. 设置表格

### 2.1. 命令

```latex
\begin{tabular}[<垂直对齐方式>]{<列格式说明>}
	<表项> & <表项> & ... & <表项> \\
	......
\end{tabular}
```

- 用`\\`表示换行
- 用`&`表示不同的列
- `l`本列左对齐，`c`本列居中对齐，`r`本列右对齐
- `|`表示单竖线，`||`表示双竖线
- `\hline` 表示单横线，`\hline \hline`表示双横线
- `p{<宽>}`本列宽度固定，能够自动换行
- 正文区（文稿区）

**帮助文档：** texdoc booktab，texdoc longtab，texdoc tabu



## 3. 浮动体

### 3.1. 命令

```latex
\begin{figure}[<允许位置>]
    <任意内容>
\end{figure}
```
- <允许位置>参数（默认tbp）
- `h`，here：代码所在的上下文位置
- `t`，top：代码所在页面或之后页面的顶部
- `b`，bottom：代码所在页面或之后页面的底部
- `p`，page：浮动页面

其他设置与宏包

- 标题控制（caption，bicaption等宏包）
- 并排与子图表（subcaption，subfig，floatrow等宏包）
- 绕排（picinpar，wrapfig等宏包）

### 3.2. 实例

```latex
% 图片浮动体
\begin{figure}[htbp]
	\centering  % 浮动体内容居中
	\includegraphic[scale=0.3]{figure1}  % 插入图片
	\caption{figure caption name}  % 图标标题
	\label{fig-1}  % 图片标签,用于交叉引用
\end{figure}

% 表格浮动体
\begin{table}[h]
	\centering  % 浮动体内容居中
	\caption{table caption name}  % 图表标题
	\label{tab-1}  % 图表标签,用于交叉引用
	\begin{tabular}{l|c|r}  % 插入表格
		......
	\end{tabular}
\end{figure}
```

### 3.3. 交叉引用

```latex
\ref{label} 如: \ref{fig-1}
```
