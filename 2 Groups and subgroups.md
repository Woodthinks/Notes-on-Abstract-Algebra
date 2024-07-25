#! https://zhuanlan.zhihu.com/p/685085725
# Notes on Abstract Algebra 2

# Chapter 2: Groups

### II Groups and subgroups

Consider some algebraic structures:
$F$ is a field, $GL_n(F) = \{n\times n \text{ invertible matrices }A\text{ with entries in }F\}$, with matrix multiplication $(A, B)\mapsto AB$ as the law of composition. $(GL_n(F),\times)$ forms a group. Usually, the group is called a $n\times n$ *general linear group*.

Take any set $T$, and consider bijective mappings from $T$ to $T$ i.e. operators on $T$. Recall that bijective mappings have inverses. Then $(\{f:T\to T|f\text{ is bijective}\},\circ)$ forms a group, called permutation group of $T$.

More specifically, when $T = \{1,2,\cdots,n\}$, the permutation group of $T$ is called the *symmetric group*, denoted by $S_n$.
That is:
$$ S_n \text{ is the group of permutations of the indices }\textbf{1,2,}\cdots\textbf{,n} $$

An obvious property is $|S_n| = n!$ since there are $n!$ permutations for a set of $n$ elements.

The most basic symmetric group is $S_2$ (because $S_1$ is not meaningful). It contains $2$ elements, one is the identity and another is the transposition (denoted as $x$ here). Because there are $2$ elements in $S_2$ and $x^2\not = x$ due to the cancellation law. So $x^2 = 1$ which can be verified by definition. Here is the production table of $S_2$:

| $\times$ | $1$  | $x$  |
|------------|----|----|
| $1 $         | $1$  | $x$  |
| $x$          | $x$  | $1$|

Before we talk about $S_3$ and other symmetric groups, let us clarify some notations for permutations.

A *permutation* of a set $S$ a bijective map $p$ from a set $S$ to itself. We can use a table to represent it, for example:
| $i$   | $1$ | $2$ | $3$ | $4$ | $5$ |
|-------|-----|-----|-----|-----|-----|
| $p(i)$| $3$ | $5$ | $4$ | $1$ | $2$ |

