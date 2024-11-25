# TP-2 : Linear algebra with matrices and vectors

## Ex 1
### Part 1 : Practice with Numbers
If my writing is too bad to read, please reach out to me, and I'll happily clarify everything !
Problem 1 to 7 : 
![Ex1 Part1 1-7](images\Ex2\Ex1Part1_1-7.jpeg)
### Part 2 : Matrix type
1. Square matrix
   1. A square matrix has the same number of columns as it has of rows. 
2. Column matrix
   1. A column matrix has dimension nx1, so it only has one column. It looks vertical => Tall
3. Row matrix
   1. A row matrix has dimension 1xm, so it has many columns but only one row => Wide
4. Identity matrix
   1. The identity matrix has its diagonal element all at 1 (when n = m), and the rest of its element at 0 (when n =/= m). It is **always** square. 
   2. In a way, it is a sort of permuation matrix.
   3. If we multiply it with another vector, we get the vector itself. 
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

### Part 3 : Some matrix Operations

For

1. $\frac{1}{n} \mathbf{1}\mathbf{1}^{\mathrm{T}}$
   
   This result in a matrix with dimension nxn, assuming that the 1-vectors have n instances, where all elements are $\frac{1}{n}$

2. $\frac{1}{n} \mathbf{1}\mathbf{1}^{\mathrm{T}}\mathbf{x}$
   
   Here, we're doing a multiplication between the nxn matrix $\frac{1}{n} \mathbf{1}\mathbf{1}^{\mathrm{T}}$ and one nx1 vector $x$. This result in a nx1 vector where every every element $x_i$ is the mean of $x$. I'll be calling this vector the constant mean of $\mathbf{x}$. 

3. $\mathbf{x} - \frac{1}{n} \mathbf{1} \mathbf{1}^{\mathrm{T}} \mathbf{x}$
   
   Here, we'll be taking our constant mean of $\mathbf{x}$ vector we computed earlier, and substracting it from the base $\mathbf{x}$. In essence, it means that for each element $\mathbf{x}_i$, we substract $\mu_\mathbf{x}$. This result in a vector nx1 based on $\mathbf{x}$ that has been demeaned, so it has a new mean of 0. 

4. $\left[\mathbf{I} - \frac{1}{n} \mathbf{1} \mathbf{1}^{\mathrm{T}} \right] \mathbf{x}$
   
   Here, we take out $\frac{1}{n} \mathbf{1}\mathbf{1}^{\mathrm{T}}$ nxn matrix and substract it from the nxn identity matrix $\mathbf{I}$. This result in a new nxn matrix where every element on the diagonal is $1-\frac{1}{n}$, and every other element is $\frac{1}{n}$. 
   
   Then, we multiply the vector $\mathbf{x}$ by this new matrix we just go. This result in a new n-vector $\mathbf{x}'$ where every element is the distance to $\mu_\mathbf{x}$. So, if $\mu_\mathbf{x} = 2$ and $\mathbf{x}_1 = 1$, then $\mathbf{x}'_1 = -1$, because $\mathbf{x}_1$ is one below $\mu_\mathbf{x}$. 

   This vector has a mean of 0, and is also centered around the mean. 

5. $\left[\mathbf{I} - \frac{1}{n} \mathbf{1} \mathbf{1}^{\mathrm{T}} \right] \mathbf{1}$
   
   Instead of taking the vector $\mathbf{x}$ here, we use the 1-vector. Because this vector is already constitued by its means (all elements are 1, the mean is 1), the resulting vector $\mathbf{x}'$ is the $\mathbf{0}$-vector. 

   This is the same thing to what we applied in the 4. exercice, except this time the vector was a constant vector. Had we used any other constant vector, we would have also got the $\mathbf{0}$-vector. 

6. $\mathbf{M} = \mathbf{I} - \frac{1}{n} \mathbf{1} \mathbf{1}^{\mathrm{T}}$

   Here, the matrix $\mathbf{M}$ is the matrix we used in the above 4 and 5 exercice. It has dimension nxn, and its content is : 
   - On the diagonal, all the element are $1-\frac{1}{n}$
   - On the rest of the element, all the elements are $-\frac{1}{n}$
   
   We've seen that one of its usage when multiplying a vector is to center it around its mean while preserving its variance. 

7. $\mathbf{1}^\mathrm{T}\mathbf{x}$
   
   This result in a scalar that is equal to the sum of all the element of $\mathbf{x}$

