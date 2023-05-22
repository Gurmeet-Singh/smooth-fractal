---
layout: article
title: "Spheres Of Attraction"
categories: Physics
comments: true
---

In my spare time I commonly like to come up with some random problem and then solve it. And some times these random explorations results in so wonderful analysis that it's hard to put it down. This was one of those.

Basically the problem is, there are two metallic spheres of radius $$a$$, $$D$$ distance apart, if they have the charge $$Q$$ and $$-Q$$ on them what will be the total force between them.

## Initial thoughts
First, let's just place the spheres on the $$x$$-axis with coordinates $$x=0$$ and $$x=D$$.

Now the charges can flow on the surface of the surface and they'll get closer to each other, so the total attractive force should be greater then the zeroth order answer, $$\frac{Q^2}{4\pi \epsilon_0 D^2}$$. The charges should rearrange themselves to keep the metal surface equipotential. And the spherical equipotential surface can be obtained by inversion of the charges outside of it with appropriate scaling. So if we start with considering the charges at the center of the sphere and then apply  consecutive inversions, we should come up with a sequence of charges which is equivalent to the charge distribution on the surface of the metal. And then by summing up the forces between the charges we should be able to calculate the total force.

## Metal surfaces with charge
We know the metal surface should be equipotential as if it isn't then the charge on the surface will feel a tangential force to balance the potential difference till it's equipotential.

Based on the above observation, it's a common technique to replace the charge on the surface with a charge on the other side which produces the same field lines and equipotential surfaces. For example, in the case of effectively infinite plane metal plate it results in reflecting the charges on the other side on the plate and equally distributing the remaining charge on the plate (which contributes to the force less and less for bigger and bigger plate, so can be ignored if the plate is effectively infinite).

In the case of spherical metal surface, let's say of radius $$a$$, a point charge $$q$$ at distance $$d$$ form the center of the sphere induces the charge on the surface of the metal equivalent to a point charge $$\frac{aq}{d}$$ inside of the sphere at a distance $$\frac{a^2}{d}$$. And the remaining charge can be equally distributed on the surface which is equivalent to a point charge at the center on the sphere.

## Basic Setup
As discussed above, let's replace the charge on the surface of the sphere at the center with equivalent list of point charges $$q_0, q_1, q_2, q_3...$$ at distances $$d_0 = 0, d_1, d_2, d_3...$$ from origin. Of course, these charges are on the $$x$$-axis because of the symmetry. By symmetry, the charge on the surface of the second sphere is replaced with equivalent list of point charges $$-q_0, -q_1, -q_2, -q_3...$$ at distances $$D - d_0, D - d_1, D - d_2, D - d_3...$$ from origin.

So, basic idea is the points $$d_1, d_2, d_3, d_4...$$ (notice the absence of $$d_0$$) are inversions of $$D - d_0, D - d_1, D - d_2, D - d_3...$$ with charges $$q_i = \frac{a}{D-d_{i-1}}q_{i-1}$$ and $$q_0$$ is the remaining charge. So,

$$
  d_i = \frac{a^2}{D-d_{i-1}}\ \ \ \ \ \ d_0 = 0
$$

$$
  q_i = \frac{a}{D-d_{i-1}}q_{i-1} = \frac{d_i q_{i-1}}{a}
$$

and

$$
  Q = \sum_{i=0}^{\infty} q_i
$$

## Interesting recursion
Let's define some convenient variables -

$$
  \begin{align}
    x_i & = \frac{d_i}{a}\ \ \ \ \ \ X = \frac{D}{a} \\
    \implies x_i & = \frac{1}{X-x_{i-1}}\ \ \ \ \ \ x_0 = 0
  \end{align}
$$

For our problem, $$X>2$$.And let $$D_i$$ be the denominator of $$x_i$$.

$$
  \implies D_i = X D_{i-1} - D_{i-2}\ \ \ with\ \ \ D_0 = 1\ \ \ and\ \ \ D_1 = X \\
$$

Our earlier variables in terms of $$D_i$$ are -

$$
  x_i = \frac{D_{i-1}}{D_i}\ \ \ \ \ \ q_i = \frac{q_0}{D_i}
$$

$$D_i$$ seems like a really interesting sequence of polynomials in $$X$$. They follows a recursion similar to recursion for Fibonacci numbers. It turns out they also have many properties similar to Fibonacci numbers and many techniques to study Fibonacci numbers can be used to study $$D_i$$ as well.

But before diving deep into an analysis of $$D_i$$'s, let's first work out the force. Total force is,

$$
  F = \sum_{i,j=0}^{\infty} \frac{q_i q_j}{4\pi \epsilon_0 (D - d_i - d_j)^2}
$$

Substituting the values for $$d_i$$ and $$q_i$$ in terms of $$D_i$$ and $$X$$,

$$
  F = \frac{q_0^2}{4\pi \epsilon_0 a^2} \sum_{i,j=0}^{\infty} \frac{D_i D_j}{(X D_i D_j - D_{i-1} D_j - D_i D_{j-1})^2}
$$

And the relation between $$Q$$ and $$q_0$$ is,

