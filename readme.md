# LaTeX 示例文档使用说明

本 `README.md` 介绍了如何使用 LaTeX 编写学术论文，包括章节的创建、图片与表格的插入、数学公式的使用，以及文献引用的方法。

## 1. 文档结构

示例 LaTeX 文件的基本结构如下：

```latex
\documentclass{article}
\usepackage{ctex}  % 自动支持中文
\usepackage{geometry}
\geometry{a4paper, margin=1in}

\usepackage{graphicx}  
\usepackage{booktabs}    
\usepackage{cite}

\bibliographystyle{plain}
```

- `\documentclass{article}` 指定了文档类型为 `article`。
- `\usepackage{ctex}` 让 LaTeX 支持中文。
- `\usepackage{geometry}` 用于设置页面格式。
- `\usepackage{graphicx}` 允许插入图片。
- `\usepackage{booktabs}` 用于美化表格。
- `\usepackage{cite}` 用于引用参考文献。
- `\bibliographystyle{plain}` 指定了参考文献的样式。

## 2. 章节的使用

使用 `\section{}` 定义章节，例如：

```latex
\section{引言}
这是引言部分。
```

## 3. 插入表格

可以使用 `tabular` 环境创建表格，例如：

```latex
\begin{table}[hbt]
    \centering
    \caption{MobileNetV4-Conv-L 特征层的尺寸和通道数}
    \label{tab:feature_map_sizes}
    \begin{tabular*}{0.75\textwidth}{@{\extracolsep{\fill}}ccc}
    \toprule
      特征层 & 尺寸 & 通道数 \\
    \midrule
      \(\times2\)  & \(H/2 \times W/2\)   & 24 \\
      \(\times4\)  & \(H/4 \times W/4\)   & 48 \\
      \(\times8\)  & \(H/8 \times W/8\)   & 96 \\
      \(\times16\) & \(H/16 \times W/16\) & 192 \\
      \(\times32\) & \(H/32 \times W/32\) & 960 \\
    \bottomrule
    \end{tabular*}
\end{table}
```

- `\caption{}` 设置表格标题。
- `\label{}` 给表格一个唯一标识符，以便在正文中引用，例如 `表 \ref{tab:feature_map_sizes}`。

## 4. 插入图片

使用 `\includegraphics{}` 插入图片，例如：

```latex
\begin{figure}[hbt]
    \centering
    \includegraphics[width=0.5\textwidth]{figures/seg.png}
    \caption{深度估计-语义分割联合网络框架}
    \label{fig:basenetwork}
\end{figure}
```

- `\includegraphics[width=0.5\textwidth]{figures/seg.png}` 指定图片路径并设置宽度。
- `\caption{}` 为图片添加说明。
- `\label{}` 给图片一个唯一标识符，以便引用，例如 `图 \ref{fig:basenetwork}`。

## 5. 数学公式

数学公式可以使用 `$...$` 或 `\[ ... \]` 语法，例如：

- 行内公式：`$E=mc^2$` 显示为 \$E=mc^2\$。
- 独立公式：

```latex
\[
   y = ax^2 + bx + c
\]
```

## 6. 参考文献引用

使用 `\cite{}` 在文中引用文献，例如：

```latex
你可以引用文献，例如 \cite{zhao2024autonomous}。
```

文献列表通常存储在 `.bib` 文件中，例如 `main.bib`，并在文档末尾添加：

```latex
\bibliography{main}
```

## 7. 编译 LaTeX 文档

建议使用 `pdflatex` 和 `bibtex` 进行编译：

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

这样可以正确生成参考文献。

---

以上是本 LaTeX 示例文档的使用说明，希望对你有所帮助！
