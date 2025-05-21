# Identities of Regular Languages

- $\emptyset \cup R = R$
- $\emptyset R \cup R\emptyset = \emptyset$
- $\emptyset R = R\emptyset = \emptyset$
- $\Lambda^* = \Lambda$, and $\emptyset^* = \Lambda$
- $R \cup R = R$
- $R^* R^* = R^*$
- $R R^* = R^* R$
- $(R^*)^* = R^*$
- $\Lambda \cup R R^* = \Lambda \cup R^* R = R^*$
- $(PQ)^* P = P (QP)^*$
- $(P \cup Q)^* = (P^* Q^*)^* = (P^* \cup Q^*)^*$
- $(P \cup Q) R = P R \cup Q R$, and $R (P \cup Q) = R P \cup R Q$

# Arden's Theorem

If $P$ and $Q$ are two regular expressions over $\Sigma$, and if $P$ does not contain $\Lambda$,  
then the equation in $R$ given by:

$$
R = Q \cup R P
$$

has a unique solution:

$$
R = Q P^*
$$