$$
  Q = q_0 \sum_{i=0}^{\infty} \frac{1}{D_i}
$$

## Properties of $$D_i$$'s
As mentioned earlier, $$D_i$$'s follows a recursion similar to Fibonacci numbers and can be analyzed similarly. For example,

$$
  X D_i D_j - D_{i-1} D_j - D_i D_{j-1} = D_{i+1} D_j - D_i D_{j-1} = D_i D_{j+1} - D_{i-1} D_j
$$

Applying the above relation repeatedly,

$$
  D_{i+1} D_j - D_i D_{j-1} = D_1 D_{i+j} - D_0 D_{i+j-1} = X D_{i+j} - D_{i+j-1} = D_{i+j+1}
$$

Which is very similar to a relation followed by Fibonacci numbers. And you can imagine, this will be useful to simplify the equation for force. But let's come back to it later. For now, let's look at the generating function,

$$
  G_X(t) = \sum_{i=0}^{\infty} D_i t^i = \frac{1}{1-Xt+t^2}
$$

The $$X$$ derivative of $$G_X(t)$$ is the generating function of $$X$$ derivative of $$D_i$$.

$$
  \frac{d G_X(t)}{d X} = \frac{t}{(1-Xt+t^2)^2} = t G_X^2(t)
$$

By comparing the coefficients of the above relation,

$$
  D_{n+1}' = \sum_{i=0}^{n} D_i D_{n-i}
$$

We can use the matrixes to find a general formula for $$D_i$$, similar to Fibonacci numbers. That is,

$$
  \begin{bmatrix}
    D_i \\ D_{i-1}
  \end{bmatrix}
  =
  \begin{bmatrix}
    X & -1 \\ 1 & 0
  \end{bmatrix}^i
  \begin{bmatrix}
    1 \\ 0
  \end{bmatrix}
$$

Now, by diagonalizing the matrix,

$$
  A =
  \begin{bmatrix}
    X & -1 \\ 1 & 0
  \end{bmatrix}
$$

we can come up with the general formula for $$D_i$$. The characteristic equation for $$A$$ is,

$$
  \begin{align}
    | A - \lambda I | = 0 \\
    \implies (X - \lambda)(-\lambda) + 1 = 0
    \implies \lambda^2 - X\lambda + 1 = 0
  \end{align}
$$

Of course, there are two solutions to the above equation, one greater than $$1$$ and one less. This equation and the fact that $$X>2$$ suggests the substitution $$X = 2\cosh{\theta}$$ with positive $$\theta$$. So, two solutions are $$e^{\theta}$$ and $$e^{-\theta}$$. The diagonalization of $$A$$ is,

$$
  \begin{align}
    A & =
    \begin{bmatrix}
      X & -1 \\ 1 & 0
    \end{bmatrix} \\
    & = \frac{1}{\lambda^2 - 1}
    \begin{bmatrix}
      \lambda & 1 \\ 1 & \lambda
    \end{bmatrix}
    \begin{bmatrix}
      \lambda & 0 \\ 0 & 1/\lambda
    \end{bmatrix}
    \begin{bmatrix}
      \lambda & -1 \\ -1 & \lambda
    \end{bmatrix} \\
  \end{align}
$$

Using this diagonalization, the general formula for $$D_i$$ is,

$$
  \begin{align}
    D_i & = \frac{\lambda^{i+1} - (1/\lambda)^{i+1}}{\lambda - 1/\lambda} \\
    & = \frac{\sinh{(i+1)\theta}}{\sinh{\theta}}
  \end{align}
$$

## Finally The Force
Using the above relations the formula for force can be amazingly simplified,

$$
  \begin{align}
    F & = \frac{q_0^2}{4\pi \epsilon_0 a^2} \sum_{i,j=0}^{\infty} \frac{D_i D_j}{D_{i+j+1}^2} \\
    & = \frac{q_0^2}{4\pi \epsilon_0 a^2} \sum_{k=1}^{\infty} \frac{\sum_{i=0}^{k-1} D_i D_{k-1-i}}{D_k^2} \\
    & = \frac{q_0^2}{4\pi \epsilon_0 a^2} \sum_{k=1}^{\infty} \frac{1}{D_k^2}\frac{d D_k}{d X} \\
    & = \frac{-q_0^2}{4\pi \epsilon_0 a^2} \frac{d}{d X}\left(\sum_{k=1}^{\infty} \frac{1}{D_k}\right) \\
    & = \frac{-q_0^2}{4\pi \epsilon_0 a^2} \frac{d}{d X}\left(\frac{Q}{q_0}\right) \\
    & = \frac{Q}{4\pi \epsilon_0 a^2}\frac{d q_0}{d X} \\
    & = \frac{Q}{8\pi \epsilon_0 a^2 sinh{\theta}}\frac{d q_0}{d \theta}
  \end{align}
$$

And the relation between $$Q$$ and $$q_0$$,

$$
  \begin{align}
    Q & = q_0 \sum_{i=0}^{\infty} \frac{1}{D_i} \\
    & = q_0 \sinh{\theta} \sum_{i=0}^{\infty} \frac{1}{\sinh{(i+1)\theta}} \\
    & = q_0 \sinh{\theta} \sum_{i=1}^{\infty} \frac{1}{\sinh{i\theta}}
  \end{align}
