---
taxon: Lemma
macrolib: topos
packages: jon-tikz
title: globally small externalization
---

The {{<cref frct-001R "externalization">}} is globally small

{{%proof%}}
We may choose a {{<cref frct-000K "generic object">}} for $\brk{C}$, namely the identity element $(C\Sub{0},\Idn{C\Sub{0}})\in \TotCat{\brk{C}}$. Given any object $(x,u)\in \TotCat{\brk{C}}$ the cartesian map $(x,u)\to (C\Sub{0},\Idn{C\Sub{0}})$ is given as follows:
```latex
\begin{tikzpicture}[diagram]
  \node (x) {$x$};
  \node (y) [below = of x] {$C\Sub{0}$};
  \node (C/1) [right = of x] {$C\Sub{1}$};
  \node (C/0) [below = of C/1] {$C\Sub{0}$};
  \node (C/0') [above = of C/1] {$C\Sub{0}$};
  \draw[->] (x) to node [upright desc] {$\Con{idn}\Sub{u}$} (C/1);
  \draw[->] (C/1) to node [right] {$t$} (C/0);
  \draw[->] (C/1) to node [right] {$s$} (C/0');
  \draw[->] (y) to node [below] {$\Idn{C\Sub{0}}$} (C/0);
  \draw[->] (x) to node [left] {$u$} (y);
  \draw[->] (x) to node [sloped,above] {$u$} (C/0');
\end{tikzpicture}
```
{{%/proof%}}
