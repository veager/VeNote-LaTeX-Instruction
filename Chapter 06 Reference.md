# 参考文献管理

基本思想：“一次管理，多次使用”

## 1. `BibTeX`工具

### 1.1. TeXstudio工具设置

“设置TeXstudio” ->  “构建” -> “默认文献工具：BibTeX”

新建 \*.bib 文件记录修改参考文献信息

清理编译缓存文件

### 1.2. 参考文献样式设置

在导言区`\bibliographystyle{plain}`

### 1.3. 引用与参考文献条目

#### 1.3.1 引用

- `\cite{<label>}`

- `\citep{<label>}`

- `\citet{<label>}`

#### 1.3.2 参考文献条目

在正文区引入参考文献数据库`\bibliography{filename1,filename2}`

`\notice{*}`输出未引用的参考文献


## 2. `biber`工具

- biblatex / biber 是新的tex参考文献排版引擎

- 样式文件（参考文献样式文件\*.bbx文件，引用样式文件-\*.cbx文件）使用latex编写

- 支持根据本地化排版，如：

   - `biber -l zh__pinyin texfile`，用于按拼音排序
   - `biber -l zh__stroke texfile`，用于按笔画排序

### 2.1. TeXstudio工具设置

“设置TeXstudio” ->  “构建” -> “默认文献工具：Biber”

### 2.2. 参考文献样式设置

```latex
% 在导言区
\usepackage[style=numeric, backend=biber]{biblatex}
\usepackage[style=caspervector, backend=biber, utf8, sorting=cenyt]{biblatex}

% 引入参考文献数据库，不可以省略文件后缀名
\addbibresource{ref.bib} 
```

- `style` 参考文献样式文件，
- `utf8` 表示编码格式
- `sorting` 参考文献排序方式，`cenyt`表示分别按中文（c，Chinese）、英文（e，English）、作者姓名（n，name）、出版年份（y，year）、文献标题（t，title）排序。也可`cenyt`。

### 2.3. 引用与参考文献条目

#### 2.3.1 引用

- `\cite{<label>}`，无格式化引用

- `\parencite{<label>}`，带方括号的引用

- `\supercite{<label>}`，上标引用

#### 2.3.2 参考文献条目

```latex
% 列出未引用的参考文献
\nocite{*}
% 输出参考文献条目，title指定参考文献条目标题
\printbibliography[title = {参考文献}]
```

### 2.4. 命令提示符运行

```cmd
xelatex latexRefBibLaTeX
biber -l zh__pinyin latexRefBibLaTeX
xelatex latexRefBibLaTeX
xelatex latexRefBibLaTeX
% 编译两次，才能现实正确的引用编号
del *.aux *.bbl *.bcf *.blg *.log *.xml
```



## 3. 文献管理

- zotero
