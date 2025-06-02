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
- 