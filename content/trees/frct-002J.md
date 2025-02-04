---
title: full subfibrations and figure shapes
macrolib: topos
---

In a category $E$, a morphism $f : x\to y$ can be thought of as a "figure"
of shape $x$ drawn in $y$. For instance, if $x$ is the point (i.e.
$x=\ObjTerm{E}$) then a morphism $x\to y$ is a "point" of the "space" $y$.
We refer to $x$ as the figure-shape in any such scenario.
The perspective of morphisms as figures is developed in more detail by Lawvere and Schanuel.

It often happens that a useful class of figure shapes can be arranged
into a *set*-indexed family $\prn{u\Sub{i}}\Sub{i\in I}$; viewed from the
perspective of the family fibration $\FAM{E}$ ({{<cref frct-0006>}}), this family is just a
displayed object $\bar{u}$ over $I$ and then a figure shape "in"
this family is given by any cartesian morphism $\bar{z}\to\bar{u}$. We will
generalize this situation to the case of an arbitrary fibration, by
constructing the full subfibration spanned by displayed objects equipped
with a cartesian morphism into $\bar{u}$ in {{<cref frct-0010>}} below.

{{<child frct-0010>}}
{{<child frct-002K>}}
