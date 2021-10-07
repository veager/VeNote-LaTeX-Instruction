 # 数学公式

## 1. 数学模型

LaTeX排版中，排版内容分为**文本模式**和**数学模式**。**数学模式**包括两种：**行内公式**和**行间公式**。

在数学模式中，使用`\text{<文本>}`实现中文文本现实。

### 1.1. 行内公式

**行内公式**一共有3种方式：

1. `$ $`

2. `\(  \)`

3. `\begin{math}  \end{math}`

### 1.2. 行间公式

行间公式：公式单独成行

1. `$$  $$`
2. `\begin{displaymath}  \end{displaymath}`
3. `\begin{equation}  \end{equation}`，可以实现自动编号。
    通过 `\lable{eq-1}`实现交叉引用。
4. `\begin{equation*}  \end{equation*}`，不带编号。

### 1.3. 必要宏包

`\usepackage{amsmath}` 矩阵

`\usepackage{amssymb}` 特殊符号



## 2. 特殊符号

### 2.1. 特殊符号对照表

LaTeX 希腊字母命令

[Latex常见符号对照表]([Latex常见符号对照表_赵氏春秋-CSDN博客_latex符号表](https://blog.csdn.net/zgj926503/article/details/52757631))

### 2.2. 特殊字体

| 命令             | 样式               |              |
| ---------------- | ------------------ | ------------ |
| `A`              | ${A}$              | 斜体         |
| `\mathrm{A}`     | ${\mathrm{A}}$     | 正体         |
| `\mathbf{A}`     | ${\mathbf{A}}$     | 正体，加粗   |
| `\boldsymbol{A}` | ${\boldsymbol{A}}$ | 斜体，加粗   |
| `\mathcal{A}`    | ${\mathcal{A,N}}$  | 花体，手写体 |
| `\mathbb{A}`     | ${\mathbb{A,R,N}}$ | 空心         |

### 2.3. 特殊命令

` \phantom{}`占位命令，用于占位，但不显示。只能用于数学模式。
$$
ABC\mathbf{D}E                     \quad 1234 \\
A\phantom{B}C\phantom{\mathbf{D}}E \quad 1{\phantom{2}}34
$$



## 3. 数学矩阵

引入宏包`\usepackage{amsmath}`

`\begin{matrix}  \end{matrix}`

- `pmatirx`小括号，`bmatrix`中括号，`Bmatrix`大括号，`vmatrix`单竖线，`Vmatrix`双竖线

- 矩阵环境中，用`&`隔列，用`\\`分割行

- 省略号：`\dots`横向，`\vdots`竖向，`\ddots`斜向

- `\begin{matrix}  \end{matrix}_{n \times n}`带矩阵维度

- 通过矩阵嵌套实现分块矩阵

- 三角矩阵：`multicolumn`合并多列

- 跨列的省略号：`\hdotsfor{<列数>}`

- 行内小矩阵：`\begin{smallmatrix}  \end{smallmatrix}`

`array`环境实现复杂矩阵排版，类似于表格环境`tabular`

```latex
\begin{arrary}{r|r}
	<content>
\end{array}
```



## 4. 多行公式

### 4.1. 常用命令

1. `gather` 和 `gather\*` 环境
   
   - 使用`\\`换行。默认会对每一行公式都自动编号。
   
   - 可以在`\\`前使用`\notag` 阻止编号
   
2. `align` 和 `align\*` 环境
   - 多公式多行对齐，通过`&`指定对齐位置
   
3. `split` 和 `split\*` 环境，嵌套在`equation`环境中
   - 单公式多行对齐，通过`&`指定对齐位置
   
   - 只有一个编号
   
4. `cases` 和 `cases\*` 环境，嵌套在`equation`环境中

   - 条件公式
     - 每行公式中使用 `&` 分隔为两部分，实现条件对齐

   - 使用`\\`实现换行，多条件

### 4.2. 进阶

#### 4.2.1. `align` 和 `alignat`

二者都创建基于`rl`对的列对齐，但是有以下两点不同

- 传入参数

  - `align`不需要传入参数，会根据内容创建足够多的列

  - `alignat`需要传入参数，指定想要多少列。（~~目前还不明白参数什么意思~~）

- 列与列间的空格

  - `align`在列与列之间添加空格

    - `<r col><l col> <space> <r col><l col> <space> `

 - `alignat`不会在列与列之间添加空格

    - `<r col><l col><r col><l col>`

- ~~个人理解~~
- 当 `&` 等于 1 时，
      - `&`符合分割左右列，并在此处对齐
- 当 `&` 大于 1时， 
  
  - 第奇数个`&`用于分割同一`rl`对的`<r col>`和`<l col>`，每一`rl`对在此处对齐
    
  - 第偶数个`&` 用于分割形成`rl`对，并在此处留白，以实现对齐

根据下述三个实例，来比较具体的不同

 1. `alignat` - 1

$$
\begin{alignat}{1}
& x_{1}  & + & 2x_{2} & \leq{} &  10 \\
& -x_{1} & + &  x_{2} & \leq{} &  4 \\
&        &   &  x_{2} & \geq{} &  2 \\
\end{alignat}
$$

 2. `alignat` - 2

$$
\begin{alignat}{1}
x_{1}  & + & 2x_{2} & \leq{} & 10 \\
-x_{1} & + &  x_{2} & \leq{} & 4 \\
       &   &  x_{2} & \geq{} & 2 \\
\end{alignat}
$$

 3. `align` 

$$
\begin{align}{1}
x_{1}  & + & 2x_{2} & \leq{} & 10 \\
-x_{1} & + &  x_{2} & \leq{} & 4 \\
       &   &  x_{2} & \geq{} & 2 \\
\end{align}
$$

