# Group
- A set G together with a binary operation $*$ (often called multiplication or addition) is called a **group**. (G,$*$)
- It should satisfy following properties,
	1. G not equal null
	2. $*|G \times G \rightarrow G$ is a function. (All inputs are accountable, (Explain what is accountable here))
		- That means $a \in G, b \in G ; a * b \in G$
		- ==In other words, using binary operator present, you can't go out of the set.==
	3. $\forall a,b,c \in G; a * (b*c) = (a*b)*c$ , ($*$ is associative)
	4. $\exists e \in G \forall a \in G; a*e = e*a = a$ , (`e` is the identity. Does this basically means there should be a identity.)
	5. $\forall a \in G ; a*\bar{a} = \bar{a} * a = e$ , ($\bar{a}$ is the inverse of $a$.)
A ~={red}binary operator=~ is essentially a function that **takes two inputs (from a set) and returns one output (from the same or possibly another set)**.
So, if perform within a single set, it may can give result outside the set,
	Ex: $\set{1,2,3}; f(x,y) = x+y$, you will get 4 here, which is not inside the set

>Note
- A group should have at least one element. (Identity)

>Theorms
- Let $(G,*)$ be a group and $a \in G$, then $\bar{\bar{a}} = a$
- If $(G,*)$ is a group, then 
	1. e is uique
	2. $\bar{a}$ is unique


---
#  Abelian Group or Commutative group

- It has all the properties of a group, plus following.
	6. $\forall a,b \in G ; a*b = b*a$ , (Basically commutative.)

---
# Fields
- Defined as $(F, +,*)$
- A field has few properties, 
	1. $(F,+)$ is an abelian group
	2. $(F-\set{e_+},*)$ is an abelian group
	3.  $*|F \times F \rightarrow F$ is a function. ($\times$ operator is closed)
	4. $\forall a,b,c \in F; a*(b+c) = a*b + a*c$ ; (Distributive law)
>[!note]
>- A field should have at least two elements. (Identities of the above abelian groups.)

>[!Theorems]
> - Let $(F,+,*)$ be a field and $a \in F$, 
> 	1. $0*a=0$
> 	2. $0 \ne 1$
>- ==Here the underscritpt number in the operator means that it uses the set of that number modules values. I mean just that the operator result must be the modulas of p==
>	- $F_p = \set{0,1,2,3,4, ..., p-1}$ , p is prime, the ($F_p, +_p,*_p$) is a field.
>	- F is a finite field $\iff$ the (number of elements in F), $|{F}| = p^{k}$ , p is prime, $k \in \mathbb{Z}^+$ 

