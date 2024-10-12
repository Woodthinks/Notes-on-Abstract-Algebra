# Notes on Abstract Algebra 8

# Chapter 2: Groups

### VIII Quotient Groups

Recall for linear spaces, quotient spaces are defined to represent a set of "parallel" subsets. For groups, we have cosets to represent subsets "parallel" to a subgroup i.e. cosets. We use more abstract concept to describle "parallel" subsets more exactly.

Given $N\trianglelefteq G$, denote $G/N = \{aN|a\in G\}$. (Later we will show why $N\trianglelefteq G$ not $N\leq G$.) Our goal is to define a natural group structure on $G/N$.

Motivation:
- $\mathbb{Z}n \trianglelefteq (\mathbb{Z},+)$: $\bar a + \bar b = \overline{a+b}$.
- Bijeection between fibers and elements in image: $\phi: G\to G'$ is a group homomorphism with $\ker \phi = K$. Then $\{\text{fibers}\}(G/K)\overset{\text{bijection}}{\longleftrightarrow} \text{im }\phi\leq G'(aK\leftrightarrow\phi(a))$.

The group structure on $G/K$ may be inducted by the group structure on $\text{im } \phi$ i.e. $aK \cdot bK = (ab)K$. e.g. $\phi = \text{sgn }: S_3\to\{\pm 1\}^{\times}$, $K = \{1\}, yK = \{-1\}$. (Elements $\to$ product of elements)

Theorem (with definition): Suppose $N\trianglelefteq G$, $\exists$ a law of composition on $G/N$ that makes it a group (called quotient group) s.t. the quotient mapping $\pi: G\to G/N(a\mapsto aN)$ is a group homomorphism with $\ker \pi = N$.

Proof: Need to: \
(I). Give out a definition on $G/N \times G/N \to G/N$. \
(II). Prove that $G/N$ with the law above is a group. \
(III). Prove that $\phi$ is a group homomorphism. \
(IV). Prove $\ker \phi = N$. \
For (I), define $aN\times bN = (ab)N$. Then we show a lemma: The definiton following is well-defined: 
-    Suppose $a\equiv a',b\equiv b'$ (i.e. $a'= am,b'=bn$) Then $a'b' = ambn = abb^{-1}mbn = abm'n \equiv ab(m\in N\trianglelefteq G\Rightarrow m' = b^{-1}mb \in N)$. \
(Remark: the lemma fails in non-normal subgroups.)

(II): Associativity: $(aN\cdot bN)\cdot cN = (ab)N \cdot cN = ((ab)c)N = (a(bc))N = aN \cdot (bN\cdot cN)$.\
Identity: $aN \cdot 1N = 1N\cdot aN = aN$. \
Inverse: $aN \cdot (a^{-1})N = a^{-1}N \cdot aN = 1N$.\
Before proving the last two, we first come up with a proposition:\
Proposition (Mapping property of quotient groups): Given $N\trianglelefteq G, \pi: G\to G/N$ (the quotient homomorphism). Suppose $\phi:G\to G'$ is a group homomorphism with $\phi(N) = 1_{G'}(N\leq \ker \phi)$. Then $\exists$ group homomorphism $\bar \phi: G/N \to G'$ s.t. $\phi = \bar \phi \circ\pi $.

Proof: Define $\bar \phi(aN) = \phi(a)$, which is the only way that makes $\phi = \bar \phi \circ\pi $.