8. $\mathbf{1}^\mathrm{T}\mathbf{Mx}$

   This result in 0. We've established earlier that using this $\mathbf{M}$ matrix result in a vector whos mean is centered around 0. When adding all the elements together, we thus get 0. 

9. $\mathbf{MM}$
   
   Here, we're doing matrix multiplication of $\mathbf{M}$ with itself. However, one of the property of this matrix is that is is idempotent, meaning once it is applied once, applying it again does nothing. As such, $\mathbf{MM} = \mathbf{M}$. Extrapolating, $\mathbf{MMx} = \mathbf{Mx}$.
   
   To understand this, we can think about how, once a vector is projected onto something by the M matrix, re-applying the matrix does not do anything : the vector is already where it needs to be. 

   This idempotency is a property of all projection Matrix, and is proved [here](https://statproofbook.github.io/P/mlr-idem.html)

10. $\mathbf{x}^\mathrm{T}\mathbf{x}$
    
      This is the standard formula for taking the dot product of $\mathbf{x}$ with itself. The result is a scalar equal to the sum of all the element squared of $\mathbf{x}$. This is also equal to the norm squared of $\mathbf{x}$.

11. $(\mathbf{M})^\mathrm{T}(\mathbf{M})$
    
      Here, we're testing exercise 9 again, but this time with a transposed $\mathbf{M}$ matrix. However, $\mathbf{M}$ is symetric : the element above and below the diagonal are all the same, so transposing it does nothing, functionnaly speaking : $(\mathbf{M})^\mathrm{T} = \mathbf{M}$.

   As such, $(\mathbf{M})^\mathrm{T}(\mathbf{M}) = \mathbf{M}$ still. 

12. $\mathbf{x}^\mathrm{T}\mathbf{y}$
    
      This is the formula to take the dot product with two vector. Assuming both vector have the same number of element, this result in a scalar that  is the sum of the element-wise addition of the two vector. 

13. $(\mathbf{M} \mathbf{x})^\top (\mathbf{M} \mathbf{y})$

      In this equation, we're getting close to calculating the covariance between $\mathbf{x}$ and $\mathbf{y}$. To remember, the equation of the covariance is :

      $$\sigma_{xy} = \frac{1}{n-1} \sum_{i=1}^n (x_i - \mu_x)(y_i - \mu_y)$$

      Here, by taking $\mathbf{Mx}$, we've effectively arrived to $(x_i - \mu_x)$. By then taking the dot product between those two centered vector $\mathbf{x}$ and $\mathbf{y}$, we're effectively computing the sum that the part $\sum_{i=1}^n (x_i - \mu_x)(y_i - \mu_y)$ computes. It is a scalar. 

      We still $\frac{1}{n-1}$ to compute the covariance however. 

14. $\frac{1}{n-1}(\mathbf{M} \mathbf{x})^\top (\mathbf{M} \mathbf{y})$

      This is the covariance formula for $\mathbf{x}$ and $\mathbf{y}$. We've seen in the 13. exercise that $\mathbf{Mx}^\top\mathbf{My} = \sum_{i=1}^n (x_i - \mu_x)(y_i - \mu_y)$, and that all we needed what the first $\frac{1}{n-1}$ factor at the beginning. 

15. $\mathbf{MX}$

      We've established that $\mathbf{M}$ was a nxn matrix, and we know that $\mathbf{X}$ is a nxk matrix. As such, the result of $\mathbf{MX}$ will be a nxk matrix. 

      Given that applying $\mathbf{Mx}$ transform $\mathbf{x}$ into its demeaned version, it is nice to know that $\mathbf{MX}$ is pretty straightforward : it demean every columns of $\mathbf{X}$ by its mean, effectively demeaning the entire matrix. 

      We can think of it like that. 
      $$\mathbf{X} = \set{\mathbf{x_1, x_2,..., x_k}}\$$
      where every $\mathbf{x_i}$ is a column/feature vector. Here, $\mathbf{MX} = \set{\mathbf{Mx_1, Mx_2,..., Mx_k}}$. And we know that $\mathbf{Mx}$ is simply $\mathbf{x}$ demeaned.  


16. $\left( MX \right)^\top \left( MX \right)$

      Here, we'll be multiplying the demeaned matrix by itself. We've seen that $\mathbf{MX}$ produces a nxk matrix with each column demneaed matrix. Transposing the first part of the formula mean making a kxn ° nxk matrice multiplication, resulting in a final kxk matrice. 

      This is close to resulting in the covariance matrix, but it's once again missing that final $\frac{1}{1-n}$ factor to get there. What we have here is a square matrix where each element is the sum of the deviation between each pair of $i,j$ features, where $i,j = 1 ... k$. 

      - The diagonal entries (when $i=j$) represent the sum of squared deviations from the mean for each column $i,j$.
      - The off-diagonal entries (when $i \neq j$) represent the sum of the product of deviations from the mean between each pair of columns $i,j$.
      
      If we wanted to get the covariance matrix, we'd need to factor the result by $\frac{1}{n-1}$ : $\frac{1}{n-1}\left( MX \right)^\top \left( MX \right)$. This would result in a symetrical, square, kxk matrix where the diagonal are 1 (since the pair $i,j$ of columns are actually the same thing, and thus have a perfect covariance.), while the other entries would be the covariance between each pair of $i,j$ features. 


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

$$\beta_1\begin{bmatrix}
1 \\2

\end{bmatrix}
=
-\begin{bmatrix}
3 \\4

\end{bmatrix}$$

(Note : this above notation is just the first equation re-written)

Here, it's obvious that there are no $\beta$ value that make this equation true. So, the set of vector is linearly independent. This becomes much harder to do with more, bigger vectors. I'll do the exercice b) with a standard method. 

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
![exercice 2 Part 3 b](images\Ex2\Ex2Part3_b.jpeg)
So : 
$$\{\alpha, \gamma, \delta\} = \{-1, -1, 1\}$$
---

