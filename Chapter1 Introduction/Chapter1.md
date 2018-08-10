### Problem 1.1

Consider the sum-of-squares error function given by (1.2) in which the function $y(x,\mathbf{w})$ is given by the polynomial (1.1). Show that the coefficients $\mathbf{w} = \{ w_i\}$ that minimize this error function are given by the solution to the following set of linear equations
$$
\sum_{j=0} ^M A_{ij} w_j  = T_i
$$
where
$$
A_{ij} = \sum_{n=1}^N (x_n)^{i+j} , T_i = \sum_{n=1}^N(x_n)^i t_n.
$$
Here a suffix $i$ or $j$ denotes the index of a component, whereas $(x)^i$ denotes $x$ raised to the power of $i$.

Appendix: equation (1.2):
$$
\label{eq:1_2}
E(\mathbf{w}) = \frac{1}{2} \sum_{n=1}^N\left \{ y (x_n,\mathbf{w}) - t_n \right \}^2
$$
equation (1.1):
$$
\label{eq:1_1}
y(x,\mathbf{w} ) = w _0 + w_1 x + w_2 x^2 +\cdots  + w_M x^M  = \sum_{j=0}^M w_j x^j
$$

#### Solution:

Substitute equation $\ref{eq:1_1}$ into $\ref{eq:1_2}$，we get 
$$
E(\mathbf{w}) = \frac{1}{2} \sum_{n=1}^N\left \{\sum_{j=0}^M w_j x_n^j - t_n \right \}^2.
$$
So, the partial derivative of $w_i$ w.r.t. $E(\mathbf{w})$ is
$$
\frac{\partial E}{\partial w_j} = \sum_{n=1}^N\left \{\sum_{j=0}^M w_j x^j - t_n \right \}x_n^i \\
=\sum_{n=1}^N \sum_{j=0}^M w_j x_n^j x_n^i  - \sum_{n=1}^N t_n x_n^i\\
= \sum_{j=0}^M w_j \sum_{n=1}^N  (x_n)^{i+j}  -  \sum_{n=1}^N t_n (x_n)^i  =  \sum_{j=0}^M w_j A_{ij} - T_i.
$$
Minimizing the sum-of-squares error requires it equal to zero, for any $i​$. Then
$$
\sum_{j=0} ^M A_{ij} w_j  = T_i.
$$

### Problem 1.2

Write down the set of coupled linear equations, analogous to (1.122), satisfied by the coefficients $w_i$ which minimize the regularized sum-of-squares error function given by (1.4).

Appendix: eq(1.122):
$$
\sum_{j=0} ^M A_{ij} w_j  = T_i
$$
eq(1.4):
$$
\tilde{E}(\mathbf{w}) = \frac{1}{2} \sum_{n=1}^N \left \{ y (x_n,\mathbf{w}) - t_n \right \}^2 + \frac{\lambda}{2} \parallel \mathbf{w} \parallel ^2
$$

#### Solution:

the partial derivative of $w_i$ w.r.t. $\tilde{E}(\mathbf{w})$ is
$$
\frac{\partial \tilde{E} }{\partial w_j} = \sum_{j=0}^M w_j A_{ij} - T_i   + \lambda \parallel \mathbf{w} \parallel \frac{w_i}{ \parallel \mathbf{w} \parallel} \\
  =   \sum_{j=0}^M w_j A_{ij} - T_i  + \lambda w_i. 
$$
Let it be $0$, then we have 
$$
\sum_{j=0}^M w_j A_{ij}+ \lambda w_i  = T_i.
$$

### Problem 1.3

Suppose that we have three colored boxes $r$ (red), $b$ (blue), and $g$ (green). Box $r$ contains $3$ apples, $4$ oranges, and $3$ limes, box $b$ contains $1$ apple, $1$ orange, and $0$ limes, and box $g$ contains $3$ apples, $3$ oranges, and $4$ limes. If a box is chosen at random with probabilities $p(r) = 0.2$, $p(b) = 0.2$, $p(g) = 0.6$, and a piece of fruit is removed from the box (with equal probability of selecting any of the items in the box), then what is the probability of selecting an apple? If we observe that the selected fruit is in fact an orange, what is the probability that it came from the green box?

#### Solution:

Denote $X$ as the random variable represents the selected fruit. Then 
$$
p(X=a) = \sum_{c \in \{ r,g,b \}} p(X=a |B =c ) p(B = c)\\
 = 0.2 *0.3 + 0.2* 0.5 + 0.6*0.3  = 0.34,
$$
and
$$
p(B=g|X= o )  =  \frac{p(X =o |B=g) p(B=g)}{p(X=o)},
$$
where
$$
p(X=o) = \sum_{c \in \{ r,g,b \}} p(X=o |B =c ) p(B = c)\\
 = 0.2 *0.4 + 0.2* 0.5 + 0.6*0.3  = 0.36,
$$
so 
$$
p(B=g|X= o ) = \frac{0.6*0.3}{0.36} = 0.5
$$
