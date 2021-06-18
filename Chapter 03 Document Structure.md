# LaTex 文档结构

## 1. 文件基本结构

- 导言区：基本设置、命令定义、引入宏包

- 正文区（文稿区）：书写正文

## 2. 正文结构

### 2.1. 基本结构

正文内容结构一般为三级结构，每一级别对应一级标题，并且自动编号。

```latex
\documentclass{ctexart}

\begin{document}
	\section{引言}
	\section{实验}
		\subsection{数据}
		\subsection{图表}
			\subsubsection{图表1}
			\subsubsection{图表2}
\end{document}
```

### 2.2. 调整标题级别

```latex
\setcounter{tocdepth}{3}    
% toc 即 table of content，表示目录显示的深度
\setcounter{secnumdepth}{4} 
% secnum 即 section number，表示章节编号的深度
```

标题级别：

- -1 part：
- 0 chapter：
- 1 section：
- 2 subsection：
- 3 subsubsection：
- 4 paragraph：`\paragraph{标题名}~{}`
- 5 subparagraph：

## 3. 特殊字符