Part c : 
![exercice 2 Part 3 c](images\Ex2\Ex2Part3_c.jpeg)

$$\mathbb{c}_1\mathbb{w} + \mathbb{c}_2\mathbb{x} + \mathbb{c}_3\mathbb{y} = \mathbb{z} \iff \mathbb{c}_1 = 1, \mathbb{c}_2 = -1, \mathbb{c}_3 = 1$$

Since there exist an answer other than having all $\mathbb{c}$ to 0, the set $\set{w,x,y,z}$ is linearly dependent.

---

### Part 4

![exercice 2 Part 4](images\Ex2\Ex2Part4.jpeg)

$\{ \mathbf{u}, \mathbf{v}, \mathbf{w} \}$ are linearly dependent when $\lambda = \{ 0, -\sqrt{2}, \sqrt{2} \}.$

### Part 5

![Ex2 part 5](images\Ex2\Ex2Part5.jpeg)

Set $\{\mathbf{u}, \mathbf{v}, \mathbf{w}\}$ is a basis for $\mathbb{R^3}$ when $\mathbb{c}\neq -2$

### Part 6

![Ex2 part 6](images\Ex2\Ex2Part6.jpeg)

Set $\{\mathbf{u}, \mathbf{v}, \mathbf{w}\}$ is a basis for $\mathbb{R^3}$ when $\mathbb{c}\neq -3$


### Part 7

![Ex2 part 7](images\Ex2\Ex2Part7.jpeg)

In the basis of $\set{x,y,z}$, $\mathbb{w}$ can be exprimed as $\left( \frac{3}{2}, -\frac{1}{2}, \frac{1}{2} \right)$

### Part 8
First part, converting to orthonormal basis : 
![Ex2 part 8 a](images\Ex2\Ex2Part8_a.jpeg)

So : 

$$
\mathbf{x}' = \begin{bmatrix}
\frac{1}{\sqrt{3}} \\
\frac{1}{\sqrt{3}} \\
\frac{1}{\sqrt{3}}
\end{bmatrix}, \quad
\mathbf{y}' = \begin{bmatrix}
\frac{-1}{\sqrt{2}} \\
\frac{1}{\sqrt{2}} \\
0
\end{bmatrix}, \quad
\mathbf{z}' = \begin{bmatrix}
\frac{1}{\sqrt{6}} \\
\frac{1}{\sqrt{6}} \\
-\frac{2}{\sqrt{6}}
\end{bmatrix}.
$$

Second part : find w using the orthonormal basis. 
Since we computed the ortonormal basis, we can find the coef to $\mathbb{w}$ by simply taking the dot product between $\mathbb{w}$ and $\mathbb{x'}$, and do so for the rest for the vectors as well. The product is the coef for $\mathbb{x'}$ to multiply it to obtain $\mathbb{w}$.

![Ex2 part 8 b](images\Ex2\Ex2Part8_b.jpeg)

So : 
$$
\mathbf{w} = a'_1 \mathbf{x}' + a'_2 \mathbf{y}' + a'_3 \mathbf{z}' \iff \set{a'_1,a'_2,a'_3} = \set{\frac{5}{\sqrt{3}}, -\sqrt{2}, \sqrt{\frac{2}{3}}}
$$


