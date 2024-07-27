# Notes on Abstract Algebra 4

# Chapter 2: Groups

### IV Group homomorphisms

Definition: $G,G'$ are $2$ groups. A group homomorphism $\phi$ from $G$ to $G'$ is a map satisfying $\forall a,b\in G,\phi(ab)=\phi(a)\phi(b)$.\
Examples:
- Determinant: $GL_n(\mathbb{R})\to (\mathbb{R}^*,\times):A\mapsto \det A$
- Exponential: $(\mathbb{R},+)\to (\mathbb{R}_+^*,\times): r\mapsto e^r$.
- Modular: $(\mathbb{C},+)\to (\mathbb{R}_+^*,\times): z\mapsto \vert z\vert$.
- Sign: $S_n\to (\{\pm 1\},\times): \sigma \mapsto \text{sgn } \sigma$. 
- Trival group homomorphism: $G\to G': g\mapsto 1_{G'}$.
- $H\to G$, where $H\leq G$: $h\mapsto h$.

Proposition: $\phi:G\to G'$ is a group homomorphism. Then:
1. $\phi(a_1a_2\cdots a_n) = \phi(a_1)\phi(a_2)\cdots\phi(a_n)$,
2. $\phi(1_G) = 1_{G'}$,
3. $\forall a \in G,\phi(a^{-1}) = \phi(a)^{-1}$. 

Proof:
1. Induction: For $k = n$ holds, when $k = n+1$, $\phi(a_1a_2\cdots a_n a_{n+1})=\phi(a_1a_2\cdots a_n)\phi(a_{n+1}) = \phi(a_1)\phi(a_2)\cdots\phi(a_n)\phi(a_{n+1})$.
2. $\phi(1_G) = \phi(1_G 1_G) = \phi(1_G) \phi(1_G)\Rightarrow\phi(1_G) = 1_{G'}$.
3. $\phi(a)\phi(a^{-1}) = \phi(aa^{-1})=\phi(1_G) = 1_{G'}\Rightarrow\phi(a)^{-1} = \phi(a^{-1})$.

Definition: A group isomorphism is a bijective group homomorophism. If there exists a group isomorphism $\phi:G\to G'$, then we say $G$ is isomorphic to $G'$ i.e. $G\cong G'$. \
Example: 
- Exponential: $(\mathbb{R},+)\to (\mathbb{R}_+^*,\times): r\mapsto e^r$.
- Integer: $\mathbb{Z}\to \mathbb{Z}n: 1\mapsto n (k\mapsto nk)$.

Lemma: If $\phi: G\to G'$ is an isomorphism. Then $\phi^{-1}: G'\to G$ is a group isomorphism.\
Proof: Need to show that: $\forall a',b'\in G', \phi^{-1}(a'b') = \phi^{-1}(a')\phi^{-1}(b')$. Since $\forall a,b\in G,\phi(ab) = \phi(a)\phi(b)$, then make $a=\phi^{-1}(a'),b=\phi^{-1}(b')\Rightarrow \phi(ab) = a'b' \Rightarrow \phi^{-1}(a')\phi^{-1}(b') = ab = \phi^{-1}(a'b')$.

Remark: $\phi: G\to G'$ as a group isomorphism. Then $a_n = 1_G \Leftrightarrow \phi(a)^n  = 1_{G'}$. In particular, $|a|$ = $|\phi(a)|$.\
Proof: "$\Rightarrow$": $\phi(a)^n = \phi(a^n) = 1_{G'}$. "$\Leftarrow$": $a^n = \phi^{-1}(\phi(a^n) = \phi^{-1}(\phi(a)^n)) = \phi^{-1}(1_{G'}) = 1_G$.

Definition: $\phi: G\to G'$ as a group homomorphism. The kernel of $\phi$ (denoted as $\ker \phi$) is $\{a\in G|\phi(a) = 1_{G'}\}\subset G$, the image of $\phi$ (denoted as $\text{im } \phi$)  is $\{x\in G'| \exists a \in G, \phi(a) = x\}\subset G'$.

Proposition: $\ker \phi\leq G$, $\text{im } \phi\leq G'$. (In fact, kernels have better properties than subgroups.)\
Example: 
| $\phi$ | $\ker \phi$  | $\text{im }\phi$  |
|------------|----|----|
| $\det: GL_n(\mathbb{R})\to \mathbb{R}^*$ | $SL_n(\mathbb{R})$ | $\mathbb{R}^*$ |
| $\vert \vert:\mathbb{C}\to \mathbb{R}^{*}_+$ | $\{z\in\mathbb{C}\mid \vert z\vert = 1\}$| $\mathbb{R}_+^*$
| $\text{sgn }: S_n\to \{\pm 1\}^{\times}$ | $A_n$ | $\{\pm 1\}$

Given $f:S\to T,t\in T$, we also call the inverse image $f^{-1}(t) = \{ s\in S|f(s) = t \}$ the fiber of $f$ over $t$. Kernel is the fiber of the group homomorphism over $1$.\
Consider $\phi: \text{sgn }$ on $S_3$, how to describe fiber of $\phi$? (Notation: $S_3 = \{1,x,x^2,y,xy,x^2y\}$ with $xy = yx^2,y^2=x^3=1$. More specifically, $x=(12),xy=(13),x^2y=(23)$) \
Try: Use translation of kernels: $K = \ker\phi = \{1,x,x^2\}$. \ 
Left multiplication by $y$: $\{y,yx,yx^2\} = \{y, x^2y, xy\} = yK$.\
Left multiplication by $xy$: $\{xy,y,x^2y\} = xyK$.\
Left multiplication by $x^2y$: $\{x^2y,xy,y\}=x^2yK$.\
They turn out to be equal.

Notation: $H\leq G, a\in G$. Define $aH = \{ah|h\in H\}\subset G$, called the left coset of $H$. (Most time not subgroups) \ 
Proposition: $\phi: G\to G'$ as a group homomorphism and $a,b\in G, K = \ker \phi$, $K=\ker\phi$. Then the following statements are equivlance (TFAE):
1. $\phi(a) = \phi(b)$.
2. $a^{-1}b\in K$.
3. $b \in aK$.
4. $aK = bK$.

Proof:
- $(1\Rightarrow 2)$: $\phi(a^{-1}b) = \phi(a)^{-1}\phi(b) = 1_G\Rightarrow a^{-1}b \in K$
- $(2\Rightarrow 3)$: $a^{-1}b = k$ for some $k\in K \Rightarrow b \in aK (b = ak)$.
- $(3\Rightarrow 4)$: $\forall ak'\in aK, b=ak\Rightarrow bkk' \in aK \Rightarrow aK\subset bK$. Similarly for $bK\subset aK$. So $aK = bK$.
- $(4\Rightarrow 1)$: $aK = bK \Rightarrow b = ak$ for some $k$, then $\phi(b) = \phi(ak) = \phi(a)$.

Corollary: $\phi: G\to G'$ as a group homomorphism, $K=\ker\phi$. Then the fiber of $\phi$ containing $a \in G$ (i.e. over $\phi(a)$) is $aK$.\
Proof:
- $\phi^{-1}(\phi(a))\subseteq aK$: $\forall b\in \phi^{-1}(\phi(a)), \phi(a) = \phi(b) \Rightarrow b\in aK$.
- $\phi^{-1}(\phi(a))\supseteq aK$: $\forall b\in aK,\phi(b) = \phi(a)\phi(k) = \phi(a)$.

Corollary: $\exists$ bijection from $K$ to $aK=\phi^{-1}(\phi(a))$. \
Proof: The inverse map $aK\to K$ is $b\mapsto a^{-1} b$.\
This corollary shows that all non-empty fibers have the same order.

Proposition: $\phi$ is a group homomorphism, then 1.$\phi$ is injective iff $\ker\phi = 1_G$, and 2.$\phi$ is surjective iff $\text{im }\phi G = G'$.\
Proof: 1 "only if" trivial since injective indicates fibers can only take $1$ elements at most; 1"if" since suppose $\phi(a)=\phi(b)$ then $\phi(a^{-1}b ) = 1_G$ so $a^-1b = 1\Rightarrow a =b$. 2 trival due to the definition of image and surjective. 

Insights: Kernel and images of group homomorphism can be analogised to null space and range space of a linear transformation. Linear transformation shows that for $T:V\to W,\dim \text{null } T +\dim \text{range } T= \dim V$. The similar conclusion holds when it comes to group i.e. a relation of $|\ker \phi|,|\text{im }\phi|, |G|$ for $\phi: G\to G'$. 