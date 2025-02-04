---
title: definable class in a fibration
taxon: Definition
macrolib: topos
packages: jon-tikz
---

Let $E$ be a cartesian fibration over $B$. A *definable class*
$\mathfrak{F}$ in $E$ is a stable subcollection of the displayed objects of $E$
such that for any $\bar{u}\in E\Sub{u}$, there exists a cartesian map $\bar{v}\to \bar{u}$ lying over a monomorphism $v\rightarrowtail u$ such that $\bar{v}\in \mathfrak{F}$ and, moreover, any cartesian morphism $\bar{w}\to\bar{u}$ such that $\bar{w}\in\mathfrak{F}$ factors through $\bar{v}\to\bar{u}$.
```latex
  \DiagramSquare{
    height = 1.5cm,
    west/style = lies over,
    east/style = lies over,
    nw/style = pullback,
    south/style = {exists,>->},
    north/style = {->,exists},
    nw = \bar{v}\in\mathfrak{F},
    ne = \bar{u},
    se = u,
    sw = v,
  }
  \qquad
  \begin{tikzpicture}[diagram,baseline=(l/sw.base)]
    \SpliceDiagramSquare<l/>{
      height = 1.5cm,
      width = 2.25cm,
      west/style = lies over,
      east/style = lies over,
      ne/style = pullback,
      nw = \bar{w}\in\mathfrak{F},
      sw = w,
      ne = \bar{v},
      se = v,
      south/style = {->,exists},
      north/style = {->,exists},
      south = \exists!,
      north = \exists!,
      north/node/style = upright desc,
    }
    \SpliceDiagramSquare<r/>{
      height = 1.5cm,
      glue = west,
      glue target = l/,
      east/style = lies over,
      south/style = >->,
      ne = \bar{u},
      se = u,
    }
    \draw[->,bend left=30] (l/nw) to node [above] {cart.} (r/ne);
  \end{tikzpicture}
```