$$

## Approximation
$$D_i$$'s depends on $$X$$ only. For large $$X$$ with the help of Mathematica,

$$
  \begin{align}
    Q & = q_0 \left(1+\frac{1}{X}+\left(\frac{1}{X^2}+\frac{1}{X^4}+\frac{1}{X^6}+\frac{1}{X^8}+\frac{1}{X^{10}}+\frac{1}{X^{12}}+\frac{1}{X^{14}}+... \right) + \left(\frac{1}{X^3}+\frac{2}{X^5}+\frac{4}{X^7}+\frac{8}{X^9}+\frac{16}{X^{11}}+\frac{32}{X^{13}}+... \right) + \left(\frac{1}{X^4}+\frac{3}{X^6}+\frac{8}{X^8}+\frac{21}{X^{10}}+\frac{55}{X^{12}}+\frac{144}{X^{14}}+... \right) + \left(\frac{1}{X^5}+\frac{4}{X^7}+\frac{13}{X^9}+\frac{40}{X^{11}}+\frac{121}{X^{13}}+... \right) + \left(\frac{1}{X^6}+\frac{5}{X^8}+\frac{19}{X^{10}}+\frac{66}{X^{12}}+\frac{221}{X^{14}}+... \right) + \left(\frac{1}{X^7}+\frac{6}{X^9}+\frac{26}{X^{11}}+\frac{100}{X^{13}}+... \right) + \left(\frac{1}{X^8}+\frac{7}{X^{10}}+\frac{34}{X^{12}}+\frac{143}{X^{14}}+... \right) + \left(\frac{1}{X^9}+\frac{8}{X^{11}}+\frac{43}{X^{13}}+... \right) + \left(\frac{1}{X^{10}}+\frac{9}{X^{12}}+\frac{53}{X^{14}}+... \right) + \left(\frac{1}{X^{11}}+\frac{10}{X^{13}}+... \right) + \left(\frac{1}{X^{12}}+\frac{11}{X^{14}}+... \right) + \left(\frac{1}{X^{13}}+... \right) + \left(\frac{1}{X^{14}}+... \right) + ... \right) \\
    & = q_0 \left(1+\frac{1}{X}+\frac{1}{X^2}+\frac{1}{X^3}+\frac{2}{X^4}+\frac{3}{X^5}+\frac{5}{X^6}+\frac{9}{X^7}+\frac{15}{X^8}+\frac{28}{X^9}+\frac{49}{X^{10}}+\frac{91}{X^{11}}+\frac{165}{X^{12}}+\frac{307}{X^{13}}+\frac{573}{X^{14}}+... \right) \\
    \implies q_0 & = Q \left(1-\frac{1}{X}-\frac{1}{X^4}-\frac{1}{X^6}-\frac{2}{X^7}-\frac{1}{X^8}-\frac{6}{X^9}-\frac{5}{X^{10}}-\frac{14}{X^{11}}-\frac{21}{X^{12}}-\frac{40}{X^{13}}-\frac{76}{X^{14}}-... \right) \\
    \implies \frac{d q_0}{d X} & = Q \left(\frac{1}{X^2}+\frac{4}{X^5}+\frac{6}{X^7}+\frac{14}{X^8}+\frac{8}{X^9}+\frac{54}{X^{10}}+\frac{50}{X^{11}}+\frac{154}{X^{12}}+\frac{252}{X^{13}}+\frac{520}{X^{14}}+\frac{1064}{X^{15}}-... \right)
  \end{align}
$$

So, the force is,

$$
  \begin{align}
    F & = \frac{Q}{4\pi \epsilon_0 a^2}\frac{d q_0}{d X} \\
    & = \frac{Q^2}{4\pi \epsilon_0 D^2} \left(1+\frac{4}{X^3}+\frac{6}{X^5}+\frac{14}{X^6}+\frac{8}{X^7}+\frac{54}{X^8}+\frac{50}{X^9}+\frac{154}{X^{10}}+\frac{252}{X^{11}}+\frac{520}{X^{12}}+\frac{1064}{X^{13}}-...\right)
  \end{align}
$$

It's interesting that there are no first and second order correction. That is, the zeroth order answer is really good approximation itself.

## Appendix - Extra notes and what next?
1. The formula,

    $$
      F = \frac{Q}{4\pi \epsilon_0 a^2}\frac{d q_0}{d X}
    $$

    strongly suggests there might be a more direct way of deriving it but I can't think of any. So, is there any more direct way or not? Or, in other words, is there a more direct way of interpreting this result?
2. What are the general conditions to produce a spherical equipotential surface?
3. (Added on 22 May 2023) The problem has been discussed in [[1]](#1) as the Exercise 8.7 on Page 166. There the problem is considered for the case of repulsion between 2 similar charged balls and it confirms the first correction term with opposite sign.


## References
<a id="1">[1]</a>
Bevington, P. R., & Robinson, D. K. (2003). Data reduction and error analysis for the physical sciences. Boston: McGraw-Hill. 3rd Edition
