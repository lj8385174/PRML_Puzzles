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

### Problem 1.4

Consider a probability density $p_x(x)$ defined over a continuous variable $x$, and suppose that we make a nonlinear change of variable using $x = g(y)$, so that the density transforms according to (1.27). By differentiating (1.27), show that the location $\hat{y}$ of the maximum of the density in $y$ is not in general related to the location $\hat{x}$ of the maximum of the density over $x$ by the simple functional relation $\hat{x} = g(\hat{y})$ as a consequence of the Jacobian factor. This shows that the maximum of a probability density (in contrast to a simple function) is dependent on the choice of variable. Verify that, in the case of a linear transformation, the location of the maximum transforms in the same way as the variable itself.

Appendix: eq 1.27:

$$
\label{eq:1_27}
p_y(y)   = p_x(x) \left| \frac{\text{d}x} {\text{d}y}\right| = p_x(g(y))|g^\prime(y)|.
$$

#### Solution:

Differentiating equation ($\ref{eq:1_27}$)，we have 
$$
\frac{\text{d} p_y(y)}{\text{d}y}  = \frac{\text{d} p_x(x)}{\text{d}x} \frac{\text{d}x} {\text{d}y}|g^\prime(y)| +  p_x(g(y)) \frac{\text{}d |g^\prime(y)|}{\text{d}y}.
$$

Assume $g^\prime(y) \geq 0$, it becomes
$$
\frac{\text{d} p_y(y)}{\text{d}y}  = \frac{\text{d} p_x(x)}{\text{d}x} (g^\prime(y))^2 + p_x(g(y)) g^{\prime\prime}(y)
$$
It can't ensure when $\frac{\text{d} p_x(x)}{\text{d}x} = 0$  causes $\frac{\text{d} p_y(y)}{\text{d}y} =0 $. However, if $g(y)$ is a linear transformation, then $g^{\prime\prime}(y)=0$. In this case, if $\frac{\text{d} p_x(x)}{\text{d}x} = 0$, then  $\frac{\text{d} p_y(y)}{\text{d}y} =0 $.

### Problem 1.5

Using the definition (1.38) show that $\text{var}[f(x)]$ satisfies (1.39).

