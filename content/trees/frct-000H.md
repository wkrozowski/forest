---
title: a more abstract formulation of locally small family fibrations
macrolib: topos
packages: jon-tikz
---

We will reformulate the local smallness property of the family fibration in a way that uses only the language that makes
sense for an arbitrary cartesian fibration, though for now we stick with $\FAM{C}$. Given
$u,v\in \FAM{C}[I]$, we have a "relative hom family" $[u,v]\in\Sl{\SET}{I}$,
defined in {{<cref frct-000G>}}. The fact that each $[u,v]\Sub{i}$ is the set of all
morphisms $u\Sub{i}\to v\Sub{i}$ can be rephrased more abstractly.

First we consider the restriction of $u\in \FAM{C}[I]$ to $\FAM{C}[[u,v]]$ as follows:
```latex
\DiagramSquare{
  nw/style = pullback,
  west/style = lies over,
  east/style = lies over,
  north/style = {->,exists},
  height = 1.5cm,
  nw = \InvImg{[u,v]}u,
  ne = u,
  sw = {[u,v]},
  se = I,
  south = p\Sub{[u,v]},
  north = \bar{p}\Sub{[u,v]}
}
```

Explicitly the family $\InvImg{[u,v]}u$ is indexed in a pair of an element $i\in I$ and a morphism $u\Sub{i}\to v\Sub{i}$.
We can think of $\InvImg{[u,v]}u$ as the object of elements of $u\Sub{i}$ indexed in pairs $(i,u\Sub{i}\to v\Sub{i})$.

There is a canonical map
$\epsilon\Sub{[u,v]}:\InvImg{[u,v]}u\to\Sub{p\Sub{[u,v]}} v$ that
"evaluates" each indexing morphism $u\Sub{i}\to v\Sub{i}$.

That each $[u,v]\Sub{i}$ is the set of all morphisms $u\Sub{i}\to v\Sub{i}$ can be
rephrased as a universal property: for any family $h\in\Sl{\SET}{I}$ and
morphism $\epsilon\Sub{h} : \InvImg{h}u\to\Sub{h} v$ in $\FAM{C}$, there is a
unique cartesian map $\InvImg{h}u\to \InvImg{[u,v]}u$ factoring $\epsilon\Sub{h}$ through $\epsilon\Sub{[u,v]}$
in the sense depicted below:

```latex
\begin{tikzpicture}[diagram]
  \SpliceDiagramSquare{
    height = 1.5cm,
    width = 3cm,
    west/style = lies over,
    east/style = lies over,
    north/node/style = upright desc,
    south/node/style = upright desc,
    nw = \InvImg{[u,v]}u,
    ne = v,
    sw = {[u,v]},
    se = I,
    south = p\Sub{[u,v]},
    north = \epsilon\Sub{[u,v]},
  }
  \node (h/u) [pullback,left = of nw] {$\InvImg{h}u$};
  \node (h) [left = of sw] {$h$};
  \draw[bend left,->] (h/u) to node [sloped,above] {$\epsilon\Sub{h}$} (ne);
  \draw[lies over] (h/u) to (h);
  \draw[->,exists] (h) to (sw);
  \draw[->,exists] (h/u) to (nw);
  \draw[->,bend right=30] (h) to node [below] {$p\Sub{h}$} (se);
\end{tikzpicture}
```

To convince ourselves of this, we note that the family $H \coloneqq \brc{u\Sub{i}\to v\Sub{i}}\Sub{i\in I}$ itself satisfies the universal property above. Indeed, fix a candidate $h \in \Sl{\SET}{I}$ equipped with a map $\epsilon\Sub{h} : \InvImg{h}u \to_h v$. Unfolding the meaning of this map in set theoretical notation, we see that it amounts to a family of maps $\epsilon\Sub{h}[i] : \prod\Sub{x\in h_i} \brc{u_i\to v_i}$ for each $i\in I$; such a family immediately induces the desired map $h\to H$.
