# Notes on Abstract Algebra 9

# Chapter 2: Groups

### IX Correspondence Theorem 

Theorem (The Correspondence Theorem of groups): If $\varphi: G\to G'$is a surjective group homomorphism with $\ker \varphi = K$. Then there exists a bijection $\{\text{subgroup }H\text{ of } G \text{ containing } K\}\leftrightarrow \{\text{subgroup H' of } G'\}: H\mapsto \varphi(H),\varphi^{-1}(H')\mapsto H'$. 
Moreover, if $H$corresponds $H'$, then $H\trianglelefteq G$iff $H' \trianglelefteq G'$and $|H'| = |H||K|$.

### Correspondence Theorem in Group Theory

---

#### **Statement of the Theorem**  
Let $\varphi: G \to G'$ be a **surjective homomorphism** of groups with kernel $K = \ker \varphi$. Then there is a bijection:  
$$
\big\{ \text{subgroups } H \subseteq G \mid K \subseteq H \big\} \longleftrightarrow \big\{ \text{subgroups } H' \subseteq G' \big\}
$$
The correspondence is given by:  
- $H \mapsto \varphi(H) $(from $G $to $G' $),  
- $H' \mapsto \varphi^{-1}(H') $(from $G' $to $G $).  

**Key Properties**:  
1. $H $is a **normal subgroup** of $G $if and only if $\varphi(H) $is a **normal subgroup** of $G' $.  
2. If $K \subseteq H \subseteq G $, then $G/H \cong G'/\varphi(H) $.  

---

#### **Key Formulas and Proof Ideas**  
1. **Kernel-Subgroup Relationship**:  
   $$
   \varphi^{-1}(\varphi(H)) = H \cdot K \quad (\text{when } K \subseteq H).
   $$
   To verify: If $K \subseteq H $, then $\varphi^{-1}(\varphi(H)) = H $.  

2. **Normal Subgroup Correspondence**:  
   - If $H \trianglelefteq G$, then $\varphi(H) \trianglelefteq G' $(since $\varphi $is surjective).  
   - If $H' \trianglelefteq G' $, then $\varphi^{-1}(H') \trianglelefteq G $.  

3. **Restricted Homomorphism and Quotient Groups**:  
   $$
   \varphi|_H: H \to \varphi(H) \text{ is a surjective homomorphism with kernel } K \cap H.
   $$
   In particular, if $K \subseteq H $, then $H/K \cong \varphi(H) $.  

---

#### **Direct Product of Groups**  
Let $G $and $G' $be groups. Their **direct product** $G \times G' $is defined as:  
$$
G \times G' = \{ (g, g') \mid g \in G, g' \in G' \}
$$
**Group Operation**:  
$$
(g_1, g'_1) \cdot (g_2, g'_2) = (g_1 g_2, g'_1 g'_2)
$$
**Properties**:  
1. **Identity Element**: $(1_G, 1_{G'}) $.  
2. **Inverse Element**: $(g, g')^{-1} = (g^{-1}, (g')^{-1}) $.  
3. **Associativity**: Inherited from $G $and $G' $.  

---

#### **Example: Structure of $C_2 \times C_3 $**  
- $C_2 = \{ 1, a \} $(cyclic group of order 2),  
- $C_3 = \{ 1, b, b^2 \} $(cyclic group of order 3).  

The direct product group $C_2 \times C_3 $Has elements:  
$$
C_2 \times C_3 = \big\{ (1,1), (1,b), (1,b^2), (a,1), (a,b), (a,b^2) \big\}
$$
This group has order $2 \times 3 = 6 $and is isomorphic to the cyclic group $C_6 $.  

---

#### **Remarks**  
1. **Application of the Correspondence Theorem**:  
   - When $\varphi: G \to G/N $is the natural projection, the subgroup correspondence becomes:  
     $$
     \{ H \subseteq G \mid N \subseteq H \} \longleftrightarrow \{ \text{subgroups } H/N \subseteq G/N \}.
     $$
2. **Role of the Kernel**: The kernel $K = \ker \varphi $is a normal subgroup of $G $, and $G/K \cong G' $.  

---

#### **Notation Summary**  
- $\ker \varphi $: Kernel of the homomorphism $\varphi $.  
- $H \cdot K $: Product of subgroup $H $and kernel $K $.  
- $\trianglelefteq $: Notation for normal subgroups.  
- $\cong $: Notation for group isomorphism.  

--- 

This note concisely summarizes the Correspondence Theorem, direct product groups, and their properties, with examples to illustrate key concepts.