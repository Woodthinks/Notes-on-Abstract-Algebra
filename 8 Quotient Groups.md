# Notes on Abstract Algebra 8

# Chapter 2: Groups

### VIII Quotient Groups

Recall for linear spaces, quotient spaces are defined to represent a set of "parallel" subsets. For groups, we have cosets to represent subsets "parallel" to a subgroup i.e. cosets. We use more abstract concept to describle "parallel" subsets more exactly.

Given $N\trianglelefteq G$, denote $G/N = \{aN|a\in G\}$. (Later we will show why $N\trianglelefteq G$ not $N\leq G$.) Our goal is to define a natural group structure on $G/N$.

Motivation:
- $\mathbb{Z}n \trianglelefteq (\mathbb{Z},+)$: $\bar a + \bar b = \overline{a+b}$.
- Bijeection between fibers and elements in image: $\phi: G\to G'$ is a group homomorphism with $\ker \phi = K$. Then $\{\text{fibers}\}(G/K)\overset{\text{bijection}}{\longleftrightarrow} \text{im }\phi\leq G'(aK\leftrightarrow\phi(a))$.

The group structure on $G/K$ may be inducted by the group structure on $\text{im } \phi$ i.e. $aK \cdot bK = (ab)K$. e.g. $\phi = \text{sgn }: S_3\to\{\pm 1\}^{\times}$, $K = \{1\}, yK = \{-1\}$. (Elements $\to$ product of elements)