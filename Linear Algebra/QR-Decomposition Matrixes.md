$$
A = QR
$$

- $Q$ is the **orthogonal** (or **orthonormal**) matrix formed from $A$. Its columns are orthonormal vectors.
- $R$ is an **upper triangular** matrix.
- Since $Q$ is orthogonal, it satisfies:
  $$
  Q^T = Q^{-1}
  $$
- For complex matrices, the **adjoint** (conjugate transpose) satisfies:
  $$
  Q^{*} = Q^{-1}
  $$
  where $Q^{*} = \overline{Q}^T$ (conjugate transpose). This generalizes the orthogonal case to **unitary** matrices.
- To compute $R$:
  $$
  R = Q^T A
  $$
- The entries of $R$ can be expressed using inner products:
  $$
  R_{ij} = \langle u_i, v_j \rangle
  $$
  where $u_i$ are the orthonormal columns of $Q$, and $v_j$ are the columns of $A$.
- Note: $R$ is upper triangular, so $R_{ij} = 0$ for $i > j$.
- [Reference video for QR decomposition](https://youtu.be/FAnNBw7d0vg?si=StNyUUaE6gYkm8TC)
