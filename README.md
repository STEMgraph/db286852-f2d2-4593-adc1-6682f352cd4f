<!---
{
  "id": "db286852-f2d2-4593-adc1-6682f352cd4f",
  "depends_on": [
    "AND",
    "66726805-4497-4dce-a1ba-ccf930a721f8",
    "11830a64-a50f-461e-8379-ae9511768cc4",
    "2d349b37-ef59-4353-87e2-33896c7d0064",
    "fc36b61a-a948-4971-87b1-dcf98a1c5d80",
    "71450eb9-b69b-45e9-8a43-8bc0fae963d1"
  ],
  "author": "Exercise Sheet Assistant",
  "first_used": "2025-06-04",
  "keywords": ["labels", "references", "LaTeX", "figures", "tables", "environments", "math", "document hierarchy"]
}
--->

# Advanced Document Structuring: Labels and References

> In this exercise you will learn how to correctly use labels and references to connect figures, tables, mathematical formulas, and hierarchical document elements. Furthermore we will explore how to integrate these features into environments and complex document structures.

## Introduction

In professional document preparation systems like LaTeX, the ability to label elements and reference them throughout the document is crucial for producing clear, consistent, and navigable texts. Labels and references are used to ensure that figures, tables, equations, and sections can be cross-referenced dynamically. This eliminates hard-coded numbering and allows for automatic updates whenever the document structure changes.

In this exercise, you will apply your previous knowledge of inserting figures, structuring documents with sections and subsections, writing mathematical expressions, creating tables, and using environments. You will combine these skills to produce a logically structured and well-referenced document. This integrated approach is not only a powerful technical capability but also an essential skill for writing professional articles, theses, and reports.

Correct labeling involves placing a `\label{}` command after a caption or heading, while referencing uses the `\ref{}` or `\eqref{}` commands to insert the corresponding number or equation reference into the text. By maintaining unique and meaningful label identifiers, you create a document that is easy to maintain, expand, and review.

### Further Readings and Other Sources

* [Overleaf: Cross-referencing sections, equations and floats](https://www.overleaf.com/learn/latex/Labels_and_Cross-referencing)
* [The LaTeX Companion, 2nd Edition (DOI:10.5555/1246063)](https://doi.org/10.5555/1246063)
* [LaTeX Wikibook: Labels and Cross-referencing](https://en.wikibooks.org/wiki/LaTeX/Labels_and_Cross-referencing)

## Tasks

### Project Setup

For this exercise, you will organize your project using the following structure:

```
./
├── figures/
│   └── chart.png
└── src/
    └── main.tex
```

Download the required figure using the following command from your project root directory:

```bash
mkdir -p figures
curl -o figures/chart.png https://raw.githubusercontent.com/STEMgraph/db286852-f2d2-4593-adc1-6682f352cd4f/refs/heads/master/assets/chart.png
```

You will compile your document by running:

```bash
pdflatex ./src/main.tex
```

### Task 1: Create a Document Structure with Labels

1. In `./src/main.tex`, start a new document with `\documentclass{article}`.
2. Insert a title, author, and date.
3. Create the following structure:

```latex
\section{Introduction}\label{sec:introduction}

\section{Theory}\label{sec:theory}
\subsection{Mathematical Background}\label{subsec:math}
\subsection{Illustrations}\label{subsec:illustrations}

\section{Results}\label{sec:results}
\subsection{Data Tables}\label{subsec:tables}
\subsection{Discussion}\label{subsec:discussion}

\section{Conclusion}\label{sec:conclusion}
```

### Task 2: Insert a Labeled Equation

In section \ref{sec\:theory}, subsection \ref{subsec\:math}, insert the following formula for the quadratic equation and label it:

```latex
\begin{equation}\label{eq:quadratic}
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
\end{equation}
```

Then refer to this equation in the text as:

```latex
As shown in Equation~\eqref{eq:quadratic}, the solutions depend on the discriminant.
```

### Task 3: Insert and Label a Figure

In subsection \ref{subsec\:illustrations}, insert the downloaded chart:

```latex
\begin{figure}[h]
    \centering
    \includegraphics[width=0.5\textwidth]{../figures/chart.png}
    \caption{Graph of the quadratic function.}
    \label{fig:quadratic_graph}
\end{figure}
```

Refer to the figure in your text using:

```latex
See Figure~\ref{fig:quadratic_graph} for a visualization.
```

### Task 4: Insert and Label a Table

In subsection \ref{subsec\:tables}, create a table summarizing discriminant values:

```latex
\begin{table}[h]
    \centering
    \begin{tabular}{|c|c|}
        \hline
        Discriminant & Nature of Roots \\
        \hline
        $> 0$ & Two real roots \\
        $= 0$ & One real root \\
        $< 0$ & Two complex roots \\
        \hline
    \end{tabular}
    \caption{Root classification based on the discriminant.}
    \label{tab:discriminant}
\end{table}
```

Reference the table as:

```latex
Table~\ref{tab:discriminant} summarizes these cases.
```

### Task 5: Use Labeled Environments

Create a custom theorem environment using `amsthm` package, and insert a labeled theorem in subsection \ref{subsec\:discussion}:

```latex
\usepackage{amsthm}
\newtheorem{theorem}{Theorem}

\begin{theorem}\label{thm:real_roots}
If the discriminant $D > 0$, then the quadratic equation has two distinct real roots.
\end{theorem}
```

Refer to the theorem in your text using:

```latex
Theorem~\ref{thm:real_roots} formally states this result.
```

## Questions

1. What happens if you change the order of sections or figures? Do you need to update any reference numbers manually?
2. What is the difference between `\ref{}` and `\eqref{}`?
3. Why is it good practice to prefix labels with categories like `sec:`, `fig:`, `eq:`, etc.?
4. How can labeled environments improve clarity in mathematical texts?
5. What happens if two elements accidentally share the same label?

## Advice

Mastering labels and references is one of the most effective ways to create professional, scalable documents. By building on your earlier work on inserting figures, writing math, creating tables, defining document hierarchy, and using environments, you now have the tools to produce fully cross-referenced texts that are easy to maintain. Always check that your labels are unique and descriptive. If you're uncertain, review the foundational sheets on [Inserting Figures](66726805-4497-4dce-a1ba-ccf930a721f8), [Document Hierarchy](11830a64-a50f-461e-8379-ae9511768cc4), [Writing Math](2d349b37-ef59-4353-87e2-33896c7d0064), [Tables](fc36b61a-a948-4971-87b1-dcf98a1c5d80), and [Environments](71450eb9-b69b-45e9-8a43-8bc0fae963d1). With consistent practice, your technical writing will become both more readable and more robust.
