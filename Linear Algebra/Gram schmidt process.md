> How can we make an orthonormal basis from any set that forms a basis?
---
- (original basis) $v_1, v_2, \ldots, v_n \rightarrow u_1, u_2, \ldots, u_n$ (orthogonal basis)  
	1. $u_1 = v_1$
	2. $u_2 = v_2 - \frac{\langle v_2, u_1 \rangle}{\lVert u_1 \rVert^2} u_1$
	3. $u_3 = v_3 - \frac{\langle v_3, u_1 \rangle}{\lVert u_1 \rVert^2} u_1 - \frac{\langle v_3, u_2 \rangle}{\lVert u_2 \rVert^2} u_2$
	$$u_k = v_k - \sum_{j=1}^{k-1} \frac{\langle v_k, u_j \rangle}{\lVert u_j \rVert^2} u_j$$
- We take apart the new vector we get by the previously founded orthogonal vectors to get the new orthogonal vector which will be orthogonal to all of the previously founded.
- `Note here` , the first vector is taken as a orthogonal vector.
- The ones come out by this are orthogonal, not orthonormal. To get the orthonormal vectors divide each vector by its length.