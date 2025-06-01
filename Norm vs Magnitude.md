> What is the difference between norm and magnitude?
---
### Norm vs Magnitude

- **Magnitude** is a term commonly used in **Euclidean space** (like $\mathbb{R}^2$, $\mathbb{R}^3$) to describe the **length** of a vector.
- **Norm** is a more general term used in **linear algebra and functional analysis** to describe the **size or length** of vectors in arbitrary vector spaces.

---

### In Euclidean space:

The **norm** of a vector is its **magnitude**:

$$
\| \mathbf{v} \| = \sqrt{v_1^2 + v_2^2 + \cdots + v_n^2}
$$

This is often called the **Euclidean norm**, or **$L^2$ norm**.

---

### In general (any normed vector space):

A **norm** is a function:

$$
\| \cdot \| : V \rightarrow \mathbb{R}
$$

satisfying:

1. **Non-negativity**  
   $$\| x \| \ge 0 \quad \text{and} \quad \| x \| = 0 \iff x = 0$$

2. **Scalar multiplication**  
   $$\| a x \| = |a| \cdot \| x \|$$

3. **Triangle inequality**  
   $$\| x + y \| \le \| x \| + \| y \|$$

---

### Summary:

- In basic settings, **norm = magnitude**.
- In advanced math, **norm** generalizes **magnitude** to spaces where “length” isn’t just the Euclidean one.

In everyday or practical contexts—like physics, engineering, or basic geometry—we usually say **magnitude** when talking about the length of a vector. It’s intuitive and tied directly to the idea of physical size or length.

**Norm**, on the other hand, is a more formal, mathematical concept used mostly in higher-level math, functional analysis, or more abstract vector spaces where “length” can be defined in different ways (not just the usual Euclidean length).

So yes, **in common use, people say magnitude**, because:

- It’s simpler and more concrete.
    
- Most practical vectors live in $\mathbb{R}^2$ or $\mathbb{R}^3$ where magnitude = norm.
    
- Norm is mainly a generalized concept used in theoretical or advanced contexts.