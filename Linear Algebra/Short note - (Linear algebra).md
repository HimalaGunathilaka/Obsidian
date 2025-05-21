## 📘 Quick Summary

- A **subspace** is a part of a vector space that contains 0 and is closed under addition and scalar multiplication.  
- A **basis** is a minimal set of vectors that span the space and are linearly independent.  
- The **dimension** of a space is the number of vectors in its basis.  
- **Rank–nullity theorem**: `dim(V) = rank(T) + nullity(T)`  
- The **inner product** generalizes dot product — defines angles, lengths, and orthogonality.  
- A **norm** gives the length of a vector.

---

## Subspace  

> A **subspace** of a vector space $V$ is a subset $W \subseteq V$ that:
>
> 1. **Contains the zero vector**  
> 2. **Closed under vector addition**: If $u, v \in W$, then $u + v \in W$  
> 3. **Closed under scalar multiplication**: If $v \in W$ and $c \in \mathbb{R}$, then $cv \in W$

---

## Basis  

> A **basis** of a vector space is a set of vectors that:
> 1. **Span the space** – every vector can be written as a linear combination of basis vectors  
> 2. Are **linearly independent** – no vector can be made from the others

### 🔹 In simpler terms:
> A basis is the **minimum set of building blocks** needed to describe the entire space.

### ℹ️ Why it matters:
- The number of vectors in a basis = **dimension**  
- In $\mathbb{R}^n$, any basis has **exactly $n$** vectors

---

## Dimensions  

- **nullity** of $T$: $\text{dim}(\ker T)$  
- **rank** of $T$: $\text{dim}(\text{ran } T)$  
- **Dimension Theorem**:  
  $\dim(V) = \text{nullity}(T) + \text{rank}(T)$

---

## Inner Product  

> An **inner product** is an operation that takes two vectors and returns a scalar.

### 🧮 In $\mathbb{R}^n$, it’s the dot product:
$\langle u, v \rangle = u_1v_1 + u_2v_2 + \dots + u_nv_n$

### ✅ Properties:
1. **Linearity**:  
   $\langle cu + v, w \rangle = c\langle u, w \rangle + \langle v, w \rangle$  
2. **Symmetry**:  
   $\langle u, v \rangle = \langle v, u \rangle$  
3. **Positive definiteness**:  
   $\langle u, u \rangle \geq 0$, and equals 0 iff $u = 0$

---

## Norm  

> A **norm** measures the length of a vector.

### ✅ Properties of a norm $\| \cdot \|$:

1. **Non-negativity**:  
   $\| v \| \geq 0$, and $\| v \| = 0 \iff v = 0$  
2. **Homogeneity**:  
   $\| cv \| = |c| \cdot \| v \|$  
3. **Triangle inequality**:  
   $\| u + v \| \leq \| u \| + \| v \|$

### 🔸 Common Norms:

#### 1. Euclidean norm ( $l_2$ norm ):
$\| v \|_2 = \sqrt{v_1^2 + v_2^2 + \dots + v_n^2}$

#### 2. Manhattan norm ( $l_1$ norm ):
$\| v \|_1 = |v_1| + |v_2| + \dots + |v_n|$

#### 3. Infinity norm:
$\| v \|_\infty = \max_i |v_i|$

# Eigenvalues, Eigenvectors, and Diagonalizability

## Eigenvalues and Eigenvectors

- **Eigenvalue** $( \lambda )$ and **eigenvector** $( \vec{v} )$ are related by the equation:
  
  $$ A \vec{v} = \lambda \vec{v} $$

  This means that when a matrix $( A )$ acts on an eigenvector $( \vec{v} )$, it only **scales** the vector by $( \lambda )$, without changing its direction.

- Eigenvectors are the special directions in which a matrix (linear transformation) acts in a simple way — just stretching or shrinking. The corresponding eigenvalue $( \lambda )$ tells how much stretching or shrinking occurs along that direction.

## Finding Eigenvectors

1. **Find the eigenvalues**: Solve the **characteristic equation**:
   
   $$ \det(A - \lambda I) = 0 $$

   This gives the eigenvalues $( \lambda_1, \lambda_2, \dots )$.

2. **Solve for eigenvectors**: For each eigenvalue $( \lambda )$, solve the system of linear equations:

   $$ (A - \lambda I) \vec{v} = 0 $$

   The solutions to this system will give you the eigenvectors corresponding to $( \lambda )$.

   - The null space (set of solutions) gives the **eigenvectors**.
   - These eigenvectors form a **basis** for the eigenspace corresponding to $( \lambda )$.

## Diagonalizability

- A matrix \( A \) is **diagonalizable** if there exists an invertible matrix \( P \) (formed from its eigenvectors) such that:

  $$ A = P D P^{-1} $$

  Where \( P \) is the matrix whose columns are the **eigenvectors** of \( A \), and \( D \) is the diagonal matrix whose diagonal entries are the **eigenvalues** of \( A \).

## Matrix \( P \) and Diagonalizability

- If the matrix \( P \) formed by eigenvectors has **linearly independent eigenvectors**, then \( P \) is **invertible**, and \( A \) is diagonalizable.
  
- The determinant of $( P )$, $( \det(P) )$, tells us if $( P )$ is invertible:
  - **If $( \det(P) \neq 0 )$**, the matrix $( A )$ is diagonalizable.
  - **If $( \det(P) = 0 )$**, the matrix $( A )$ is **not diagonalizable**.

## Key Points

- **Eigenvectors** are directions where the matrix acts by stretching or shrinking, with no rotation.
- **Eigenvalues** give the factor by which the eigenvectors are stretched or shrunk.
- **Diagonalizability** depends on having enough linearly independent eigenvectors (i.e., a full set of eigenvectors).

---

This note provides an overview of how eigenvalues and eigenvectors work, and how diagonalizability is determined by the matrix of eigenvectors $( P )$.