Appendix: eq 1.38:
$$
\text{var}[f] = \mathbb{E} \left [ (f(x) − \mathbb{E}[f(x)])^2  \right]
$$
eq 1.39:
$$
\text{var}[f] = \mathbb{E} \left [ (f(x)^2 \right]− \mathbb{E}[f(x)]^2
$$

#### Solution:

It trivial that expectation operator is linear, thus 
$$
\text{var}[f] = \mathbb{E} \left [ (f(x) − \mathbb{E}[f(x)])^2  \right] =\mathbb{E} \left [ f(x)^2 +  \mathbb{E}[f(x)]^2 -2f(x)\mathbb{E}[f(x)] \right]\\
= \mathbb{E} \left [ (f(x)^2 \right] + \mathbb{E}[\mathbb{E}[f(x)]^2] -2  \mathbb{E}[f(x)]^2 -2\mathbb{E}[f(x)] \mathbb{E}[f(x)] \\
= \mathbb{E} \left [ (f(x)^2 \right] - \mathbb{E}[f(x)]^2
$$

### Problem 1.6

Show that if two variables $x$ and $y$ are independent, then their covariance is zero.

#### Solution:

According to the definition of covariance, we have
$$
\text{Cov}(x,y) = \mathbb{E}\left[  (x -\mathbb{E}[x]) (y - \mathbb{E}[y])\right]\\
= \iint (x-\mathbb{E}[x])(y - \mathbb{E}[y])  p(x,y) \text{d}x \text{d}y
$$
Since $x$ and $y$ are independent, $p(x,y) = p(x) p(y)$. So 
$$
\iint (x-\mathbb{E}[x])(y - \mathbb{E}[y])  p(x,y) \text{d}x \text{d}y =  \iint (x-\mathbb{E}[x])(y - \mathbb{E}[y])  p(x)p(y) \text{d}x \text{d}y \\
 = \int (x-\mathbb{E}[x]) p(x) \text{d}x \int (y-\mathbb{E}[y]) p(y) \text{d}y  = 0 
$$

### Problem 1.7

In this exercise, we prove the normalization condition (1.48) for the univariate Gaussian. To do this consider, the integral
$$
I = \int_{-\infty} ^{\infty} \exp \left( -\frac{1}{2\sigma^2} x^2\right) \text{d}x
$$
which we can evaluate by first writing its square in the form
$$
\label{eq:Isquare}
I^2 = \int_{-\infty} ^{\infty}  \int_{-\infty} ^{\infty} \exp \left( -\frac{1}{2\sigma^2} x^2  -\frac{1}{2\sigma^2} y^2 \right) \text{d}x \text{d}y.
$$
Now make the transformation from Cartesian coordinates $(x, y)$ to polar coordinates $(r, θ)$ and then substitute $u = r^2$. Show that, by performing the integrals over $θ$ and $u$, and then taking the square root of both sides, we obtain
$$
I = (2\pi \sigma^2 )^{1/2}.
$$
Finally, use this result to show that the Gaussian distribution $\mathcal{N}(x|\mu, \sigma^2)$ is normalized.

Appendix: eq (1.48):
$$
\int_{-\infty}^{\infty} \mathcal{N}(x|\mu,\sigma^2) \text{d}x =1.
$$

#### Solution:

Transform $(x,y)$ from Cartesian coordinates to polar coordinates $(r,\theta)$,  then we get
$$
x = r \cos \theta\\
y = r \sin \theta\\
$$
the equation $\ref{eq:Isquare}$ becomes
$$
I^2 = \int_{-\infty} ^{\infty}  \int_{-\pi} ^{\pi} \exp  \left( -\frac{1}{2\sigma^2} r^2 \cos^2 \theta   -\frac{1}{2\sigma^2} r^2 \sin ^2 \theta \right) r \text{d}\theta \text{d}r\\
=  \int_{0} ^{\infty}  \int_{-\pi} ^{\pi} \exp \left( - \frac{1}{2\sigma^2} r ^2 \right) r \text{d}\theta \text{d}r = 2\pi \int_{0} ^{\infty}  \exp \left( - \frac{1}{2\sigma^2} r ^2 \right)r \text{d}r
$$
For the integrity part, 
$$
\label{eq:intpart}
\int_{0} ^{\infty}  \exp \left( - \frac{1}{2\sigma^2} r ^2 \right)r \text{d}r = -\sigma^2
$$
As $I \geq 0$ then $I = (2\pi \sigma^2 )^{1/2}$.

### Problem 1.8

By using a change of variables, verify that the univariate Gaussian distribution given by (1.46) satisfies (1.49). Next, by differentiating both sides of the normalization condition
$$
\int_{-\infty}^{\infty} \mathcal{N}(x|\mu,\sigma^2) \text{d}x =1
$$
with respect to $\sigma^2$, verify that the Gaussian satisfies (1.50). Finally, show that (1.51) holds.

Appendix: eq 1.46:
$$
\mathcal{N}\left( x | \mu, \sigma^2  \right) = \frac{1}{(2 \pi \sigma^2)^{1/2}} \exp\left\{ -\frac{1}{2\sigma^2}(x-\mu)^2\right\}
$$
eq 1.49:
$$
\mathbb{E} [x] = \mu
$$
eq 1.50: 
$$
\mathbb{E}[x^2] = \mu^2 + \sigma^2
$$
eq 1.51:
$$
\text{var} [x] = \mathbb{E}[x^2] - \mathbb{E}[x]^2 = \sigma^2
$$

#### Solution:

Firstly, we can prove that
$$
\int_{-\infty}^{\infty} \mathcal{N}(x|0,\sigma^2) x  \text{d}x =0
$$
utilizing the equation $\ref{eq:intpart}$. Then
$$
\mathbb{E} [x] = \int_{-\infty}^{\infty} \mathcal{N}(x|\mu,\sigma^2) x  \text{d}x = \int_{-\infty}^{\infty} \mathcal{N}(y|0,\sigma^2) (y+\mu) \text{d}y = \mu
$$
We can also prove that 
$$
\int_{-\infty}^{\infty} \mathcal{N}(x|0,\sigma^2) x^2  \text{d}x = \sigma^2
$$
utilizing the equation $\ref{eq:intpart}$. Then 
$$
\mathbb{E}[x^2] = \int_{-\infty}^{\infty} \mathcal{N}(y|0,\sigma^2) (y^2+\mu^2 +2 y \mu ) \text{d}y  =  \mu^2 + \sigma^2
$$

### Problem 1.9

Show that the mode (i.e. the maximum) of the Gaussian distribution (1.46) is given by $\mu$. Similarly, show that the mode of the multivariate Gaussian (1.52) is given by $\boldsymbol{\mu}$.

Appendix: eq 1.46:
$$
\mathcal{N}\left( x | \mu, \sigma^2  \right) = \frac{1}{(2 \pi \sigma^2)^{1/2}} \exp\left\{ -\frac{1}{2\sigma^2}(x-\mu)^2\right\}
$$
eq 1.52:
$$
\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}, \mathbf{\Sigma}) = \frac{1}{(2\pi)^{D/2}} \frac{1}{|\mathbf{\Sigma}|^{1/2}}\exp \left\{ -\frac{1}{2} (\mathbf{x} - \boldsymbol{\mu})^T \mathbf{\Sigma}^{-1} (\mathbf{x} - \boldsymbol{\mu}) \right\}
$$
D for dimensional of the random variables.

#### Solution:

Differentiating equation 1.46, we get
$$
\frac{\text{d} \mathcal{N}(x,...)}{ \text{d} x } = C  \exp\left\{ -\frac{1}{2\sigma^2}(x-\mu)^2\right\} (x - \mu)
$$
where $C$ is  a constant. It will be $0$ if and only if $x = \mu$.

So as for eq 1.52

### Problem 1.10

Suppose that the two variables $x$ and $z$ are statistically independent. Show that the mean and variance of their sum satisfies
$$
\mathbb{E}[x+z]  = \mathbb{E}[x] +  \mathbb{E}[z]\\
\text{var}[x+z] = \text{var}[x]+\text{var}[z]
$$

#### Solution:

Denote $y = x+z$
$$
\mathbb{E}[x+z] =
$$
