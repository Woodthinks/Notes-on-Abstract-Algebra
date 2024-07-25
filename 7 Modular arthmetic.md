#! https://zhuanlan.zhihu.com/p/691563034
# Notes on Abstract Algebra 7

# Chapter 2: Groups

### VII Modular arithmetic and $\mathbb{Z}/n\mathbb{Z}$

When we talk about subgroups, we first discuss subgroups of $(\mathbb{Z},+)$. When we talk about cosets, we will take $\mathbb{Z}$ as examples.
Another way to call them is "modular arithmetic". In this part, $n$ is a positive integer.

Definition: We say $a,b\in \mathbb{Z}$ are congreunt mod $n$ $(a\equiv b (\text{mod } n))$ iff $n|a-b$.

Remark: $a\equiv b(\text{mod }n)$ iff $a\equiv b$(w.r.t $n\mathbb{Z}$).

Lemma: $\equiv(\text{mod }n)$ is an equivalence relation.
Some notation: $\bar a = \{a+kn|k\in\mathbb{Z}\}$, (Quotient Set) $\mathbb{Z}/n\mathbb{Z} = \{\bar a| a\in \mathbb{Z}\} = \{\bar 0,\bar 1,\cdots, \overline{n-1}\}$.
$\bar a$ is called the congruence classes. 
The laws of operation between congruence classes are defined as $\bar a + \bar b = \overline{a+b},\bar a \bar b = \overline{ab}$.

Lemma: The definition are well-defined i.e. $\forall \bar a = \bar {a'},\bar b = \bar {b'}, \bar a + \bar b = \bar {a'} + \bar{b'}, \bar a \bar b = \bar{a'}\bar{b'}.$
Propositions:

- $(\mathbb{Z}/n\mathbb{Z},+)$ is an abelian group with identity $\bar 0$.
- $(\mathbb{Z}/n\mathbb{Z}-\{\bar0\},\cdot)$ is associative, communitive with identity $\bar 1$.
- The distribution law holds: $\forall \bar a,\bar b,\bar c\in \mathbb{Z}/n\mathbb{Z},\bar a(\bar b+\bar c) = \bar a \bar b+\bar a \bar c,(\bar b+\bar c)\bar a=\bar b\bar a + \bar c \bar a$.

Proof for the third law (left distribution, similarly for right distribution):
$\forall \bar a,\bar b,\bar c\in \mathbb{Z}/n\mathbb{Z},\bar a(\bar b+\bar c) = \bar a \overline{(b+c)} = \overline{a(b+c)}= \overline{ab+ac} =  \overline{ab}+\overline{ac} = \bar a \bar b+\bar a \bar c$.

The above $3$ propositions show that $(\mathbb{Z}/n\mathbb{Z},+,\cdot)$ is a communitive ring with unit.
Example: Solve $2x+5\equiv 8 (\text{mod } 9)$
Solution: In $\mathbb{Z}/9\mathbb{Z}$, $\bar 2 \bar x + \bar 3 = \bar 8\Rightarrow \bar 2 \bar x = \bar 5\Rightarrow \bar 5 \bar 2 \bar x = \bar5\bar5 \Rightarrow \bar x = \bar 7 (\bar 2^{-1} = \bar 5 \text{ since } \bar 2 \bar 5 =\bar 1)$.

Proposition: Let $(\mathbb{Z}/n\mathbb{Z})^* = \{\bar a \in \mathbb{Z}/n\mathbb{Z}|\exists \bar b\in \mathbb{Z}/n\mathbb{Z},\bar a \bar b = \bar 1\}$. Then $(\mathbb{Z}/n\mathbb{Z})^* = \{\bar a \in \mathbb{Z}/n\mathbb{Z}| \gcd(a,n) =1\}$.

Proof: $\exists b\text{ s.t. }\bar a \bar b = \bar 1\Leftrightarrow\exists b \text{ s.t. }ab\equiv 1(\text{mod }n)\Leftrightarrow \exists k\in \mathbb{Z},ab + kn = 1\Leftrightarrow \gcd(a,n) = 1$.

Corollary: If $p$ is a prime, then $(\mathbb{Z}/ p \mathbb{Z})^* = \mathbb{Z}/ p \mathbb{Z} - \{\bar 0\}$

