---
taxon: Lemma
macrolib: topos
packages: jon-tikz
title: locally small externalization
---

The {{<cref frct-001R "externalization">}} is locally small.

{{%proof%}}
Fix $x\in E$ and $u,v\in
\brk{C}\Sub{x}$, we must exhibit a terminal object to the (total) category
$\TotCat{\CandHom{x}{u}{v}}$ of "hom candidates" defined in {{<cref frct-000I>}}.
First we define $\brk{u,v}$ to be the following pullback in $E$:
```latex
\DiagramSquare{
  nw/style = pullback,
  ne = C\Sub{1},
  se = C\Sub{0}\times C\Sub{0},
  east = {(s,t)},
  south = {(u,v)},
  sw = x,
  nw = \brk{u,v},
  west = p,
  north = q,
  west/style = {->,exists},
  north/style = {->,exists},
}
```

We define $\overline{p}:\InvImg{\brk{u,v}}{u}\to\Sub{p} u\in \brk{C}\Sub{\brk{u,v}}$ to be
the cartesian lift of $u\in \brk{C}\Sub{x}$ along $p:\brk{u,v}\to x$:
```latex
\DiagramSquare{
  height = 1.5cm,
  nw/style = pullback,
  west/style = lies over,
  east/style = lies over,
  north/style = {->,exists},
  ne = u,
  nw = \InvImg{\brk{u,v}}u,
  sw = \brk{u,v},
  se = x,
  south = p,
  north = \overline{p},
}
```

We need to define a displayed evaluation map
$\epsilon : \InvImg{\brk{u,v}}u\to\Sub{p} v$; unraveling the definition of a displayed
morphism in the externalization of $C$, we choose the following diagram:

```latex
  \begin{tikzpicture}[diagram]
    \SpliceDiagramSquare{
      ne = C\Sub{1},
      se = C\Sub{0},
      east = t,
      nw = \brk{u,v},
      sw = x,
      west = p,
      south = v,
      north = q,
      north/style = {magenta,->},
      north/node/style = upright desc,
    }
    \node (nne) [above = of ne] {$C\Sub{0}$};
    \node (nnw) [above = of nw] {$x$};
    \draw[->] (ne) to node [right] {$s$} (nne);
    \draw[->] (nw) to node [left] {$p$} (nnw);
    \draw[->] (nnw) to node [above] {$u$} (nne);
    \draw[->] (nw) to node [desc] {$\InvImg{\brk{u,v}}{u}$} (nne);
  \end{tikzpicture}
```


Putting all this together, we assert that the terminal object of
$\TotCat{\CandHom{x}{u}{v}}$ is the following span in $\brk{C}$:
```latex
\begin{tikzpicture}[diagram]
\SpliceDiagramSquare<l/>{
  height = 1.5cm,
  west/style = lies over,
  east/style = lies over,
  north/style = <-,
  south/style = <-,
  ne/style = ne pullback,
  ne = \InvImg{\brk{u,v}}{u},
  se = \brk{u,v},
  sw = x,
  nw = u,
  south = p,
  north = \bar{p},
}
\SpliceDiagramSquare<r/>{
  height = 1.5cm,
  west/style = lies over,
  east/style = lies over,
  glue = west,
  glue target = l/,
  ne = v,
  se = x,
  north = \epsilon,
  south = p,
}
\end{tikzpicture}
```

Fixing another such candidate hom span $\brc{u \leftarrow \bar{h}\rightarrow v}\in\TotCat{\CandHom{x}{u}{v}}$, according to {{<cref frct-000I>}} we must exhibit a unique cartesian morphism $\bar\alpha : \bar{h}\to \InvImg{\brk{u,v}}{u}$ making the following diagram commute:
   ```latex
   \begin{tikzpicture}[diagram]
     \node (u) {$u$};
     \node (h) [above right = 1.5cm of u,xshift=.5cm] {$\bar{h}$};
     \node (hom) [below right = 1.5cm of u,xshift=.5cm] {$\InvImg{\brk{u,v}}{u}$};
     \node (v) [below right = 1.5cm of h,xshift=.5cm] {$v$};
     \draw[->] (hom) to node [sloped,below] {$\bar{p}$} (u);
     \draw[->] (h) to node [sloped,above] {$\bar{p}\Sub{h}$} (u);
     \draw[->] (hom) to node [sloped,below] {$\epsilon$} (v);
     \draw[->] (h) to node [sloped,above] {$\epsilon\Sub{h}$} (v);
     \draw[->] (h) to node [upright desc] {$\bar\alpha$} (hom);
   \end{tikzpicture}
   ```

First we note that the evaluation map $\epsilon\Sub{h} : \bar{h}\to v$ amounts
to an internal morphism $h\to C\Sub{1}$ satisfying the appropriate
compatibility conditions. Therefore we may define the base $\alpha:h\to \brk{u,v}$ of
the universal map using the universal property of the pullback that defines $\brk{u,v}$:
```latex
\begin{tikzpicture}[diagram]
  \SpliceDiagramSquare{
    nw/style = pullback,
    ne = C\Sub{1},
    se = C\Sub{0}\times C\Sub{0},
    east = {(s,t)},
    south = {(u,v)},
    sw = x,
    nw = \brk{u,v},
    west = p,
    north = q,
    north/node/style = upright desc,
    west/node/style = upright desc,
  }
  \node (h) [above left = of nw] {$h$};
  \draw[->,bend right=30] (h) to node [left] {$p_h$} (sw);
  \draw[->,bend left=30] (h) to node [sloped,above] {$\epsilon_h$} (ne);
  \draw[->,exists] (h) to node [desc] {$\alpha$} (nw);
\end{tikzpicture}
```

The morphism $\alpha:h\to \brk{u,v}$ defined above is the *unique* map in $E$
satisfying the conditions required of the base for $\bar\alpha$; therefore, it
suffices to show that there exists a cartesian morphism
$\bar\alpha:\bar{h}\to\Sub{\alpha}\InvImg{\brk{u,v}}u$ since it will be unique if it
exists. We define $\bar\alpha$ using the universal property of the cartesian lift:
```latex
\begin{tikzpicture}[diagram]
  \SpliceDiagramSquare<l/>{
    ne/style = pullback,
    nw/style = dotted pullback,
    west/style = lies over,
    east/style = lies over,
    height = 1.5cm,
    se = \brk{u,v},
    ne = \InvImg{\brk{u,v}}u,
    sw = h,
    nw = \bar{h},
    south = \alpha,
    north = \bar\alpha,
    north/style = {->,exists},
    north/node/style = upright desc,
    south/node/style = upright desc,
  }
  \SpliceDiagramSquare<r/>{
    glue = west,
    glue target = l/,
    east/style = lies over,
    height = 1.5cm,
    ne = u,
    se = x,
    south = p,
    north = \bar{p},
    north/node/style = upright desc,
    south/node/style = upright desc,
  }
  \draw[->,bend left=30] (l/nw) to node [above] {$\bar{p}\Sub{h}$} (r/ne);
  \draw[->,bend right=30] (l/sw) to node [below] {$p\Sub{h}$} (r/se);
\end{tikzpicture}
```

That $\bar{\alpha}:\bar{h}\to\Sub{\alpha}\InvImg{\brk{u,v}}u$ is cartesian follows from {{<cref frct-0014 "the generalized pullback lemma for cartesian morphisms">}}: it suffices
to observe that both $\bar{p}\Sub{h}:\bar{h}\to u$ and its second factor
$\bar{p}:\InvImg{\brk{u,v}}u\to u$ are cartesian.
{{%/proof%}}
