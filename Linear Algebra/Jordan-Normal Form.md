Jordan decomposition for $A \in \mathbb{C}^{n \times n}$ is below,
## Goal:
Find matrices \( J \) and \( P \) such that:
$$[
A = P J P^{-1}
]$$
where $( J )$ is the Jordan normal form.

---

## Step-by-Step Guide

### ✅ Step 1: Find the Eigenvalues
- Solve the characteristic polynomial:
  $$[
  \det(A - \lambda I) = 0
  ]$$
- The roots $( \lambda_1, \lambda_2, \dots )$ are the eigenvalues.

---

### ✅ Step 2: Find Algebraic Multiplicity (AM)
- For each eigenvalue, find how many times it repeats as a root in the characteristic polynomial.

---

### ✅ Step 3: Find Geometric Multiplicity (GM)
- For each eigenvalue $( \lambda )$, compute:
  $$
  dim(\ker(A - \lambda I)) = \text{number of linearly independent eigenvectors for } lambda
  $$

---

### ✅ Step 4: Determine Jordan Block Structure
- Number of Jordan blocks for each eigenvalue = GM.
- Sum of the sizes of these blocks = AM.
- For example, if AM = 3 and GM = 1, then there is one Jordan block of size 3.
>[!note]
>- Jordan block for $\lambda$ consists of $\lambda$ on the diagonal, 1 on the upper sub diagonal (If exists) and rest of the elements are 0.

>[!theorem]
>- Every $A \in \mathbb{C}^{n \times n}$ has a Jordan decomposition.
>- If $A \in \mathbb{C}^{n \times n}$ has n L.I eigen vectors then the Jordan decomposition coincides with the Eigen value decomposition.
>- If Jordan blocks of the eigenvalues are of the sizes $\lambda$ are of  the sizes $1 \le k_1,k_2, ... , k_r$,
>	1. $g_{\lambda} = r$
>	2. $a_\lambda = \sum_{i=1}^{r} k_i \ge \sum_{i=1}^{r} 1 = r = g_\lambda$
>	3. $m_\lambda = \max\{k_1, k_2, \cdots, k_r\} = k_j$, say  
>	4. Therefore, $a_\lambda - g_\lambda = \sum_{i=1}^{r}(k_i - 1) \ge k_j - 1 = m_\lambda - 1$, so $a_\lambda \ge g_\lambda$ since $m_\lambda \ge 1$  
>	5. $a_\lambda - g_\lambda = m_\lambda - 1$ if the size of the matrix $n \le 3$




---

### ✅ Step 5: Find Generalized Eigenvectors
- If GM < AM, find generalized eigenvectors by solving:
  $$[
  (A - \lambda I)^k v = 0 \quad \text{for smallest } k > 1
  ]
  but
  [
  (A - \lambda I)^{k-1} v \neq 0
  ]$$
- These vectors form chains that complete the basis.

---

### ✅ Step 6: Construct Matrix \( P \)
- Arrange eigenvectors and generalized eigenvectors as columns of \( P \).
- Order them so that in each Jordan block, the chain goes from the generalized eigenvector to the eigenvector.

---

### ✅ Step 7: Form the Jordan Matrix \( J \)
- \( J \) is block diagonal, each block is a Jordan block:
  $$
  J_k(\lambda) =
  \begin{bmatrix}
  \lambda & 1      & 0      & \cdots & 0 \\
  0       & \lambda & 1     & \cdots & 0 \\
  0       & 0       & \lambda & \cdots & 0 \\
  \vdots  & \vdots  & \vdots  & \ddots & 1 \\
  0       & 0       & 0       & \cdots & \lambda
  \end{bmatrix}
  $$

---

## Summary Table

| Step | Description                          |
|-------|-----------------------------------|
| 1     | Find eigenvalues                   |
| 2     | Find algebraic multiplicities     |
| 3     | Find geometric multiplicities     |
| 4     | Determine number and size of Jordan blocks |
| 5     | Find generalized eigenvectors      |
| 6     | Construct \( P \) from eigenvectors and generalized eigenvectors |
| 7     | Construct Jordan normal form matrix \( J \) |

---