Example: Solve $\left\{\begin{array}{lc}x \equiv 2(\text{mod } 3) & (1)\\ 
x \equiv 3(\text{mod } 5) &(2)\\ 
x \equiv 2(\text{mod } 7) &(3)
\end{array}\right.$

Solution (1):
$
x = 3k+2 \overset{\text{into }(2)}{\longrightarrow} \overline{3k+2} = \bar3 \Rightarrow \overline{3k} = \bar 1 \Rightarrow \bar k = \bar 2 \text{ i.e. } k = 5m+2 \\
x = 15m+8 \overset{\text{into }(3)}{\longrightarrow}\overline{15m+8} = \bar2 \Rightarrow \overline{m+1} = \bar 2\Rightarrow \bar m = \bar 1
\text{ i.e. } m = 7a+1\\
x = 105a+23
$

Solution (2):

Observation: Suppose $x_1, x_2, x_3$ satisfies:
$
 \left\{\begin{array} { l } 
{ x _ { 1 } \equiv 1 (\text{mod }3 ) } \\
{ x _ { 2 } \equiv 0 (\text{mod }5 ) } \\
{ x _ { 3 } \equiv 0 (\text{mod }7 ) }
\end{array},\right.
\left\{\begin{array} { l } 
{ x _ { 2 } \equiv 0 (\text{mod }3 ) } \\
{ x _ { 2 } \equiv 1 (\text{mod }5 ) } \\
{ x _ { 2 } \equiv 0 (\text{mod }7 ) }
\end{array},\right.
\left\{\begin{array} { l } 
{ x _ { 3 } \equiv 0 (\text{mod }3 ) } \\
{ x _ { 3 } \equiv 0 (\text{mod }5 ) } \\
{ x _ { 3 } \equiv 1 (\text{mod }7 ) }
\end{array};\right.$ where $x=2 x_1+3 x_2+2 x_3$.
$
x_1=35 k_1\Rightarrow \overline{35} \bar k_1=\bar 1 \Rightarrow \bar 2 \bar k_1=\bar 1 \Rightarrow \bar k_1=\bar{2}, \\
k_1=3 m+2\Rightarrow x_1=105 m+70 ;
$
$
x_2=21 k_2\Rightarrow \overline{21} \bar k_2=\bar 1 \Rightarrow \bar k_2=\bar 1, \\
\bar k_2=5 m+1\Rightarrow x_2=105 m+21 ;
$
$
x_3=15 k_3\Rightarrow \overline{15} \bar k_3=\bar 1 \Rightarrow  \bar k_3=\bar 1, \\
\bar k_3=7 m+1\Rightarrow x_3=105 m+15 ;
$
$
x = 2x_1+3x_2+2x_3 = 105 \left(2 m_1+3 m_2+2 m_3\right)+233 \text {. } \\
105 k+233=105 k+23 . \\
$

Generalizing the method of solution (2), we can prove the Chinese Remainder Theorem:

For pairwise relatively prime numbers $n_1,\dots,n_k\in\mathbb{Z}>0$, $\forall b_1,\dots, b_k\in \mathbb{Z}$, $\exists x\in \mathbb{Z}, \forall i,x\equiv b_i (\text{mod }n_i)$. Moreover, $x$ is unique modulo $N = n_1\dots n_k$.

Definition: A field $F$ is a set with $2$ laws of composition:

- $+$: $F\times F\to F, (a,b)\mapsto a+b$.
- $\cdot$: $F\times F\to, (a,b)\mapsto a\cdot b$.

Satisfying: 

- $(F,+)$ is an Abelian group with identity $0$.
- $(F-{0},\cdot)$ is an Abelian group with identity $1\not = 0$.
- Distribution law holds $\forall a,b,c\in F,a(b+c) = ab+ac$.
  
Examples: $\mathbb{Q},\mathbb{R},\mathbb{C},\mathbb{Q}(\sqrt2) = \{a+b\sqrt2|a,b\in\mathbb{Q}\}, \mathbb F_p = (\mathbb{Z}/p\mathbb{Z}^*,+,\cdot)$(for a prime $p$).
$\mathbb F_p$ is an example of finite fields.

By Lagrange's Theorem, we know that $\forall 1\leq a<p,|\bar a|$ divides $|(\mathbb{Z}/p\mathbb{Z})^*| = p-1 \Rightarrow (\bar a)^{p-1} = \bar 1\Rightarrow a^{p-1} \equiv 1(\text{mod }p)$. (Together with $a = np$, we get $a^p \equiv a (\text{mod } p)$.This is also called the Fermat's Little Theorem).

Insight: When it comes to a general $n$($n$ may not be prime.) $|(\mathbb{Z}/p\mathbb{Z})^*|$ is equal to the number of those which is relatively prime to $n$, also denoted as $\phi(n)$(The Euler's function), Then it can be generalized into The Euler's Theorem: $\forall a \text{ s.t. }\gcd(a,n) = 1,a^{\phi(n)} \equiv 1(\text{mod }n)$.

Another example (Wilson's Theorem): If $p$ is prime, then $(p-1)!\equiv -1(\text{mod }p)$.

Remark: $((\mathbb{Z}/p\mathbb{Z})^*,\cdot)$ is a cyclic group of order $p-1$.

Propositions: In $\mathbb F_p$,
- $\bar a \bar b = \bar 0 \Rightarrow \bar a = \bar 0$ or $\bar b = \bar 0$. 
- $\bar a \neq \bar 0,\bar a \bar b = \bar a \bar c\Rightarrow \bar b = \bar c$. (Cancellation law)
