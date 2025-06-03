> **How can we make an orthonormal basis from any basis?**

- Start with your original basis vectors:  
  $v_1, v_2, \ldots, v_n$  
  and transform them into orthogonal vectors:  
  $u_1, u_2, \ldots, u_n$

1. $u_1 = v_1$  
2. $u_2 = v_2 - \frac{\langle v_2, u_1 \rangle}{\|u_1\|^2} u_1$  
3. $u_3 = v_3 - \frac{\langle v_3, u_1 \rangle}{\|u_1\|^2} u_1 - \frac{\langle v_3, u_2 \rangle}{\|u_2\|^2} u_2$  

And in general:  
$$
u_k = v_k - \sum_{j=1}^{k-1} \frac{\langle v_k, u_j \rangle}{\|u_j\|^2} u_j
$$

- What you’re doing here is: taking each vector $v_k$ and removing the parts that lie along the previously found orthogonal vectors $u_1, u_2, \ldots, u_{k-1}$. This leaves you with a vector $u_k$ that’s orthogonal to all the earlier $u_j$'s.

- **Note:** The first vector $u_1$ is just $v_1$ because there’s nothing to subtract yet.

- The vectors $u_1, u_2, \ldots, u_n$ you get here are **orthogonal**, but not necessarily **orthonormal**.

- To get an **orthonormal** basis, just divide each $u_k$ by its length:  
$$
e_k = \frac{u_k}{\|u_k\|}
$$
