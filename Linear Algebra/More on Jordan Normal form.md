## 🔗 Linear Independence & Eigenvectors

A set of vectors is **linearly independent** if **none of them can be written as a linear combination of the others**.

### 🧠 Why the Definition Might Feel Backward

Mathematically, we define linear independence using:

$$
c₁v₁ + c₂v₂ + ⋯ + cₙvₙ = 0
$$

The vectors are **linearly independent** if the **only** solution is:

$$
c₁ = c₂ = ⋯ = cₙ = 0
$$

That feels backward at first, but it's precise:  
If there’s **no nontrivial way** to combine them and get the zero vector, they’re independent.

---

## 💡 Key Fact

> **Eigenvectors corresponding to distinct eigenvalues are linearly independent.**

---

### 📚 Concepts Cheat Sheet

| Concept                     | Meaning                                                                        |
| --------------------------- | ------------------------------------------------------------------------------ |
| **Diagonalization**         | A matrix is diagonalizable if it has enough linearly independent eigenvectors. |
| **Jordan Form**             | Used when a matrix isn’t diagonalizable.                                       |
| **Jordan Block**            | A block matrix with a repeated eigenvalue and 1s on the superdiagonal.         |
| **Generalized Eigenvector** | Helps form a complete basis when regular eigenvectors aren’t enough.           |

---

## 📌 What Is a Generalized Eigenvector?

Given a matrix **A** and eigenvalue **λ**, a **generalized eigenvector** is a vector **v** such that:
$$
(A − λI)^k v = 0 \quad \text{for some smallest integer } k > 1
$$

but:
$$
(A − λI)^{k−1} v ≠ 0
$$
So:
- It’s **not** a regular eigenvector (doesn't satisfy $(A - λI)v = 0$),
- But applying $(A - λI)$ **repeatedly** will eventually send it to zero.

---

## 🧠 The Kernel (Null Space)

The **kernel** (or **null space**) of a matrix **A** is the set of all vectors **x** such that:

$$A x = 0
$$

### ✅ Dimension of the Kernel

The **dimension** of the kernel is the number of **basis vectors** required to span it.

---

## ✅ Step-by-Step: Finding Eigenvectors

### Step 1: Set Up the Equation

You want to find non-zero vectors **v** such that:

$$
A v = λ v
$$

Rewriting this:

$$
(A − λI) v = 0
$$

This is a **homogeneous system** — you're looking for the **null space** of $(A - λI)$.

---
### Step 2: Solve the Null Space

1. Compute $(A - λI)$.
2. Solve:
$$
(A − λI) v = 0
$$

This finds **all** eigenvectors corresponding to λ.

- The solution space may have infinitely many vectors.
- These vectors form a **basis** of the eigenspace.

---

## 🔁 What Does "Similar Matrices" Mean?

> **Matrix A is similar to matrix B** if:
$$
A = P B P^{-1}
$$

for some **invertible matrix** $P$.

---

### 🧩 Algebraic vs Geometric Multiplicity

| Term                          | Meaning                                                                          |
|-------------------------------|----------------------------------------------------------------------------------|
| **Algebraic Multiplicity**    | How many times $$λ$$ appears as a root of the **characteristic polynomial**     |
| **Geometric Multiplicity**    | The **dimension of the eigenspace**: the number of linearly independent eigenvectors |

- The **number of Jordan blocks** for λ = **geometric multiplicity**.
- The **sum of block sizes** = **algebraic multiplicity**.

---

## 🌐 What Is the Image of a Matrix?

The **image** of a matrix $M$, written as $\text{Im}(M)$, is:

$$
\text{Im}(M) = \{ Mv \mid v \in \mathbb{R}^n \}
$$

It’s the set of all **output vectors** you can get by applying $M$ to some input.

---

### 🧠 Understanding Example:

Suppose we’re analyzing:
$$
(A - I) m_3 = m_2
$$

This means:

- $m_2 \in \text{Im}(A - I)$
- There **exists** some $m_3$ such that $(A - I)m_3 = m_2$
