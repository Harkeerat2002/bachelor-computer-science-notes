# Assignment 9
***Harkeerat Singh Sawhney & Mak Fazlic*

## Problem 1. (Cubic Spline Interpolation)
We make the ansatz
$$
s(x) = \sum^3_{j=-1} \alpha_jB_3(x-j)
$$
where we have to compute the coefficients $\alpha_j$, such that the interpolation conditions
$$
s(x_i) = \sum^3_{j=-1} \alpha_jB_3(x_i-j) = y_i \space for\space i = 0, 1, ..., n
$$

are met. Since the functions $B_3 (x_i - j)$ are obtained by translation and scaling of the argument $x$, the values of this function in the grid point can be inferred from those of $B_3$ as follows:
$$
B3(0) = \frac{2}{3}, B_3(\pm1)= \frac{1}{6}, B'_3(0) = 0, B'_3(\pm1) = \mp \frac{1}{2}, B''_3(0) = -2, B''_3(\pm 1) = 1
$$
Hence, now in order to get the coefficients of the cubic spline, the linear system of the equation would be as follows:
$$
\begin{bmatrix}  
1 & -2 & 1 & 0 & 0\\  
\frac{1}{6} & \frac{2}{3} & \frac{1}{6} & 0 & 0 \\
0 & \frac{1}{6} & \frac{2}{3} & \frac{1}{6} & 0 \\
0 & 0 & \frac{1}{6} & \frac{2}{3} & \frac{1}{6} \\
0 & 0 & 1 & -2 & 1   
\end{bmatrix}

\begin{bmatrix}
\alpha - 1 \\
\alpha_0 \\
\alpha_1 \\
\alpha_2 \\
\alpha_3
\end{bmatrix}

= 

\begin{bmatrix}
0 \\
1 \\
5 \\
1 \\
0
\end{bmatrix}
$$
Therefore, after performing linear systems for the coefficients, following is the cubic spline $[0, 2] \rightarrow R$ is as follows:
$$
s(x) = -5B_3(x+1) + B_3(x) + 7B_3(x-1) + B_3(x-2) - 5B_3(x-3)
$$

