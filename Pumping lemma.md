# For Regular languages
- ==It cannot prove that a language is Regualr==
>[!note]
>If L is a regular language, then L has a Pumping length 'P' such that any string 'S' where |S| $\ge$ P may be divided into 3 parts S = xyz such that the following conditions must be true.
>	1. $xy^{i}z \in L$ for every $i \ge 0$
>	2. $|y| > 0$
>	3. $|xy| \le P$

To prove that a language is not regular follow the below steps,
(We prove using contradiction)
- Assume L is regular
- It has to have a pumping length (P)
- All strings longer than P can be pumped $|S| \ge P$
- Now find a string 'S' in L such that  $|S| \ge P$
- Divides S into xyz
- Show that $xy^{i}z \notin L$ for some i
- Then consider all ways that S can be divided into x y z
- Show that none of these can satisfy all the 3 pumping conditions at the same time.
- S cannot be pumped --> CONTRADICTION
Ex:
A = $\set{ a^{n}b^{n}| n \ge 0}$ 
Assume A is regular,
Pumping length = P
S = $a^{p}b^{p}$
S = aaaaaaabbbbbbb , (Assume P = 7)

**Case 01**:
The Y is in the 'a' part
aayabbbbbbb = xyz

$xy^2 z$ = aa*aaaaaaaa*abbbbbbb


**Case 02**:
The y is in the 'b' part
aaaaaaabbyb = xyz

$xy^2 z$ = aaaaaaabb**bbbbbbbb**b

**Case 03**:
The y is in the 'a' and 'b' part
aaaaaybbbbb = xyz

$xy^2 z$ = aaaaa**aabbaabb**bbbbbb

There for xyz cannot be pumped
# For CFL
- Is used to prove that a language is NOT context free.
>[!note]
>If L is a regular language, then L has a Pumping length 'P' such that any string 'S' where |S| $\ge$ P may be divided into 5 parts S = uvxyz such that the following conditions must be true.
>	1. $uv^{i}xy^{i}z \in L$ for every $i \ge 0$
>	2. $|vy| > 0$
>	3. $|vxy| \le P$

- Assume L is regular
- It has to have a pumping length (P)
- All strings longer than P can be pumped $|S| \ge P$
- Now find a string 'S' in L such that  $|S| \ge P$
- Divides S into uvxyz
- Show that $uv^{i}xy^{i}z\notin L$ for some i
- Then consider all ways that S can be divided into u v x y z
- Show that none of these can satisfy all the 3 pumping conditions at the same time.
- S cannot be pumped --> CONTRADICTION