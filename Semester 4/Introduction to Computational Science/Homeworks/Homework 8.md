# Assignment 8
Harkeerat Singh Sawhney & Mak Fazlic

## Problem 3. (Bonus exercise: Lagrange Interpolation)
Since it is known that when the function such as $f(x) =1$ is interpolated, then the interpolation polynomial of the function would be:
$$
\begin{align}
P(x) = \sum_{i=0}^{n}f(x_i)L_i()x \\
= \sum_{i=0}^{n}L_i(x) \\
= \prod_{j\neq i} \frac{x-x_j}{x_i - x_j}
\end{align}
$$
Hence through the **Theory 3.2** it can be stated as following:
$$
\sum_{i=0}^{n}L_i(x) = 1
$$
