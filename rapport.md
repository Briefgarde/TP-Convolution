# TP-2 : Linear algebra with matrices and vectors

## Ex 1
### Part 1 : 
If my writing is too bad to read, please reach out to me, and I'll happily clarify everything !
Problem 1 to 7 : 
![Ex1 Part1 1-7](images\Ex2\Ex1Part1_1-7.jpeg)
### Part 2
1. Square matrix
   1. A square matrix has the same number of columns as it has of rows. 
2. Column matrix
   1. A column matrix has dimension nx1, so it only has one column. It looks vertical => Tall
3. Row matrix
   1. A row matrix has dimension 1xm, so it has many columns but only one row => Wide
4. Identity matrix
   1. The identity matrix has its diagonal element all at 1 (when n = m), and the rest of its element at 0 (when n =/= m). It is **always** square. 
   2. In a way, it is a sort of permuation matrix.
5. Diagonal matrix
   1. The diagonal matrix is similar to the identity matrix, but inversed : when n=m (its diagonal), the element is any number but 0. When not, the number is 0.
6. symmetric matrix
   1. A symmetric matrix has a symmetry access along its diagonal (when n=m).
7. Permutation matrix
   1. A permuation matrix is a matrix that has only one 1 per row **AND** per column. 
   2. The rest of the elements are 0. 
   3. It is always square
8. Upper triangular matrix
   1. An upper triangular matrix is a matrixe where the element below the diagonal (when n>m) are all 0. 
   2. The diagonal itself can be any number.
9.  Lower triangular matrix
    1.  A lower triangular matrix is a matrixe where the element above (when n<m) the diagonal are all 0. 


## Ex-2
### Part 1 : Definition of linear dependance
The definition of linear dependence for a set of vectors can be written as : 
$$\beta_1 \alpha_1 + \cdots + \beta_k \alpha_k = 0$$
where $\{\alpha_1, \alpha_2, \dots, \alpha_k\}$ are all n-vectors. In the above notation, the set of vectors $\alpha$ is linearly dependant if there are solutions for the notation to be corret other than by setting all $\beta=0$. 

---
Is $\{0, 0\}$ linearly dependent ? 

We can multiply the $\{0, 0\}$ vector by any $\beta \in \mathbb{R}$ and still get a correct value. Example : 

$$\beta \cdot \begin{bmatrix} 0 \\ 0 \end{bmatrix} = \vec{0}$$
Correct values include : 
$$1 \cdot \begin{bmatrix} 0 \\ 0 \end{bmatrix} = \vec{0}, \quad 2 \cdot \begin{bmatrix} 0 \\ 0 \end{bmatrix} = \vec{0}, \quad -1 \cdot \begin{bmatrix} 0 \\ 0 \end{bmatrix} = \vec{0}.$$

Since the set of possible answers $\beta$ is more than just 0, it is linearly dependent.

---

Are $\{1, 0\}$ and $\{2, 10\}$ linearly dependent ?

Since $\{2, 10\} = 2 \{1, 5\}$, they are linearly dependent. 

---
![exercice c](images\Ex2\Ex2Part1_c.jpeg)
Note : When checking for linear (in)dependence, we do not need to write the $\vec{0}$ target vector inside of the matrice, because it would always remain 0 no matter what. So, we do not need to build an augmented matrice. The process remain the exact same nonetheless. 

---
![exercice d](images\Ex2\Ex2Part1_d.jpeg)


---

### Part 2 : Définition of linear independence

A set of vector $\alpha$ are linearly independent if the only way to make this equation hold is by setting all $\beta$ to 0 : 

$$\beta_1 \alpha_1 + \cdots + \beta_k \alpha_k = 0$$

If at least one $\beta_i$ is not 0, and the equation still hold, then the set is linearly dependent. 

---
Ex a) Show that the vectors (1,2) and (3,4) are linearly independent.

For small quantities of small vectors, one easy test is to see if we can obtain one vector by multiplying a set of the others : 

$$\beta\begin{bmatrix}
1 \\2

\end{bmatrix}
=
-\begin{bmatrix}
3 \\4

\end{bmatrix}$$

(Note : this above notation is just the first equation re-written)

Here, it's obvious that there are no $\beta$ value that make this equation true. So. the set of vector is linearly independent. This becomes much harder to do with more, bigger vectors. I'll do the exercice b) with a standard method. 

---
![exercice d](images\Ex2\Ex2Part2_b.jpeg)

---

### Part 3

 Let w =(1,1,0,0),x = (1,0,1,0),y = (0,0,1,1), and z = (0,1,0,1).

Part a : 
![exercice 2 Part 3 a](images\Ex2\Ex2Part3_a.jpeg)

So : 

$$\mathbf{u} \in \text{span}\{\mathbf{w}, \mathbf{x}, \mathbf{y}, \mathbf{z}\} \iff a = 4$$
$$\mathbf{u} \notin \text{span}\{\mathbf{w}, \mathbf{x}, \mathbf{y}, \mathbf{z}\} \iff a \neq 4$$

---
Part b

---

Part c : 
![exercice 2 Part 3 c](images\Ex2\Ex2Part3_c.jpeg)

$$\mathbb{c}_1\mathbb{w} + \mathbb{c}_2\mathbb{x} + \mathbb{c}_3\mathbb{y} = \mathbb{z} \iff \mathbb{c}_1 = 1, \mathbb{c}_2 = -1, \mathbb{c}_3 = 1$$

Since there exist an answer other than having all $\mathbb{c}$ to 0, the set $\set{w,x,y,z}$ is linearly dependent