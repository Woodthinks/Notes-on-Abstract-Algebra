# Notes on Abstract Algebra 4

# Chapter 2: Groups

### IV Group homomorphisms

Definition: $G,G'$ are $2$ groups. A group homomorphism $\varphi$ from $G$ to $G'$ is a map satisfying $\forall a,b\in G,\varphi(ab)=\varphi(a)\varphi(b)$.\
Examples:
- Determinant: $GL_n(\mathbb{R})\to (\mathbb{R}^*,\times):A\mapsto \det A$
- Exponential: $(\mathbb{R},+)\to (\mathbb{R}_+^*,\times): r\mapsto e^r$.
- Modular: $(\mathbb{C},+)\to (\mathbb{R}_+^*,\times): z\mapsto \vert z\vert$.
- Sign: $S_n\to (\{\pm 1\},\times): \sigma \mapsto \text{sgn } \sigma$. 
- Trival group homomorphism: $G\to G': g\mapsto 1_{G'}$.
- $H\to G$, where $H\leq G$: $h\mapsto h$.

Proposition: $\varphi:G\to G'$ is a group homomorphism. Then:
1. $\varphi(a_1a_2\cdots a_n) = \varphi(a_1)\varphi(a_2)\cdots\varphi(a_n)$,
2. $\varphi(1_G) = 1_{G'}$,
3. $\forall a \in G,\varphi(a^{-1}) = \varphi(a)^{-1}$. 

Proof:
1. Induction: For $k = n$ holds, when $k = n+1$, $\varphi(a_1a_2\cdots a_n a_{n+1})=\varphi(a_1a_2\cdots a_n)\varphi(a_{n+1}) = \varphi(a_1)\varphi(a_2)\cdots\varphi(a_n)\varphi(a_{n+1})$.
2. $\varphi(1_G) = \varphi(1_G 1_G) = \varphi(1_G) \varphi(1_G)\Rightarrow\varphi(1_G) = 1_{G'}$.
3. $\varphi(a)\varphi(a^{-1}) = \varphi(aa^{-1})=\varphi(1_G) = 1_{G'}\Rightarrow\varphi(a)^{-1} = \varphi(a^{-1})$.

Definition: A group isomorphism is a bijective group homomorophism. If there exists a group isomorphism $\varphi:G\to G'$, then we say $G$ is isomorphic to $G'$ i.e. $G\cong G'$. \
Example: 
- Exponential: $(\mathbb{R},+)\to (\mathbb{R}_+^*,\times): r\mapsto e^r$.
- Integer: $\mathbb{Z}\to \mathbb{Z}n: 1\mapsto n (k\mapsto nk)$.

Lemma: If $\varphi: G\to G'$ is an isomorphism. Then $\varphi^{-1}: G'\to G$ is a group isomorphism.\
Proof: Need to show that: $\forall a',b'\in G', \varphi^{-1}(a'b') = \varphi^{-1}(a')\varphi^{-1}(b')$. Since $\forall a,b\in G,\varphi(ab) = \varphi(a)\varphi(b)$, then make $a=\varphi^{-1}(a'),b=\varphi^{-1}(b')\Rightarrow \varphi(ab) = a'b' \Rightarrow \varphi^{-1}(a')\varphi^{-1}(b') = ab = \varphi^{-1}(a'b')$.

Remark: $\varphi: G\to G'$ as a group isomorphism. Then $a_n = 1_G \Leftrightarrow \varphi(a)^n  = 1_{G'}$. In particular, $|a|$ = $|\varphi(a)|$.\
Proof: "$\Rightarrow$": $\varphi(a)^n = \varphi(a^n) = 1_{G'}$. "$\Leftarrow$": $a^n = \varphi^{-1}(\varphi(a^n) = \varphi^{-1}(\varphi(a)^n)) = \varphi^{-1}(1_{G'}) = 1_G$.

Definition: $\varphi: G\to G'$ as a group homomorphism. The kernel of $\varphi$ (denoted as $\ker \varphi$) is $\{a\in G|\varphi(a) = 1_{G'}\}\subset G$, the image of $\varphi$ (denoted as $\text{im } \varphi$)  is $\{x\in G'| \exists a \in G, \varphi(a) = x\}\subset G'$.

Proposition: $\ker \varphi\leq G$, $\text{im } \varphi\leq G'$. (In fact, kernels have better properties than subgroups.)\
Example: 
| $\varphi$ | $\ker \varphi$  | $\text{im }\varphi$  |
|------------|----|----|
| $\det: GL_n(\mathbb{R})\to \mathbb{R}^*$ | $SL_n(\mathbb{R})$ | $\mathbb{R}^*$ |
| $\vert \vert:\mathbb{C}\to \mathbb{R}^{*}_+$ | $\{z\in\mathbb{C}\mid \vert z\vert = 1\}$| $\mathbb{R}_+^*$
| $\text{sgn }: S_n\to \{\pm 1\}^{\times}$ | $A_n$ | $\{\pm 1\}$

Given $f:S\to T,t\in T$, we also call the inverse image $f^{-1}(t) = \{ s\in S|f(s) = t \}$ the fiber of $f$ over $t$. Kernel is the fiber of the group homomorphism over $1$.\
Consider $\varphi: \text{sgn }$ on $S_3$, how to describe fiber of $\varphi$? (Notation: $S_3 = \{1,x,x^2,y,xy,x^2y\}$ with $xy = yx^2,y^2=x^3=1$. More specifically, $x=(12),xy=(13),x^2y=(23)$) \
Try: Use translation of kernels: $K = \ker\varphi = \{1,x,x^2\}$. \ 
Left multiplication by $y$: $\{y,yx,yx^2\} = \{y, x^2y, xy\} = yK$.\
Left multiplication by $xy$: $\{xy,y,x^2y\} = xyK$.\
Left multiplication by $x^2y$: $\{x^2y,xy,y\}=x^2yK$.\
They turn out to be equal.

Notation: $H\leq G, a\in G$. Define $aH = \{ah|h\in H\}\subset G$, called the left coset of $H$. (Most time not subgroups) \ 
Proposition: $\varphi: G\to G'$ as a group homomorphism and $a,b\in G, K = \ker \varphi$, $K=\ker\varphi$. Then the following statements are equivlance (TFAE):
1. $\varphi(a) = \varphi(b)$.
2. $a^{-1}b\in K$.
3. $b \in aK$.
4. $aK = bK$.

Proof:
- $(1\Rightarrow 2)$: $\varphi(a^{-1}b) = \varphi(a)^{-1}\varphi(b) = 1_G\Rightarrow a^{-1}b \in K$
- $(2\Rightarrow 3)$: $a^{-1}b = k$ for some $k\in K \Rightarrow b \in aK (b = ak)$.
- $(3\Rightarrow 4)$: $\forall ak'\in aK, b=ak\Rightarrow bkk' \in aK \Rightarrow aK\subset bK$. Similarly for $bK\subset aK$. So $aK = bK$.
- $(4\Rightarrow 1)$: $aK = bK \Rightarrow b = ak$ for some $k$, then $\varphi(b) = \varphi(ak) = \varphi(a)$.

Corollary: $\varphi: G\to G'$ as a group homomorphism, $K=\ker\varphi$. Then the fiber of $\varphi$ containing $a \in G$ (i.e. over $\varphi(a)$) is $aK$.\
Proof:
- $\varphi^{-1}(\varphi(a))\subseteq aK$: $\forall b\in \varphi^{-1}(\varphi(a)), \varphi(a) = \varphi(b) \Rightarrow b\in aK$.
- $\varphi^{-1}(\varphi(a))\supseteq aK$: $\forall b\in aK,\varphi(b) = \varphi(a)\varphi(k) = \varphi(a)$.

Corollary: $\exists$ bijection from $K$ to $aK=\varphi^{-1}(\varphi(a))$. \
Proof: The inverse map $aK\to K$ is $b\mapsto a^{-1} b$.\
This corollary shows that all non-empty fibers have the same order.

Proposition: $\varphi$ is a group homomorphism, then 1.$\varphi$ is injective iff $\ker\varphi = 1_G$, and 2.$\varphi$ is surjective iff $\text{im }\varphi G = G'$.\
Proof: 1 "only if" trivial since injective indicates fibers can only take $1$ elements at most; 1"if" since suppose $\varphi(a)=\varphi(b)$ then $\varphi(a^{-1}b ) = 1_G$ so $a^-1b = 1\Rightarrow a =b$. 2 trival due to the definition of image and surjective. 

Insights: Kernel and images of group homomorphism can be analogised to null space and range space of a linear transformation. Linear transformation shows that for $T:V\to W,\dim \text{null } T +\dim \text{range } T= \dim V$. The similar conclusion holds when it comes to group i.e. a relation of $|\ker \varphi|,|\text{im }\varphi|, |G|$ for $\varphi: G\to G'$. 