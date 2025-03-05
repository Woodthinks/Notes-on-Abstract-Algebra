# Notes on Abstract Algebra 10

# Chapter 2: Groups

### X Product Groups and Review on Groups

Definition: $G,G'$ are groups. The product set $G\times G'=\{(a,a')|a\in G,a'\in G'\}$ together with the following law of composition: $(a,a')\cdot (b,b') = (ab,a'b')$ is a group called (direct) product group of $G$ and $G'$.

Verify:

- Law of composition is associative. (Due to the associativity of the $2$ original group.)
- Identity: $(1_G,1_{G'})$
- Inverse: $(a,a')^{-1} = (a^{-1},a'^{-1})$.

Example: $C_2= \{1,y\},C_3 = \{1,z,z^2\},C_2\times C_3 = \{(1,1),(1,z),(1,z^2),(y,1),(y,z),(y,z^2)\}\cong C_6$.

Proposition: $C_r\times C_s\cong C_{rs}$, if $r,s$ is relatively prime.

Proof: $|C_r\times C_s| = r\times s$. Denote $C_r = \langle y \rangle ,C_s = \langle z\rangle$. $(y,z)$ is order $r\times s$.

Remark: $C_2\times C_2 \not \cong C_4$. Rather $C_2\times C_2 \cong$ Klein four group.

Define: Projection mapping: $G \overset{p}{\leftarrow}G\times G'\overset{p'}{\rightarrow}G':(a,1_{G'})\leftarrow(a,a')\rightarrow(1_G,a')$ with $\ker p = \{1\}\times G'$ and $\ker p' = G\times\{1\}$.

Exercise: Mapping property for $G\times G'$:

$\forall$ group $H,G,G'$, if $\varphi:H\to G,\varphi': H\to G'$. Then $\exists \varphi: H\to G\times G', \varphi = p\circ \varphi, \varphi' = p' \circ \varphi$.

Inclusion mapping: $G \overset{i}{\rightarrow}G\times G'\overset{i'}{\leftarrow}G': a\to (a,1_{G'}),a'\to(1_G,a')$. The inclusion mapping $i$ is injective group homomorphism with images $G\times \{1_{G'}\}$ ($i'$ with $\{1_{G}\}\times G'$).

Question: Given a group $G$, are there $H,K\leq G,G = H\times K$?

Observation: Identifying $G$ with $G\times 1$, we have:

- $\forall(a,a')\in G\times G',(a,a') = (a,1)(1,a')$.
- $G\cap G' = \{(1_G,1_{G'})\}$.
- $G\trianglelefteq G\times G',G'\trianglelefteq G\times G'$

Proposition: $H,K\leq G$. Define $f:H\times K \to G: (h,k)\mapsto hk$.

- $f$ is injective $\Leftrightarrow H\cap K=\{1\}$.
- $f$ is surjective $\Leftrightarrow HK = {G}$.
- $f$ is a group homomorphism$\Leftrightarrow hk = kh,\forall k\in K, H\in H$.

$f$ is a group isomorphism iff $f$ is injective and surjective and $H\trianglelefteq G, K\trianglelefteq G$.

Proposition $|G| = 4$, either $G\cong C_4$ or $G\cong C_2\times C_2$(Klein four group).

​	Case $1$: $\exists x \in G,|x| = 4, G=\langle x \rangle$.

​	Case $2$: $\forall x \in G, x\not = 1, |x| = 2$. Then $\exists y\not = z, |y| = |z| = 2.$ $H = \langle y \rangle, K = \langle z\rangle$, $H\cap K = \{1\}$, $HK = \{1,y,z,yz\} = G$, $[G:H] = [G:K]=2\Rightarrow H\trianglelefteq G, K\trianglelefteq G$. So $G\cong H\times K \cong C_2\times C_2$.

Remark: Note that $G' \overset{i'}{\rightarrow}G'\times G''\overset{p''}{\to}G''$ satisfies $i'$ is an injective group homomorphism, $p''$ is a surjective group homomorphism, which infers $\ker p'' = \text{im } i' = G'\times 1$.    
More generally, short exact sequence can be used to describle such situation. A sequence of group homomorphisms: $1 \to H \xrightarrow{\iota} G \xrightarrow{\pi} K \to 1$  is called a **short exact sequence**(s.e.s) if:
1. $\iota$ is injective,  
2. $\pi$ is surjective,  
3. $\ker \pi = \operatorname{im} \iota$.  

Example: $S_3\not \cong C_2\times C_3$, but exists s.e.s $1\to C_3\to S_3\to C_2 \to 1$.    
In fact, for a normal subgroup $H \trianglelefteq G$, the sequence: $1 \to H \to G \to G/H \to 1$ is exact. 