---
# Vector space
- $(V,\#,*)$ over $(F,+,.)$ is a vector space $\iff$
	1. $(V,\#)$ is an [[#Abelian Group or Commutative group]]
	2. $(F,+,.)$ is a field
	3. $*|F \times V \rightarrow V$ ; is a function
	4.  $\forall a,b \in F;\forall v \in V; (a+b)*v = a*v \# b*v$ 
	5. $\forall a,b \in F;\forall v,u \in V; a*(v\#u) = a*v \# a*u$ 
	6. $\forall a,b \in F;\forall v \in V; (a.b)*v = a*(b*v)$
	7. $\forall x \in V; 1 * x = x$ 
>Confusing symbol explanation
- $(F, +, \cdot)$ is a field:
    - $+$ is field addition: $a + b$
    - $\cdot$ is field multiplication: $a \cdot b$
- $(V, \#, *)$ is a vector space over $F$:
    - $\#$ is vector addition: $\vec{u} \# \vec{v}$
    - $*$ is scalar multiplication: $a * \vec{v}$ where $a \in F$, $\vec{v} \in V$
---
# Subspace
- Closure under scaler multiplication
- Closure under vector addition
Let `V` be a vector space over `F` and `S` be a non empty subset of `V`. Then,
	`S` is a subspace of `V` $\iff$ `S` is a vector space over `F` 
(Basically its a fragment of the original vector space. But it is a vector space it self.)

>Theorem
- Let S be a non empty subset of the vector space V over F . If S is closed under vector addition and scalar multiplication, then S is a subspace of V over F.
---
# Linear combination and Independancy
Let $B = \{x_1, x_2, \dots, x_n\}$ be a non-empty finite subset of a vector space $V$ over a field $F$. Then an element of the form $\sum_{k=1}^{n} a_k x_k = a_1 x_1 + a_2 x_2 + \cdots + a_n x_n$, with $a_k \in F$, is called a linear combination of $B$.
i.e. $\text{Span}(B) = \left\{ \sum_{k=1}^{n} a_k x_k \mid x_k \in B,\, a_k \in F \right\}$.  
If $\text{Span}(B) = W$, we say that $B$ spans $W$.
- In other words, `span is like the all vectors inside a vector space`
- $span(B) = V$ --> B span V
- B is ~={purple}linearly independent=~ $\iff \left\{\sum_{i=1}^{n}a_ix_i = \vec{0} \implies \forall i,a_i\right\} =0$ 
- Here **Scaler multiplication** along with **vector addition** is used to get the 0.

>[!Theorem]
>1. If $B' \subseteq B$, then $\text{Span}(B') \subseteq \text{Span}(B) \subseteq V$  
>2. $\vec{0} \in \text{Span}(B)$  
>3. $\text{Span}(B)$ is a subspace of $V$  
>4. $\text{Span}(B)$ is the smallest subspace of $V$ that contains $B$
>- If $B = \{x_1, x_2, \dots, x_n\}$ is linearly dependent, then at least one element of $B$ can be written as a linear combination of the others.

---
# Basis
Let $B$ be a non-empty finite subset of a vector space $V$ over a field $F$. $B$ is called a **basis** of $V$ if and only if ~={yellow}$B$ spans $V$ =~and ~={yellow}$B$ is linearly independent=~.

>Theorem
- Let a basis $B$ have $n$ elements in a vector space $V$ over a field $F$. Then:
    1. Any subset of $V$ with more than $n$ elements is linearly dependent.
	2. Any subset of $V$ with fewer than $n$ elements does not span $V$.
- Any two bases in a vector space has the same number of elements.
- Representation of any element in a vector space by a given basis is unique. i.e. the associated field elements are unique.
- If B spans a vector space V but no proper subset of B spans V . Then B is a basis for V . (Basically B has enough elements, not more to cover up V.)
- Let B be a `LI` subset of V . Then B can be extended to a basis.(Already the previous terms are linearly independent, so we can add new linearly independent terms to form the basis.)
- Let B be a spanning subset of V . Then B can be reduced to a basis. ~={cyan}(A **spanning subset** is any set of vectors whose **span is the entire space**.)=~
- B is a basis iff B is maximally linearly independent(no super set that contains B is linearly independent).

>Note

Consider the system of equations $A_{n \times m} X_{m \times 1} = b_{n \times 1}$, i.e., $n$ equations in~={red} $m$ =~variables.
1. If $\text{rank}(A|b) > \text{rank}(A)$, then there are **no solutions** (inconsistent system).
2. If $\text{rank}(A|b) = \text{rank}(A) = r$, then the system is **consistent**:
	1. If $r = m$, then there is a **unique solution**. 
	2. If $r < m$, then there are **infinitely many solutions**.  
	3. If $r > m$, this is **not possible** because rank cannot exceed the number of columns $m$.
3. If $\text{rank}(A|b) < \text{rank}(A)$, this is **not possible** by definition of augmented matrix rank.
Here (A|b) is the augmented matrix.

---
# Hamel basis
Basis Such that it need not be finite and only finite linear combinations are taken. (Like x powers in $e^{x}$ expansion)
~={blue}In other words, Hamel basis has infinite elements, there for its fine to take only fininte number of elements.=~

~={cyan}**"Properly contained"** (also called **proper subset**) means that one set is **strictly inside** another set — it is **contained** but **not equal**.=~

>Definition
- A collection of sets $\mathcal{C}$ is called a **chain** if and only if for all $A, B \in \mathcal{C}$, either $A \subseteq B$ or $B \subseteq A$.
- An element $M$ of a collection of sets $\mathcal{D}$ is called **maximal** if and only if $M$ is not properly contained in any element of $\mathcal{D}$.
>Theorems
- ~={green}Zorn’s Lemma=~ : If for every chain $\mathcal{C}$ in a collection $\mathcal{D}$, there exists an element $U \in \mathcal{D}$ such that $U$ contains every member of $\mathcal{C}$ (i.e., $U$ is an upper bound of $\mathcal{C}$), then $\mathcal{D}$ has a maximal element.
- Every vector space has a Hamal Basis.
---
# Dimension
The number of elements in a basis of a vector space $V$ is called its **dimension**, denoted by $\dim V$.  
We define $\dim \{0\} = 0$, where $\{0\}$ is the zero vector space.

---
# Schauder basis
A **Schauder basis** $B$ is a basis such that it is **countably infinite**, and **infinite sums** (i.e., infinite linear combinations) are allowed to represent elements of the space.
- A **Schauder basis** is used in **infinite-dimensional vector spaces**, especially in **functional analysis**.
- Unlike a finite basis (where vectors are written as finite linear combinations), a **Schauder basis** allows:$$x = \sum_{n=1}^{\infty} a_n x_n$$where the sum is an **infinite linear combination** that **converges** (typically in norm or topology) to the vector $x$.
>Theorem
- If $f \in C[-\pi, \pi]$ and $\sum_{k=-\infty}^{\infty} |c_k|$ is convergent, then the Fourier series of $f$ **exists** and **converges uniformly** to $f$ on $[-\pi, \pi]$. Note that $f \in C[-\pi, \pi] \Rightarrow f \in L^2[-\pi, \pi]$.

---
# Inner product
Let $V$ be a vector space over an ordered field $(F, +, \cdot, \le)$. Then an **inner product** $\langle \cdot, \cdot \rangle$ on $V$ is a function satisfying the following properties for all $x, y, z \in V$ and $a \in F$:

1. $\langle \cdot, \cdot \rangle : V \times V \to F$ is a function  
2. $\langle x, y \rangle = \langle y, x \rangle$ (Symmetry)  
3. $\langle x, y + z \rangle = \langle x, y \rangle + \langle x, z \rangle$ (Linearity in the second argument)  
4. $\langle ax, y \rangle = a \langle x, y \rangle$ (Homogeneity in the first argument)  
5. $\langle x, x \rangle \ge 0$ and $\langle x, x \rangle = 0$ if and only if $x = 0$ (Positive-definiteness)
> **Note:**  
> $F = \mathbb{C}$ is **not** an ordered field.  
> However, a proper subset $\mathbb{R} \subset \mathbb{C}$ **is** an ordered field.  
> 
> We define or ensure the order properties on $\mathbb{R}$, but such an order **cannot** be extended to the entire field $\mathbb{C}$ while preserving field operations.
- $\overline{\langle x, y \rangle} = \langle y, x \rangle$
- ${\langle ax, y \rangle} = \bar{a}\langle y, x \rangle$
- $\langle x, x \rangle , 0 \in \mathbb{R}$ 
>Further
- We define the norm of $x$ as $\|x\| = \sqrt{\langle x, x \rangle}$
- $\langle x, y \rangle = x^H \cdot y$ for $V = \mathbb{C}^n$ over $F = \mathbb{C}$,  where the Hermitian of $x$ is $x^H = \overline{x}^T =\overline{ x^T}$ 
- $\langle A, B \rangle = \operatorname{Tr}(A^H B)$ for $V = \mathbb{C}^{n \times n}$ over $F = \mathbb{C}$, where the trace $\operatorname{Tr}$ is the sum of the diagonal elements.
>Theorems
- **Cauchy–Schwarz Inequality:**  
$$
|\langle u, v \rangle| \leq \|u\| \|v\|
$$
- **Triangle Inequality:**  
$$
\|u + v\| \leq \|u\| + \|v\|
$$

## Ordered field
A field $F$ is called an **ordered field** if:
- There is a **total order** $<$ on $F$ such that for all $a, b, c \in F$:
	- **Trichotomy**: Exactly one of the following is true: $a < b$, $a = b$, or $a > b$
	- **Transitivity**: If $a < b$ and $b < c$, then $a < c$
- The order is **compatible with field operations**:
	- If $a < b$, then $a + c < b + c$
	- If $0 < a$ and $0 < b$, then $0 < ab$


---
# Orthogonality vs Orthonormality

$x, y \in V$

1. $x, y \in V$ are **orthogonal** iff $\langle x, y \rangle = 0$  
2. $x, y \in V$ are **orthonormal** iff $x, y$ are orthogonal and $\|x\| = \|y\| = 1$

If the above conditions are satisfied for **all** $x, y \in B$, we say that the set $B$ is **orthogonal** or **orthonormal** respectively.

>Theorem
- If $0 \notin B$ and $B$ is orthogonal, then $B$ is linearly independent.
- [[Gram schmidt process]]

> [!note]- Note  
> Let $V = \mathbb{R}[x]$, $F = \mathbb{R}$ and $B = \{1, x, x^2, x^3, \ldots \}$ be the standard basis.
> 
> 1. **Orthogonal basis w.r.t. the inner product**  
>    $$
>    \langle f, g \rangle = \int_{-1}^1 f(x) g(x) \, dx
>    $$  
>    is  
>    $$
>    B = \left\{1, x, \frac{1}{2}(3x^2 - 1), \ldots \right\} = \{P_n(x)\}_{n=0}^\infty
>    $$  
>    where $P_n(x)$ are the **Legendre polynomials**.  
>    They satisfy the ODE:  
>    $$
>    (1 - x^2) y'' - 2x y' + n(n+1) y = 0.
>    $$
> 
> 2. **Orthogonal basis w.r.t. the inner product**  
>    $$
>    \langle f, g \rangle = \int_0^\infty e^{-x} f(x) g(x) \, dx
>    $$  
>    is  
>    $$
>    B = \left\{1, -x + 1, \frac{1}{2}(x^2 - 4x + 2), \ldots \right\} = \{L_n(x)\}_{n=0}^\infty
>    $$  
>    where $L_n(x)$ are the **Laguerre polynomials**.  
>    They satisfy the ODE:  
>    $$
>    x y'' + (1 - x) y' + n y = 0.
>    $$
> 
> 3. **Orthogonal basis w.r.t. the inner product**  
>    $$
>    \langle f, g \rangle = \int_{-1}^1 \frac{1}{\sqrt{1 - x^2}} f(x) g(x) \, dx
>    $$  
>    is  
>    $$
>    B = \left\{1, x, 2x^2 - 1, \ldots \right\} = \{T_n(x)\}_{n=0}^\infty
>    $$  
>    where $T_n(x)$ are the **Chebyshev polynomials**.  
>    They satisfy the ODE:  
>    $$
>    (1 - x^2) y'' - x y' + n^2 y = 0.
>    $$
>    It is also true that  
>    $$
>    T_n(\cos \theta) = \cos(n \theta).
>    $$

---
# Normal subspace
~={blue}A **normal subspace** usually refers to a subspace that is, in some sense, _perpendicular_ or _orthogonal_ to another subspace in a vector space with an inner product.=~
Let $W$ be a non-empty subset of an inner product space $V$ over $F$.  
The **Normal Subspace** of $W$, or the **$W$ perpendicular space**, is defined as  
$$
W^\perp = \{ u \in V \mid \langle u, w \rangle = 0, \; \forall w \in W \}.
$$


> [!tip] Theorems
> 1. $W^\perp$ is a [[#Subspace]] of $V$.  
> 2. $(W^\perp)^\perp \supseteq W$.  
> 3. $W \cap W^\perp = \{0\}$, if $W$ is also a subspace.  
> 4. If $W$ is a subspace of $V$, then any $u \in V$ can be written as  
>    $$
>    u = P u + Q u
>    $$  
>    where  
>    $Q u \in W^\perp$ and  
>    $$
>    P u = \sum_i \overline{\langle u, w_i \rangle} w_i \in W,
>    $$  
>    with $\{w_i\}$ an orthonormal basis for $W$. Using (3), this expression is unique.  (Basically any vector can be written as part of W and W normal space.)
> 5. In the setting described by (4), we write  
>    $$
>    V = W \oplus W^\perp,
>    $$  
>    and say that $V$ is a **direct sum** of $W$ and $W^\perp$.  
> 6. With the setting in (4), $P u$ is the **best approximation** to $u$ in $W$, i.e.  
>    $$
>    \|u - P u\| \leq \|u - w\|
>    $$  
>    for any $w \in W$. (The vector $P \vec{u}$ (which is the projection of $\vec{u}$ onto W) is **the closest vector** in W. “Closest” here means the distance (norm) between $\vec{u}$ and $P\vec{u}$ is the smallest possible compared to any other vector $\vec{w}$ in W.)

# Norm
A norm $|| \cdot ||$ on a vector space $V$ over $F = \mathbb{C}$ satisfies, for all  $u, v \in V$ and $a \in F$:  
1. $|| \cdot || : V \to F$ is a function.  
2. $||v|| \geq 0$ and $||v|| = 0$ $\iff$ $v = \vec{0}$.  
3. $||a v|| = |a| \, ||v||$.  
4. $||u + v|| \leq ||u|| + ||v||$.  
If $V$ also has a multiplication (like in the case of matrices), we also require:  
5. $||u v|| \leq ||u|| \, ||v||$.

> [!tip] Note  
> 1. If we have a **norm**, we can define **Cauchy sequences**. A sequence $u_n$ is Cauchy if  
>    $$
>    \forall \varepsilon > 0, \exists N \in \mathbb{Z}^+ \text{ such that } \forall m, n > N, \ ||u_n - u_m|| < \varepsilon.
>    $$
> 2. If **all** Cauchy sequences in $V$ converge to a point in $V$, we say that **$V$ is complete**.  
> 3. A **Banach space** is a complete **normed** space.  (==A **Banach space** is a space where you can do linear algebra and measure vector lengths, **and** where sequences that look like they should converge actually **do converge** inside the space.==)
> 4. As defined earlier, we can have a **norm** that does **not** come from an inner product.  
>    But if we **have an inner product**, we can always define a norm by  
>    $$
>    ||x|| = \sqrt{\langle x, x \rangle}.
>    $$
> 5. A **Hilbert space** is a complete **inner product** space.  
> 6. If $V$ is a normed space, we can define a **metric** (distance function) by  
>    $$
>    d(x, y) = ||x - y||.
>    $$
> 7. But we can also have a **matric** that does **not** come from a norm. A general **matric** is defined as follows...

---
# Metric

A **metric** $d$ on a set $V$ is a function that satisfies the following properties for all $x, y, z \in V$:  
1. $d : V \times V \to \mathbb{R}$ is a function.  
2. **Symmetry:** $d(x, y) = d(y, x)$.  
3. **Triangle inequality:** $d(x, z) \leq d(x, y) + d(y, z)$.  
4. **Non-negativity and definiteness:** $d(x, y) \geq 0$ and $d(x, y) = 0$ if and only if $x = y$.  
Basically: if you define your own custom "distance", it has to follow these rules to be a **metric**.

---
# Linear transformation

Let $V$, $W$ be two vector spaces over a common field $\mathbb{F}$. A **linear transformation** $T$ from $V$ to $W$ satisfies the following for all $u, v \in V$ and $a \in \mathbb{F}$
1. $T : V \to W$ is a function.  
2. **Additivity:** $T(u + v) = T(u) + T(v)$.  
3. **Homogeneity (Scalar multiplication):** $T(au) = aT(u)$.  
If all are correct for a transformation, its a linear transformation.
>[!tip] Theorem
>1. $T(\vec{0})=\vec{0}$
>2.  $T(\vec{-u}) = -T(\vec{u})$

> [!info] Kernel and Range of a Linear Transformation  
> Let $T : V \to W$ be a **linear transformation** over the field $\mathbb{F}$.
> 1. The **kernel** of $T$ is  
>    $$
>    \ker T = \{ u \in V \mid T(u) = 0 \}
>    $$
>    It consists of all vectors in $V$ that map to the zero vector in $W$. (Its like when there is $x\vec{v}$ ,set of all the values which transform v to 0 is the kernel.)
> 2. The **range** of $T$ is  
>    $$
>    \operatorname{ran} T = \{ T(u) \mid u \in V \}
>    $$
>    It consists of all vectors in $W$ that are images of vectors in $V$ under $T$. (Its like the range for which transformation T() can reach.)

> [!tip] Rank-Nullity Properties  
> Let $T : V \to W$ be a **linear transformation** over the field $\mathbb{F}$.
> 1. $\ker T$ is a **subspace** of $V$.
> 2. $\operatorname{ran} T$ is a **subspace** of $W$.
> 
> We define:
> - **Nullity** of $T$:  
>   $$
>   \operatorname{null} T = \dim(\ker T)
>   $$
> - **Rank** of $T$:  
>   $$
>   \operatorname{rank} T = \dim(\operatorname{ran} T)
>   $$


> [!theorem] Rank–Nullity Theorem  
> Let $T : V \to W$ be a linear transformation between finite-dimensional vector spaces over a field $\mathbb{F}$. Then:
> $$
> \operatorname{null} T + \operatorname{rank} T = \dim V
> $$
> This theorem expresses that the dimension of the domain $V$ is the sum of the dimensions of the kernel and t

>[!note] Complete norm space
>A **complete normed space** is a vector space **with a norm** where **every Cauchy sequence converges to a point inside the space**.
This is called a **Banach space**.

---
# Matrix of a Linear Transformation

Let $T : V \to W$ be a linear transformation over a field $F$, and let $\{u_i\}_{i=1}^n$ and $\{w_j\}_{j=1}^m$ be ordered bases of $V$ and $W$, respectively.
Then, the matrix $A \in F^{m \times n}$, where the columns of $A$ are the coordinate vectors of $T(u_i)$ expressed in the basis $\{w_j\}$, is called the **matrix of $T$** with respect to the bases $\{u_i\}$ and $\{w_j\}$.
That is,
$$
T(u_i) = \sum_{j=1}^m A_{ji} w_j,
$$

or in matrix notation:
$$
[T(u_1) \ \cdots \ T(u_n)] = [w_1 \ \cdots \ w_m] \cdot A.
$$
This matrix allows us to compute the transformation $T$ in terms of coordinates.
(Basically basis of V is transformed to basis of W. It is not a must, but a super useful characteristic if present.)

>[!theorem] 
>Let $(u_i)$, $(u'_i)$ and $(w_j)$, $(w'_j)$ be two ordered bases of $V$ and $W$ respectively.  
With  $(u'_i) = (u_i) P \quad \text{and} \quad (w'_j) = (w_j) Q,$ and  $$A = T_{(u_i),(w_j)}, \quad A' = T_{(u'_i),(w'_j)},$$  
>we have  $$A P = Q A' \quad \text{or equivalently} \quad A' = Q^{-1} A P.$$

---
# Eigen values and Eigen vectors
Let $T : V \to V$ be a linear transformation on a vector space over $F$.  
$\lambda \in F$ is an eigenvalue and $0 \neq v \in V$ is a corresponding eigenvector $\iff T(v) = \lambda v.$
- The eigenspace $V_\lambda$ of the eigenvalue $\lambda$ is the set of all eigenvectors corresponding to $\lambda$ together with the zero vector, i.e.,  
$$
V_\lambda = \{ v \in V \mid T(v) = \lambda v \} \cup \{0\}.
$$
- i.e. $V_\lambda = \{ v \in V \mid T(v) = \lambda v \} = \{ v \in V \mid (T - \lambda I)(v) = 0 \} = \ker(T - \lambda I),$  where $I$ is the identity linear transformation $I : V \to V$ with $I(x) = x$ for all $x \in V$.  Note that if $\lambda$ exists, $V_\lambda$ is a subspace of $V$. We call its basis elements (which are non-zero) the eigenvectors.
>[!theorem]
>- If eigen values / vectors exists then $V_{\lambda}$ is a subspace of $v$

1. Eigenvalues $\lambda$ and Eigenvectors $v$ of the matrix $A \in F^{n \times n}$ are defined to be the same as for the Linear Transformation $T : F^n \to F^n$ over $F$ defined by $T(v) = Av$ where $v \in F^n$.  
   i.e. for $A \in F^{n \times n}$, they satisfy  $$
   Av = \lambda v
   $$
   such that $\lambda \in F$ and $0 \neq v \in F^n$.

2. The eigenvalues satisfy the characteristic equation  $$
   \det(A - \lambda I) = 0.
   $$
3. $f(x) = \det(xI - A) = (-1)^n \det(A - xI)$, $x \in F$, is called the **characteristic polynomial** of $A$.

4. Matrices $A$ and $B$ are **similar** iff there exists an invertible matrix $P$ such that ,$$
   AP = PB.
   $$
>[!theorem] 
>$T_1$
>- Similar matrices have the same eigenvalues.  
>- Eigenvalues of $T : V \to V$ over $F$ and the eigenvalues of the matrix of $T$ are the same for any choice of basis.  
>- If the eigenvalues are different, then the corresponding eigenvectors are linearly independent.
>
>$T_2$
>- $\prod \lambda = \det A$: product of eigenvalues is the determinant of $A$.  
>- $\sum \lambda = \operatorname{trace} A$: sum of eigenvalues is the trace of $A$ (sum of the diagonal elements).  
>- $f(A) = 0$: matrix $A$ satisfies its own characteristic polynomial (Cayley-Hamilton theorem).

---
~={blue}Minimal polynomial=~ $g(x)$ of $A \in \mathbb{C}^{n \times n}$ satisfies:  
1. $g(x)$ is monic.  
2. $g(A) = 0$.  
3. No non-zero polynomial $h(x)$ with lesser degree satisfies $h(A) = 0$.
More below,
[[Eigen-short note#🔹 Minimal Polynomial (Informal Definition)]]

---
>[!note]
>1. ~={pink}Algebraic multiplicity =~of $\lambda$: $a_\lambda$ is the power of $(x - \lambda)$ in $f(x)$.  
>2. ~={pink}Geometric multiplicity=~ of $\lambda$: $g_\lambda = \dim V_\lambda = \dim(\ker(A - \lambda I)) = \operatorname{null}(A - \lambda I)$.  
>3. ~={pink}Minimal multiplicity=~ of $\lambda$: $m_\lambda$ is the power of $(x - \lambda)$ in $g(x)$ (the minimal polynomial).$$
a_i - g_i \ge m_i - 1 \ge 0
$$

~={cyan}More below,=~
[[More on Jordan Normal form#🧩 Algebraic vs Geometric Multiplicity]]

---
~={cyan}On diagonalizability,=~
[[Short note - (Linear algebra)#Eigenvalues, Eigenvectors, and Diagonalizability]]

---

## Some definitions

- Let $P \in \mathbb{C}^{n \times n}$ be said to be **~={blue}Unitary=~** $\iff P^H P = P P^H = I,$ i.e. $P^{-1} = P^H.$ If $P$ has orthonormal columns, then $P$ is Unitary.
- $A \in \mathbb{C}^{n \times n}$ is **Positive Definite (PD)** $\iff x^H A x > 0 \quad \text{for all } x \neq 0.$
- 
---
# [[Jordan-Normal Form]]

---
