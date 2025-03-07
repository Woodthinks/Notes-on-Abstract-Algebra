#! https://zhuanlan.zhihu.com/p/691560519
# Notes on Abstract Algebra 6

# Chapter 2: Groups

### VI Cosets and Lagrange's theorem

Recall how normal subgroups are defined:
$$
N\trianglelefteq G:
\begin{cases}
    N \leq G \\
    \forall h\in N, \forall g\in G, ghg^{-1}\in N
\end{cases}
$$
Cosets $\Rightarrow$ Equivalence classes: $H\leq G \Rightarrow \bar a = aH, G = \bigsqcup_{a\in G} aH$.

Lemma: All left cosets $aH$ of a subgroup $H$ of a group $G$ have the same order.

Definition: The index of $H\leq G$: $[G:H] =$ # of left cosets of $H$.

Example: $[\mathbb{Z}:\{0\}]=\infty$, $[\mathbb{Z}:\mathbb{Z}2] = 2$.

Theorem(Counting Formula): $H\leq G\Rightarrow |G| = |H|[G:H]$.

Lagranges's Theorem: If $G$ is finite, $H\leq G$, then $|H| \mid |G|$ i.e.the order of $H$ divides the order of $G$.

Corollary: $G$ is a finite group, $x\in G$, then $|x| \mid |G|$. ($\langle x\rangle \subseteq G$)

Let $G\to G'$ be a group homomorphism of finite groups:

- $|G| = |\ker \varphi| \cdot |\text{im} \varphi|$.
- $|\ker \varphi|$ divides $|G|$, and 
- $|\text{im} \varphi|$ divides both $|G|$ and $|G'|$.

Proof:
By Counting Formula, $|G| = [G:\ker \varphi] |\ker\varphi|$.
Construct a bijection between cosets of $\ker \varphi$(fibers) and $\text{im} \varphi$: $aK\leftrightarrow \varphi(a)$
The bijection is well-defined: Denote $K=\ker \varphi, aK = a'K\Leftrightarrow a = a'k,\exists k\in K\Leftrightarrow \varphi(a) = \varphi(a'k) = \varphi(a')\varphi(k) = \varphi(a')\Leftrightarrow aK = a'K\Leftrightarrow \varphi(a) = \varphi(a').$ 

Proposition: If $K\leq H\leq G$, $[G:K] = [G:H][H:K]$.
E.g. If $H\leq S_n$ satisfies $|H|$ is odd, then $H\leq A_n$. ($\text{sgn}(H)$ divides $|H|\Rightarrow \text{sgn}(H)=1$)

Definition: A right coset of $H\leq G$ is $Ha$ (i.e. $Ha=\{ha|h\in H\}$).

Remark: Also can define an equivalent relation $a\equiv b$ iff $b=ha,h\in H$ (Right congruent). Then there exists an equivalent partition: $\bar a = Ha$.

Think about how to construct a mapping between left cosets and right cosets. 

A "meaningful" bijection $aH\leftrightarrow Ha$($xH \leftrightarrow Hx^{-1}$): $\forall g \in xH, g^{-1}\in Hx^{-1}$ since $\exists h \in H, g = xh \Leftrightarrow \exists h^{-1} \in H, g^{-1} = h^{-1}x^{-1}$.

Insight: $aH \not= Ha$ for general $H,a$. Moreover, only normal subgroups $N$ can get $aN = Na$. Or $z\in Z(G)$ will get $zH = Hz$.

Proposition: $H\leq G$, the following formulas are equivalent;

1. $H\trianglelefteq G$ 
2. $\forall g\in G,gHg^{-1} = H$
3. $\forall g \in G,gH = Hg$
4. $\forall$ left cosets of $H$, it's a right coset.
  
Proof:
$1.\Rightarrow 2.$: $\forall h\in H, ghg^{-1}\in H\Rightarrow gHg^{-1} \subset H$. Then we have $H\subset g^{-1} H g$, and $\forall g\in G, \exists h\in G, g = h^{-1} \Rightarrow \forall h\in H, h\in gHg^{-1} \Rightarrow H\subset gHg^{-1}\Rightarrow H = gHg^{-1}$.
$2.\Rightarrow 3.$: $\forall g\in G,gHg^{-1} = H\Rightarrow \forall g\in G,gH = Hg$.
$2.\Rightarrow 1.$: From definition, $\forall g\in G, h\in H, ghg^{-1}\in gHg^{-1} = H$.
$3.\Rightarrow 4.$: $gH$ is a left coset, $Hg$ is a right coset.
$4.\Rightarrow 3.$: For a left coset $gH$, if $gH = Hg'$, then $g\in gH\Rightarrow g\in Hg'\Rightarrow gg'^{-1}\in H \Rightarrow Hg' = Hg$. Moreover, $\{Hg|g\in G\}$ forms a partition of $G$. $g\in Hg' \Rightarrow Hg = \bar g = Hg'\Rightarrow gH = Hg$.

Proposition: If $\exists! H\leq G, |H| = r$, then $H\trianglelefteq G$.

Proof: $\forall g\in G, gHg^{-1}$ also forms a group of order $r$. If the subgroup of order $r$ is unique, then $\forall g\in G, gHg^{-1} = H$.

Example: $[G:H] = 2$, then $H\trianglelefteq G$.
