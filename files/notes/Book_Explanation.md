## ✅ 标准 LaTeX 笔记生成 Prompt（精炼严谨版）



请你生成一份 **LaTeX 笔记**，要求如下：

------

### 1. 基本语言与风格要求

- **使用英文撰写**
- 这是研究生/博士水平的理论物理笔记，请保持**严谨、精确、逻辑清晰**
- 不要吝啬篇幅：
  - 该解释清楚的地方一定要用完整语言解释，
  - 写出推导过程，尤其是我要你【具体】写出过程的地方！！！
  - 允许并鼓励适当补充背景、推导思路、物理直觉

------

### 2. 结构要求（Section / Subsection）

- 使用 `\section{}`，从而实现编号为 **1, 2, 3, ...**

- 使用 `\subsection{}`，从而编号为 **1.1, 1.2, 2.1, ...**

- Subsection 内部如果存在明显的**层次、视角、逻辑切换**，需要另起段落；不允许私自添加小节

  如有需要，我会指出‘Point’，见下一小节

- 如果我明确说明“另起一段”，必须另起一段
  如果我没有明说，但内容存在明显层次变化，你也必须另起一段

------

### 3. Subsection 内的【Point】格式（必须严格遵守）

当需要【Point】标出某个子层次时，请使用如下 **LaTeX 格式**：

```latex
\\

\noindent
$\blacksquare$ \textbf{Title of the Point}

Main text
```

注意以下细节（非常重要）：

- 与上一段 **隔一个空行**
- `$\blacksquare$ \textbf{...}` 与正文之间 **必须有换行**
- Point 只是结构提示，其余内容**不要用显式分点**



如果没有十分鲜明的“分点结构”，可以使用加粗的形式在小节内开启一个新话题。

------

### 4. 段落组织原则

- 我说明“另起一段”时：**必须另起**
- 我没有说明时：
  - 只要出现视角切换、物理层次变化、推导阶段变化
  - **你需要主动另起一段**
- 目标是：读者可以清楚“现在在干什么、为什么这么做”

------

### 5. 数学公式规范（必须遵守）

- 行内公式：使用 `\( ... \)`

- 行间公式：

  - 如需编号，使用：

    ```latex
    \begin{equation}
    ...
    \end{equation}
    ```

- **不要使用 `$$ ... $$`**

- 符号定义必须清楚，避免“默认读者知道”

------

### 6. 【重要结论】的处理（必须框出）

当我标注【重要结论】时，你**必须**使用如下格式框出：

```latex
\begin{mdframed}
The \textbf{superfluid component} corresponds to the macroscopically occupied mode and carries no entropy;
the \textbf{normal component} is made of thermal excitations and carries all the entropy.
\end{mdframed}
```

- 框内语言应简洁、结论化、可引用

------

### 7. LaTeX 文档整体结构（必须原样使用）

请使用以下 LaTeX 设定，不要修改、不遗漏：

```latex
\documentclass[11pt]{article}
\usepackage{pxfonts}
\usepackage[a4paper,margin=1in]{geometry}
\usepackage{amsmath,amssymb,bm}
\usepackage{hyperref}

\usepackage{indentfirst}
\setlength{\parindent}{2em}

\usepackage[most]{tcolorbox}
\usepackage{xcolor}

\tcbset{
  enhanced,
  breakable,
  colback=blue!4,
  colframe=blue!25,
  coltitle=black,
  fonttitle=\bfseries,
  boxrule=0.6pt,
  arc=2mm,
  left=2mm,right=2mm,top=1.2mm,bottom=1.2mm,
}

\newtcolorbox{mybox}[1]{title={#1}}

\title{}
\author{Tristan.W}
\date{\today}

\begin{document}
\maketitle
```

正文内容写在 `\maketitle` 之后。

------

### 8. 内容来源说明

- 我提供的笔记内容可能已经有一定组织
- 你 **不需要沿用我的语言或行文顺序**
- 但你 **必须覆盖所有要点**
- 允许并鼓励你：
  - 重组逻辑
  - 增加解释
  - 提升理论完整性

------

### 9. 输出要求

- 只输出 **完整、可编译的 LaTeX 源码**
- 不要输出任何解释、注释或多余说明
- 不要省略 `\end{document}`

------

### 【笔记内容】

请使用者自行补充











