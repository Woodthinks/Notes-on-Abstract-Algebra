#! https://zhuanlan.zhihu.com/p/684592309
# Notes on Abstract Algebra 1

# Chapter 2: Groups

### I Basic Concepts

Law of compositions: For a set $S$, a law of composition on set $S$ is a mapping: $S\times S\to S$ i.e. $(a,b)\mapsto ab$ (or $a+b$).

Properties:

- Associative: We call a law of composition is associative iff $\forall a,b,c\in S,(ab)c=a(bc)$. (Associative law)

- Commutative: We call a law of composition is commutative iff $\forall a,b\in S,ab=ba$. (Commutative law)

Notation: Usually, we denote the result of composition of $a$ and $b$ as $a+b$ (additive notation) if the law of composition is commutative. And $ab$ (product notation) will carry no implication on whether the law is commutative. (For convenience, unless specified, we use to product notation refer to the law of composition.)

Insight: Associative law is seen as more common and "fundamental" (*P38, Algebra, M. Artin*) than the commutative law.

Example: Consider the set $S = M_{2\times2}(\mathbb{R})$ i.e. the set of $2\times2$ real matrices. Define the law of composition as $(A, B)\mapsto AB$ i.e. the matrix multiplication. It's associative but not commutative.

Propositions of properties:

If a law of composition (the mapping $S\times S \to S$) is associative, then $\forall n\in\mathbb{N}, \forall a_1,a_2,\cdots,a_n\in S,$ the value of $a_1a_2\cdots a_n$ is independent of how it's bracketed.

A similar proportion on Commutative law is (more obvious):

If a law of composition (the mapping $S\times S \to S$) is commutative , then $\forall n\in\mathbb{N}, \forall a_1,a_2,\cdots,a_n\in S,$ the value of $a_1a_2\cdots a_n$ is independent of its order.

We give out a brief proof of the proposition on associative law:

Denote the value of  $a_1a_2\cdots a_n$ without brackets as $[a_1a_2\cdots a_n] = (\cdots((a_1a_2)a_3)a_{n-1})\cdots a_n$

Using Induction to prove this proposition i.e. no matter how it's bracketed, its value is equal to $[a_1a_2\cdots a_n]$:

When $n\leq 2$, the proposition holds obviously.

When $n=3$, the proposition holds due to the associative law.

We suppose when $k\leq n-1$, the proposition (for $k$ elements ) holds, and we consider when $k=n$.

We could find the last bracket at position $i$, that is $a_1\cdots(a_k\cdots a_i)a_{i+1}\cdots a_n$.

If $i\leq n-1$, then consider the items without $a_n:a_1\cdots(a_k\cdots a_i)a_{i+1}\cdots a_{n-1}$, with induction hypothesis, we know that it is equal to $ [a_1\cdots a_{n-1}] = (\cdots((a_1a_2)a_3)\cdots )a_{n-1}$.  So $a_1\cdots(a_k\cdots a_i)a_{i+1}\cdots a_n =(\cdots((a_1a_2)a_3)\cdots )a_{n-1} a_n = ((\cdots((a_1a_2)a_3)\cdots )a_{n-1}) a_n =[a_1a_2\cdots a_n]$. The second equality holds due to the original order of composition.

If $i = n$, then the formula becomes $a_1\cdots a_{k-1}(a_k\cdots a_n)$. Use induction hypothesis on $k$ to $n$, it becomes $a_1\cdots a_{k-1} ((\cdots (a_k a_{k+1})\cdots )a_n)$. Then using associative law (with $a_1\cdots a_{k-1},(\cdots (a_k a_{k+1})\cdots )a_{n-1},a_n$), it will become $(a_1\cdots a_{k-1} (\cdots (a_k a_{k+1})\cdots ))a_n$. This form is finished by above $(i\leq n-1)$.

This completes the proof. Similar to $1$ for multiplication and $0$ for addition, we want to find a "unit" for the law of composition.

Definition: Identity（幺元/单位元）(Usually denote the identity as $0/1(\in S)$, depending on the notation of the law of composition.)

- An identity for a law of composition $S\times S\to S$ is $e\in S$ s.t. $\forall a \in S, ea = a, ae=e$.

