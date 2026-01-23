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









请整理latex笔记，请你完整遍历我们的讨论，该补充的细节和计算要写上；但是避免啰嗦和繁琐。大致的内容放在下面了，可能不全，你有很大的自由增补的权利，因为我下面列举的只是要点、很可能组织不佳或者有所遗漏。尤其是我说了“。。。”的地方，你需要认真思考要讨论什么内容。

第一章 Fermi–Hubbard 模型及其对称性

第一节是：形式和符号含义，用box简单解释一下将相互作用项写成 $(\hat{n}_{i\uparrow}-\tfrac12)(\hat{n}_{i\downarrow}-\tfrac12)$ 的形式，等价于对化学势作 $U/2$ 的平移

第二节讲正则系综表示。写出哈密顿量和守恒量（doping和spin imbalance）。用一个box回顾和对比巨正则系综和正则系综；以及我们这里使用正则系综的原因（我猜是以为doping不变，所以没有相应的涨落，如果我说的不对你可以纠正）

第三节讲自旋旋转对称性。从Pauli 矩阵完备性和S的定义式出发，得到
$$
\frac12 \hat{n}_i^2
=
\hat{n}_{i\uparrow}
-
\frac{2}{3}
\hat{\mathbf S}_i\cdot\hat{\mathbf S}_i.
$$
记得用box补充详细的过程推导

进而得到改写后的哈密顿量
$$
\hat{H}_{\mathrm{FH}}
=
-J \sum_{\langle ij\rangle,\sigma}
\hat{c}_{i\sigma}^\dagger\hat{c}_{j\sigma}
-
\frac{2U}{3}\sum_i \hat{\mathbf S}_i^2
-
\mu\sum_i \hat{n}_i
-
2h\sum_i \hat{S}_{zi}.
$$
从哈密顿量不难看出全局与局域自旋对称性（分h=0或不等于0讨论）



第二章讲粒子–空穴变换

第一节简单讨论基本思想--为什么变换？。。。

第二节讲一下naive的$\hat{c}_{i\uparrow}\rightarrow \hat{c}_{i\uparrow},\qquad
\hat{c}_{i\downarrow}\rightarrow \hat{c}_{i\downarrow}^\dagger.$

解释如何相互作用强度 $U$ 变号（排斥 $\leftrightarrow$ 吸引）；化学势项与 Zeeman 项相互交换角色。最后提到动能项会变

第三节讲bipartite lattice能够使得动能不变

首先介绍双分晶格概念，然后写出变换。用一个box解释一下第二节的结论是否成立。然后开始讨论为什么不改变动能：方法是转换到动量空间，具体计算一下（如有必要可以用box囊括过程）

第四节讲一下这一变换如何联系不同参数的模型（要求清晰梳理）



第三章讲解Pairing 与反铁磁（Antiferromagnetism）的对应关系

第一节吸引相互作用、等自旋数的 FHM，讲解为什么配对序参量出现（或许你需要做一些物理的argue，回顾BCS啥的); 为什么也被成为CDW，要给出物理原因

第二节讲解排斥半填充模型如何从particle–hole transformation得到。解释序参量的变化（反铁磁序/自旋序，要解释清楚含义），并用box具体给出推导

第三节简单谈论一下U(1)简并

第四节具体讲解为什么弱耦合极限下，任意小的相互作用也能诱导有序



第四章讲解转变温度

第一节讲解弱耦合区间

第二节讨论强耦合、排斥区域。用具体的微扰过程推导出Heisenberg model （如果你觉得正文太长可以写一个box）。进而解释温标

第三节通过mapping可以仔细讨论吸引侧的行为。



第五章讲讲SO(4) 对称性。。。。



第六章简单聊聊未解问题，主要是物理图像





appendix A讲解Pauli矩阵与SU（2）对称性

你需要包括的内容有Pauli 矩阵完备关系、旋量表示下的生成元S等内容





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

\title{XXXXXXXXX}
\author{Tristan.W}
\begin{document}
\maketitle

\newtcolorbox{mdframed}{
  enhanced,
  breakable,
  colback=gray!5,
  colframe=black,
  boxrule=1.6pt,
  arc=1.5mm,
  left=2mm,right=2mm,top=1.2mm,bottom=1.2mm
}

\newcommand{\keypoint}[1]{\par\medskip\noindent\textbf{#1.}\ }
\newcommand{\squarepoint}[1]{\par\medskip\noindent$\blacksquare$\ \textbf{#1.}\ }

\begin{figure}[htbp]
  \centering
  \includegraphics[width=0.7\textwidth]{XXXXX.png}
  \label{fig:example}
\end{figure}

\newpage

\tableofcontents
\newpage
```

正文内容写在 `\maketitle` 之后。

注：\keypoint命令可以用于标出小节里新的一段内容（如果和前文有鲜明的话题递进或者转移）；\squarepoint用于标出具有明显并列关系的内容

\mybox用于标出重要的注解以及细节的补充步骤（这些步骤可能比较技术性以至于影响正文的连贯），而\mdframed用于标出重要结论（别写出重要结论这几个字）

### 数学公式规范（必须遵守）

- 行内公式：使用 `\( ... \)`

- 行间公式：

  - 如需编号，使用：

    ```latex
    \begin{equation}
    ...
    \end{equation}
    ```

- label可以很好串联上下文

- **不要使用 `$$ ... $$`**

- 符号定义必须清楚，避免“默认读者知道”

### 结构要求（Section / Subsection）

- 使用 `\section{}`，从而实现编号为 **1, 2, 3, ...**

- 使用 `\subsection{}`，从而编号为 **1.1, 1.2, 2.1, ...**

- Subsection 内部如果存在明显的**层次、视角、逻辑切换**，需要另起段落（并根据情况添加keypoint或者squarepoint）；不允许私自添加小节









