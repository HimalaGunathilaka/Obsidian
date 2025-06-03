# Group
- A set G together with a binary operation $*$ (often called multiplication or addition) is called a **group**. (G,$*$)
- It should satisfy following properties,
	1. G not equal null
	2. $G \times G \rightarrow G$ is a function. (All inputs are accountable, (Explain what is accountable here))
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
- Defined as $(F, \operator1,\operator2)$
- A field has few properties, 
	1. $(F,+)$ is an abelian group
	2. $(F-\set{e_+},*)$ is an abelian group
	3.  $F \times F \rightarrow F$ is a function. ($\times$ operator is closed)
	4. $\forall a,b,c \in F; a*(b+c) = a*b + a*c$ ; (Distributive law)
>Note
- A field should have at least two elements. (Identities of the above abelian groups.)
- 
>Theorems
- Let $(F,+,*)$ be a field and $a \in F$, 
	1. $0*a=0$
	2. $0 \ne 1$
- ==Here the underscritpt number in the operator means that it uses the set of that number modules values. I mean just that the operator result must be the modulas of p==
	- $F_p = \set{0,1,2,3,4, ..., p-1}$ , p is prime, the ($F_p, +_p,*_p$) is a field.
	- F is a finite field $\iff$ the (number of elements in F), $|{F}| = p^{k}$ , p is prime, $k \in \mathbb{Z}^+$ 

---
# Vector space
- $(V,\#,*)$ over $(F,+,.)$ is a vector space $\iff$
	1. $(V,\#)$ is an abelian group
	2. $(F,+,.)$ is a field
	3. $F \times V \rightarrow V$ ; is a function
	4.  $\forall a,b \in F;\forall v \in V; (a+b)*v = a.v + b.v$ 
	5. $\forall a,b \in F;\forall v,u \in V; a.(v\#u) = a.v \# a.u$ 
	6. $\forall a,b \in F;\forall v \in V; (a.b)*v = a*(b.v)$
>Confusing symbol explanation
- $(F, +, \cdot)$ is a field:
    - $+$ is field addition: $a + b$
    - $\cdot$ is field multiplication: $a \cdot b$
- $(V, \#, *)$ is a vector space over $F$:
    - $\#$ is vector addition: $\vec{u} \# \vec{v}$
    - $*$ is scalar multiplication: $a * \vec{v}$ where $a \in F$, $\vec{v} \in V$
---
# Subspace
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

>Theorem
1. If $B' \subseteq B$, then $\text{Span}(B') \subseteq \text{Span}(B) \subseteq V$  
2. $\vec{0} \in \text{Span}(B)$  
3. $\text{Span}(B)$ is a subspace of $V$  
4. $\text{Span}(B)$ is the smallest subspace of $V$ that contains $B$
- If $B = \{x_1, x_2, \dots, x_n\}$ is linearly dependent, then at least one element of $B$ can be written as a linear combination of the others.
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
In other words, Hamel basis has infinite elements, there for its fine to take only fininte number of elements.

~={cyan}**"Properly contained"** (also called **proper subset**) means that one set is **strictly inside** another set — it is **contained** but **not equal**.=~

>Definition
- A collection of sets $\mathcal{C}$ is called a **chain** if and only if for all $A, B \in \mathcal{C}$, either $A \subseteq B$ or $B \subseteq A$.
- An element $M$ of a collection of sets $\mathcal{D}$ is called **maximal** if and only if $M$ is not properly contained in any element of $\mathcal{D}$.
>Theorems
- ~={green}Zorn’s Lemma=~ : If for every chain $\mathcal{C}$ in a collection $\mathcal{D}$, there exists an element $U \in \mathcal{D}$ such that $U$ contains every member of $\mathcal{C}$ (i.e., $U$ is an upper bound of $\mathcal{C}$), then $\mathcal{D}$ has a maximal element.
- Every vector space has a Hamal Basis.