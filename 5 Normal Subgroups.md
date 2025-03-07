#! https://zhuanlan.zhihu.com/p/691560340
# Notes on Abstract Algebra 5

# Chapter 2: Groups

### V Normal Subgroups

Consider $\varphi = sgn:S_3\to \{\pm1\}^{\times}$. (Notation as $x = (1,2,3)$ and $y = (1,2)$)
$K = \ker \varphi = \{1,(1,2,3),(1,3,2)\}\mapsto 1$. $yK = \{(1,2),(1,3),(2,3)\}\mapsto -1$.

Question: Can we use the "right coset" of $K = \ker \varphi$ to describe fibers of $\varphi$?

A naive trial: $Ky = \{(1,2),(1,3),(2,3)\} = yK$. $\forall k\in K, \exists k'\in K,$ s.t. $yK = k'y$.
For $K=\ker \varphi$, we have $Ky = yK$. (Reason: $\forall k\in K,\exists k'\in K$ s.t. $yk = k'y$ i.e. $\forall k \in K, yky^{-1}\in K$.)

Definition: We say $N\leq G$ is a normal subgroup ($N\trianglelefteq  G$) if $\forall a \in N \forall g \in G, gag^{-1}\in N$. $gag^{-1}$ are called conjugate of $a$ by $g$.

Proposition: $\forall \varphi: G\to G'$ which is a group homomorphism, $\ker\varphi$ is a normal subgroup of $G$.

Proof: $\ker \varphi\leq G$ is obvious. And $\forall k\in K = \ker \varphi, g\in G,\varphi(gkg^{-1}) = \varphi(g)\varphi(k)\varphi(g^{-1}) = \varphi(g)1_G\varphi(g)^{-1} = 1_G$, which implies $gkg^{-1}\in K$.

Some examples of normal subgroups:

- $SL_n(\mathbb R)\trianglelefteq GL_n(\mathbb R)$. ($SL_n(\mathbb R) =\ker \det$).
- $A_n \trianglelefteq S_n(A_n = \ker \text{sgn})$.

Insight: Every kernel is a normal subgroup. What about the inverse "Every normal subgroup is a kernel."?

If $G$ is abelian, $H\leq G\Rightarrow H\trianglelefteq G$ since $ghg^{-1} = gg^{-1}h = h\in H$.

A counter example of normal subgroup: $\{1,(12)\}\leq S_3$, but $(1 2 3)(1 2)(123)^{-1} = (2 3)\not \in \{1,(12)\}$.

Another normal subgroup of a group $G$: The center of $G$ (always denoted as $Z$) is defined as $Z(G) = \{z\in G|\forall g\in G,zg = gz\}$ i.e. elements in $Z(G)$ is commutative for every element in $G$.

Proposition: $Z(G)$ is a normal subgroup of $G$ since $\forall z\in Z(G), \forall g\in G,gzg^{-1} = zgg^{-1}=z\in Z(G)$.

Example: $Z(GL_n(\mathbb R)) = \{\lambda I|\lambda\in \mathbb R^*\}$, $Z(S_3) = \{1\}$. (In fact, $Z(S_n)(n\geq 3) = \{1\}$).

Another way to describe the "commutative level" of two elements $a,b$ is the commutator, defined as $aba^{-1} b^{-1}$. $ab = ba$ if and only if $aba^{-1} b^{-1}=1$.

Remark: The conjugate :$\varphi_g: G\to G,\varphi(a) = gag^{-1}$ is an automorphism (an isomorphism from $G$ to $G$ self).

- $\varphi_g$ is a homorphism ($\varphi_g(x)\varphi_g(y) = gxg^{-1}gyg^{-1} = g(xy)g^{-1} = \varphi_g(xy)$)
- $\varphi_g$ has a inverse $\varphi_g^{-1}$: $\varphi_g^{-1}(x) = g^{-1}xg$ ($\varphi_g\circ \varphi_g^{-1} = \varphi_g^{-1}\circ \varphi_g = i$) so $\varphi_g$ is bijective.

Fibers as equivalent classes:
$\varphi: G\to G'$ is a group homomorphism. $K=\ker\varphi \trianglelefteq G$. Consider the mapping. Observe that:

- $G= \bigsqcup(\text{disjoint})$(nonempty) fibers of $\varphi$ (a partition): $\{\text{(nonempty) fibers of }\varphi\}\overset{\text{bijection}}{\longleftrightarrow}\text{im } \varphi$.
- The fibers over $\varphi(a) = aK$, $|aK| = |K|$.

Recall how to define an equivalence relation: A relation $R\subset S\times S$ is an equivalence relation if it satisfies:

- Reflexive: $aRa$
- Symmetric: $aRb\Rightarrow bRa$
- Transitive: $aRb,bRc\Rightarrow aRc$.

$\sim$ is an equivalence relation on $S$ and $a\in S$. The equivalence class of $a$: $\bar a = \{b\in S| b\sim a\}$, $a$ is called the representative of this class.

Lemma: Either $\bar a = \bar b$, or $\bar a \cap \bar b = \emptyset$.

Prove: If $c \in \bar a \cap \bar b$, $\forall x\in \bar a, x\sim b$ since $x\sim c, c\sim b$. Similarly for $\forall x \in \bar b, x\sim a$.

Proposition: An equivalence relation on $S$ determines a partition on $S$, and vice versa, i.e. $S = \bigsqcup_\lambda S_\lambda, S_\lambda \subset S$.

Proof: ($\Rightarrow$) $S  = \bigsqcup_{a\in S} \bar a$. (Note that the disjoint union $\bigsqcup$ here won't contain the same set twice.)
($\Leftarrow$) Define $\sim$: $a\sim b$ if $a,b\in S_{\lambda_0}$ for some $\lambda_0$ i.e. in the same subeset.

Define $\bar S = S/\sim$ by $\bar S=\{\bar a| a\in S\}$ (quotient set). Call $\pi:S\to \bar S(a\mapsto \bar a)$ a quotient map.

Insight: Quotient set implies the definitions of quotient-like items i.e. quotient space. Similarly to quotient space from subspaces, we can define quotient groups from subgroups. Then the equivalence on normal subgroups is obvious.

Example: Define an equivalence relation from a mapping $f: S\to T$. $s_1\sim s_2$ if and only if $f(s_1) = f(s_2)$. (Recall the quotient map: mapping the elements to its subset. In this point of view, $T$ of the quotient map is actually the set of equivalence classes.) Furthermore, the fiber of $f(S)$ is defined as $f^{-1}(f(S))$ (all the preimage of $f(S)$).

Come back to left cosets: $H\leq G$, define $a\underset{\text{Congruent}}{\equiv} b$ if and only if $b = ah$ for some $h\in H$.
Lemma: $\equiv$ is an equivalence relation.
Proof: The $3$ properties of subgroups imply the $3$ requirements of equivalence relations.

- Indentity $\to$ Reflexive: $1\in H, a = 1a\Rightarrow a\equiv a$.
- Inverse $\to$ Symmetric: $b=ah\Rightarrow a = bh^{-1}$, $h\in H\Rightarrow h^{-1}$.
- Closure $\to$ Transitive: $b = ah, c = bh'\Rightarrow c = a(hh')$, $h\in H,h'\in H\Rightarrow hh'\in H$.

Corollary: Either $aH=bH$, or $aH\cap bH = \emptyset$.