Lemma: Identity is unique. (In other words, left identity is equal to right identity.)

Proof:

If their exists $2$ identities $e'$ and $e$. We have: $e = e'e = e'$

The first equality holds due to $e'$ being identity and the second equality holds due to $e$ being identity.

(This proof can also show that left identity is also right identity and vice versa.)

After we define identity, we can define what "opposite" means for the law of composition.

Definition: Invertible（可逆）and Inverse（逆元）(Usually denote the inverse as $-a/a^{-1}$.) :

- Suppose a law of composition $S\times S\to S$ is associative, with an identity $1\in S$. Then $a\in S$ is invertible iff $\exists b\in S, ab = ba = 1(\in S)$. $b$ is called the inverse of $a$.

Lemma:

- If $la = 1, ar = 1$,then $l =r$. (If left inverse and right inverse both exist, then they are equal.)
- $a$ is invertible $\Rightarrow$ $a^{-1}$ is unique. (Inverse is unique.)
- If $a,b$ is invertible, then $ab$ is invertible and $(ab)^{-1} = b^{-1}a^{-1}$. (Inverse under the law of composition.)

Proof:

- $l= lar = r$
- If exists $b$ and $c$ that $ba = ca = 1,ab=ac = 1$, then $b = bac = c$.  
- Consider $(ab)(b^{-1}a^{-1})$ and $(b^{-1}a^{-1})(ab)$. $(ab)(b^{-1}a^{-1}) = (abb^{-1})a^{-1} = aa^{-1}=1,(b^{-1}a^{-1})(ab) = (b^{-1}a^{-1}a)b=b^{-1}b=1$

Example:

Consider the set $S = M_{2\times2}(\mathbb{R})$ and the law of composition mentioned before. $\exists A, A$ is not invertible. However, consider a subset of $S:$ $S'=\{X|X\in S, X \text{ is invertible}\}$. (It's closed under the law of composition i.e. matrix multiplication.) $\forall A\in S',A$ is Invertible. And for those two sets and laws of composition, $I$, or more detailed, $I_{2}$ is the identity.

Notation: With $n\in \mathbb{N},$ $a\times\cdots(n\text{ factors})\times a = a^n, a^{-n} = a^{-1}\times\cdots(n\text{ factors})\times a^{-1},a^0 = 1(\in S)$(product notation) or $na = a+\cdots + a, -na = (-a) + \cdots + (-a)$ (additive notation). Notations $\frac ba$ are not preferred

A *group*（群） is a set $G$ together with a law of composition $G\times G\to G$ which satisfies:

- Associativity ($\forall a,b,c\in G, (ab)c = a(bc)$)
-  $\exists e \in G, e$ is identity.
- $\forall a \in G, a$ is Invertible.

If the law of composition only satisfies the first condition, it's called a *semigroup*（半群）; if the law of composition satisfies the first two conditions, it's called a *monoid*（幺半群）. If the law of composition also satisfies the commutative law, it's called an *abelian group*（阿贝尔群/交换群）.

Propositions (Cancellation Law,消去律): Let $a,b,c$ be elements of a group $G$ whose law of composition is written multiplicatively. If $ab = ac$, or if $ba = ca$, then $b=c$. If $ab=a$ or if $ba = a$, then $b=1$.

Proof: Multiply $a^{-1}$ on the left side of $ab=ac$ or the right side of $ba=ca$. The second proposition is a special case for $c=1$.

The *order* of a group $G$ is the number of elements that it contains: $|G| =$ \# of elements of $G$. (A naive method to decide kinds of groups: finite/infinite)

Some notations of familiar groups: $\mathbb Z^+,\mathbb R^+,\mathbb R^\times,\mathbb C^{+},\mathbb C^{\times}$.(Note that multiplication groups should remove $0$ from the sets.) Moreover, due to ambiguity, it might be better to denote groups like $(\mathbb R,+)$.

Insight: Given a finite set $S$ with a certain order, we can construct a group $G$, whose elements are invertible mappings on $S$ ($S\to S$) and the law of composition is composition mapping ($f,g\mapsto f\circ g$). The number of groups is finite.