---
taxon: Lemma
title: characterization of definable classes of families
macrolib: topos
---

Let $\mathfrak{C}\subseteq\mathscr{M}$ be a class of sets; then $\bar{\mathfrak{C}}$ is a definable class of families of sets if and only if $\mathfrak{C}$ is a definable class of sets.

{{%proof%}}
Suppose that $\mathfrak{C}$ is a definable class of sets. To
check that $\bar{\mathfrak{C}}$ is a definable class of families of sets,
we fix a family $\prn{S\Sub{i}}\Sub{i\in I}$ not necessarily lying in $\bar{\mathfrak{C}}$. Because $\mathfrak{C}$ is definable, the intersection $\mathfrak{C}\cap \bigcup\Sub{i\in I}S\Sub{i}$ is represented by a set $U$. We therefore take the subset $J = \brc{i \in I\mid S_i\in U}\subseteq I$, and verify that the base change $\prn{S\Sub{j}}\Sub{j\in J}$ is the largest approximation of $\prn{S\Sub{i}}\Sub{i\in I}$ by a family lying in $\bar{\mathfrak{C}}$.

Conversely suppose that $\bar{\mathfrak{C}}$ is a definable class of families of sets. To see that $\mathfrak{C}$ is definable, we fix a class $\mathfrak{U}$ represented by a set $U\in\mathscr{M}$ to check that $\mathfrak{C}\cap\mathfrak{U}$ is representable. We consider the family of sets $\prn{u}\Sub{u\in U}$; because $\bar{\mathfrak{C}}$ is definable, there is a largest subset $V\subseteq U$ such that the change of base $\prn{v}\Sub{v\in V}$ lies in $\bar{\mathfrak{C}}$, i.e. such that each $v\in V$ lies in $\mathfrak{C}$. Therefore $\mathfrak{C}\cap\mathfrak{U}$ is represented by the set $V$.
{{%/proof%}}
