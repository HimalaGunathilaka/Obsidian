> How is the inner product defined? Isn't it just the dot product? 
---
### Inner Product vs Dot Product

- The **dot product** is a specific type of **inner product** defined in Euclidean space.
- The **inner product** is a generalization of the dot product.

---

### In Euclidean space ($\mathbb{R}^n$):

The inner product **is** the dot product:

$$
\langle \mathbf{a}, \mathbf{b} \rangle = \mathbf{a} \cdot \mathbf{b} = \sum_{i=1}^n a_i b_i
$$

---

### In general (abstract vector spaces):

An **inner product** is a function:

$$
\langle \cdot, \cdot \rangle : V \times V \rightarrow \mathbb{R} \text{ or } \mathbb{C}
$$

satisfying:

1. **Linearity in the first argument**  
   $$\langle ax + by, z \rangle = a\langle x, z \rangle + b\langle y, z \rangle$$

2. **Conjugate symmetry**  
   $$\langle x, y \rangle = \overline{\langle y, x \rangle}$$

3. **Positive-definiteness**  
   $$\langle x, x \rangle \ge 0 \quad \text{and} \quad \langle x, x \rangle = 0 \iff x = 0$$

---

### Conclusion:

Yes — **in $\mathbb{R}^n$, the inner product is just the dot product**.  
But in more general spaces, it's defined abstractly using the properties above.