The table notation is complicated and time-consuming when writing. Here we introduce another representation method: cycle notation.
Notation $(a_1a_2\cdots a_m)(m\leq n)$ indicates a mapping $f$, that 
$$f(i)=
\left\{
    \begin{aligned}
    a_{j+1} &  & i=a_j(j< m) \\
    a_1 & & i=a_m \\
    i & & \text{otherwise}
    \end{aligned}
\right.$$
They compose as the rules of mapping composition. For example ${(1452)(351)(25)}={(135)}$. And one mapping can be written into different cycles: $(134)=(341)$. Disjoint cycles are commutative: $(25)(134)=(134)(25)$. We also call $2-$cycles as transitions.

Then consider how to use disjoint cycles to represent permutations.
Proposition (Cycle decomposition): Any permutation in $S_n$ can be written as a product of disjoint cycles.
Proposition (Expansion of large cycles): $(a_1\cdots a_m)=(a_1a_m)(a_1a_{m-1})\cdots(a_1a_2)$.
These two propositions show that $\forall$ permutation $p\in S_n$, $p$ can be written as a product of $2-$cycles.

Note that equivalent permutations have something in common. First, we give out the definition of permutation matrices. Denote $e_{ij}$ as the matrix unit with $i,j$-th entry $1$ and others $0$. Then the permutation matrix of $p\in S_n$ is $P=\sum_{i=1}^ne_{p(i),i}$.
E.g. $p=(1,2,3)\in S_3,P = e_{21}+e_{32}+e_{13} = \begin{bmatrix}
    0 & 0 & 1 \\
    1 & 0 & 0 \\
    0 & 1 & 0 
\end{bmatrix}$
Proposition of permutation matrix: If $P$ is the permutation matrix of $p\in S_n$, $det(P)\in\{1,-1\}.$ Suppose $P, Q$ is the permutation matrix of $p,q$, then $PQ$ is the permutation matrix of $pq(p\circ q).$
The sign of permutation is defined as the determinant of the permutation matrix. Here we give out some formulas of the sign of the permutation matrix:
- $sgn(PQ) = sgn(P)sgn(Q)$.
- $sgn((a b)) =1,sgn((a b c)) = -1$.
- $sgn((a_1\cdots a_m)) = (-1)^{m-1}$.

We come back to $S_3$, the smallest group not abelian. The identity element $1$ is $i(n) = n$, the constant mapping. Denote the cyclic permutation ${(123)}$ as $x\in S_3$ and easy to verify that $x^3=1$. Note that there are $6$ elements in $S_3$, so we can't use $x^i$ to represent all elements in $S_3$. Take another element, transposition for the first elements ${(12)}$ and denote it as $y$. We can find $y^2=1$ and $yx=x^2y$. Note that $S_3$ is not abelian otherwise $xy$ will be equal to $yx$. And none of $S_n(n\geq 3)$ are abelian ($(12),(123)\in S_n(n\geq3),(12)(123)\not=(123)(12)$).

Then we can represent $S_3$ by $\{1,x,x^2,y,yx,yx^2\}$. The rules ($x^3=1,y^2=1,xy=y^2x$) together with the associative law ensure that all elements in $S_3$ can be written in the form of $x^iy^j,(0\leq x\leq2,0\leq y\leq1)$. For instance, the element $x^{-1}y^3x^2y$ can be written into:

$$x^{-1}y^3x^2y\overset{x^3=1}=x^2yx^2y=x^2(yx)xy\overset{yx=x^2y}=x^2(x^2y)xy\overset{x^3=1}=xyxy\overset{yx=x^2y}=x(x^2y)y=1.$$

We call $x$ and $y$ generators of groups $S_3$ and the rules *defining relations* since every element in $S_3$ can be written in the form of $x^iy^j$ by the rules and the associative law. Note that a group may have different generators. A naive set of generators for a group $(G,\cdot)$ is $G$, because $\forall g_i\in G,g_i = g_i^1\Rightarrow \forall g\in G, g=\prod_{i=1} g^{x_i}_i$, where $\sum_{i=1}^{|G|}x_i=1,x_i\in \mathbb{N}$.

Insight: There exist similarities between spanning vectors for vector space and generators of groups. 

Like subspaces are to vector spaces, subsets are to sets, we can define subgroups:

A subset $H$ of a group is a *subgroup* if it has the following properties:
- Closure: $\forall a,b\in H,ab\in H$.
- Indetity: $1\in H$.
- Inverses: $\forall a\in H,a^{-1}\in H$.

Then $H$ is a group with respect to the operation on $G$
Proof:
- $\forall a,b,c\in H, H\subset G\Rightarrow a,b,c\in G\Rightarrow a(bc) = (ab)c$
- $1\in H\Rightarrow \forall a\in H,\exists 1\in H, 1a=a1=a$.
- $\forall a \in H, a^{-1}\in H$ by definition.

Examples:
- The set of complex numbers of absolute value $1$ is a subgroup of $(C,\times)$.
- The group of $n\times n$ matrices with determinant $1$ is a subgroup of $GL_n(\mathbb{R})$. (Also denote the subgroup as $SL_n(\mathbb R)$, called *special linear group*).
- The set of even permutations $(A_n=\{\sigma\in S_n|sgn(\sigma)=1\})$ is a subgroup of $S_n$. (Also called alternating group.)

Insight: Why not use a more general range of matrices, like with determinant absolute value $1$? Note that $(\{x\in\mathbb C||x| =1\},\times)$ is also a group. We may "combine" these two groups to get the ones with more range. This could lead to the definition of product groups. Notice that $A_n$ can be written in a better form with $S_n$. $(A_n=\{\sigma^2|\sigma\in S_n\})$.

Two trivial subgroups for a group $G$ are $1_G$ and $G$. $\{1_G\}$ satisfies the properties above.(Use $1_G$ to clarify $1_G$ and the scalar $1$.) Easy to verify that $G$ is also a subgroup of $G$. A subgroup is a *proper subgroup* if it is not one of those two.