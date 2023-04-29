# Assignment 7
Harkeerat Singh Sawhney & Mak Fazlic

## Problem 1. (Lagrange Interpolation)
Considering the main function:
$$
f(x) = \frac{2}{3+2x}
$$
Now trying to compute the interpolating polynomial p with respect to the Lagrangian basis for the abscissas.
$$
\begin{align}
f(x_{0}) = \frac{2}{3+(2 \times -1)} = \frac{2}{1} = 2 \\
f(x_{1}) = \frac{2}{3-(2 \times 0.5)} = \frac{2}{2} = 1 \\
f(x_{2}) = \frac{2}{3+(2 \times 0.5)} = \frac{2}{4} = 0.5 \\
f(x_{3}) = \frac{2}{3+(2 \times 1)} = \frac{2}{5} = 0.4 \\

\end{align}
$$
Hence we will get the following table:
| x   | -1   | -0.5   | 0.5   | 1   |
| --- | --- | --- | --- | --- |
| y   | 2   | 1   | 0.5  | 0.4  |

Now we knew that the Lagrange Polynomials are given by the following equation:
$$
L_i(x) := \prod_{n}^{j=0}\bigg(\frac{x - x_i}{x_i - x_j}\bigg) \in \Pi_{n}
$$
Hence using that equation now:
$$
\begin{aligned}
L_{0}(x) = \frac{x+0.5}{-0.5} \times \frac{x-0.5}{-1.5} \times \frac{x-1}{-2}
\\
L_{1}(x) = \frac{x+1}{0.5} \times \frac{x-0.5}{-1} \times \frac{x-1}{-1.5}
\\
L_{2}(x) = \frac{x+1}{1.5} \times \frac{x+0.5}{1} \times \frac{x-0.5}{-0.5}
\\
L_{3}(x) = \frac{x+1}{2} \times \frac{x+0.5}{1.5} \times \frac{x-0.5}{0.5}
\end{aligned}
$$
Hence now using the interpolating polynomial to find the polynomials.
$$
p(x) = \sum_{i=0}^{n}y_{i}L_{i}(x_{j}) = y_{j} \space for \space all \space j= 0, 1, ..., n
$$
Therefore,
$$
\begin{align}
p(x) = 2L_{0}(x) + L_{1}(x) + 0.5L_{2}(x) + 0.4L_{3}(x)\\
\\
= \frac{4x^3 - 4x^2 - x + 1}{3} + \frac{4x^3 - 2x^2 - 4x + 2}{3} - \frac{2x^3 - x^2 - 2x + 1}{3} \\
= \frac{-2x^3 + 3x^2 - 2x + 3}{5}
\end{align}
$$
Hence, now in order to get the error estimate:
$$
\begin{align}
\max_{e \in [-1, 1]]} \big| (x-x_{0}) (x-x_{1}) (x-x_{2}) (x-x_{3}) \big|  \\
\max_{e \in [-1, 1]]} \big| x^4  - 1.25x^25 + 0.25 \big|
\end{align}
$$
With the help of differentiation the critical points can be found. Hence, if the derivative of the above equation is taken the following is understood that at 0, 0.79 and -0.79 are the critical points. Hence, as follows we know:
$$
\begin{align}
\max_{e \in [-1, 1]]} \big| x^4  - 1.25x^25 + 0.25 \big| = 0.25
\end{align}

$$


## Problem 3. (Bonus Exercise: Lagrange Interpolation)
What we know so far:
$$
(0,5)\space(1,1)\space(2,-3)\space(4, 13)
$$
$$
L_i(x) := \prod_{n}^{j=0}\bigg(\frac{x - x_i}{x_i - x_j}\bigg) \in \Pi_{n}
$$

Hence, this could be written in a table as following:
| x   | 0   | 1   | 2   | 4   |
| --- | --- | --- | --- | --- |
| y   | 5   | 1   | -3  | 13  |

Therefore, by using the Lagrange Polynomials, we can get the interpolation polynomial.
$$
\begin{aligned}
L_{0}(x) = \frac{x-1}{-1} \times \frac{x-2}{-2} \times \frac{x-4}{-4}
\\
L_{1}(x) = \frac{x}{1} \times \frac{x-2}{-1} \times \frac{x-4}{-3}
\\
L_{2}(x) = \frac{x}{2} \times \frac{x-1}{1} \times \frac{x-4}{-2}
\\
L_{3}(x) = \frac{x}{4} \times \frac{x-1}{3} \times \frac{x-2}{2}
\end{aligned}
$$
Now using the interpolating polynomial formula to find the polynomials
$$

p(x) = \sum_{i=0}^{n}y_{i}L_{i}(x_{j}) = y_{j} \space for \space all \space j= 0, 1, ..., n
$$
Therefore,
$$
p(x) = \big(5 \times L_{0}(x)\big) + L_{1}(x) - \big(3 \times L_{2}(x)\big) + \big(13 \times L_{3}(x)\big) = x^{3} - 3x^2 - 2x + 5
$$
