# Assignment 10
***Harkeerat Singh Sawhney & Mak Fazlic***
## Problem 1. (Gaussian Normal Equations 1)
We know the following information:
$$
\begin{align}
p(x) = ax^2 +bx + c \\
\therefore y = ax^2 +bx + c
\end{align}
$$
| i   | 0   | 1   | 2   | 3   |
| --- | --- | --- | --- | --- |
| $x_i$   | -1     |0     |1     |2     |
|$y_1$     |1     |0     |1     |     |
Hence with this we also know the following formula as well:
$$
A^T A x = A^Tb
$$
Therefore, it goes as follows:
$$
\begin{align}
	y = ax^2 + bx + c \\
	\begin{bmatrix}
		1 \\
		0 \\
		1 \\
		0 	
	\end{bmatrix}
	=
	\begin{bmatrix}
		1 & -1 & 1\\
		0 & 0 & 1 \\
		1 & 1 & 1 \\
		4 & 2 & 1 	
	\end{bmatrix} 
	\begin{bmatrix}
		a \\
		b \\
		c 	
	\end{bmatrix} \\ \\
	\therefore A^TAx = A^Tb \Longrightarrow
	\begin{bmatrix}
		1 & 0 & 1 & 4 \\
		-1 & 0 & 1 & 2 \\
		1 & 1 & 1 & 1
	\end{bmatrix}
	\begin{bmatrix}
		1 & -1 & 1\\
		0 & 0 & 1 \\
		1 & 1 & 1 \\
		4 & 2 & 1 	
	\end{bmatrix} 
	\begin{bmatrix}
		a \\
		b \\
		c 	
	\end{bmatrix}
	= 
	\begin{bmatrix}
		1 & 0 & 1 & 4 \\
		-1 & 0 & 1 & 2 \\
		1 & 1 & 1 & 1
	\end{bmatrix}
	\begin{bmatrix}
		1 \\
		0 \\
		1 \\
		0 	
	\end{bmatrix} \\
	\Longrightarrow
	\begin{bmatrix}
		18 & 8 & 6 \\
		8 & 6 & 2 \\
		6 & 2 & 4
	\end{bmatrix}
	\begin{bmatrix}
		a \\
		b \\
		c 	
	\end{bmatrix}
	=
	\begin{bmatrix}
		2 \\
		0 \\
		2 	
	\end{bmatrix}
\end{align}
$$
Hence we get the following expression:
$$
\begin{bmatrix}
		a \\
		b \\
		c 	
\end{bmatrix}
= 
\begin{bmatrix}
		0 \\
		-0.2 \\
		0.6 	
\end{bmatrix}
$$
So the coefficients of the parabola with the given that would be as follows:
$$
\textbf{a = 0, b = -0.2, c= 0.6}
$$
## Bonus Exercise. (Gaussian Normal Equations 2)
This questions is the same logic as the **Problem 1**, hence the same logic would be also used here to solve it.
We know the following information:
$$
\begin{align}
p(x) = acos(x) + bsin(x) \\
\therefore y = acos(x) + bsin(x)
\end{align}
$$
| i   | 0   | 1   | 2   | 3   | 4|
| --- | --- | --- | --- | --- | ---|
| $x_i$   | 0     |$\frac{\pi}{2}$     |$\pi$     |$\frac{3\pi}{2}$     |$2\pi$ |
|$y_1$     |$\frac{3}{2}$     |2     |$\frac{-1}{2}$     |-2     |1 |
Hence with this we also know the following formula as well:
$$
A^T A x = A^Tb
$$
Therefore, it goes as follows:
$$
\begin{align}
	y = acos(x) + bsin(x) \\
	\begin{bmatrix}
		\frac{3}{2} \\
		2 \\
		-\frac{1}{2} \\
		-2 \\
		1 	
	\end{bmatrix}
	=
	\begin{bmatrix}
		1 & 0\\
		0 & 1\\
		-1 & 0\\
		1 & 0 	
	\end{bmatrix}
	\begin{bmatrix}
		a \\
		b 	
	\end{bmatrix} \\ \\
	\therefore A^TAx = A^Tb \Longrightarrow
	\begin{bmatrix}
		1 & 0 & -1 & 0 & 1 \\
		0 & 1 & 0 & -1 & 0
	\end{bmatrix}
	\begin{bmatrix}
		1 & 0\\
		0 & 1\\
		-1 & 0\\
		1 & 0 	
	\end{bmatrix} 
	\begin{bmatrix}
		a \\
		b	
	\end{bmatrix}
	= 
	\begin{bmatrix}
		1 & 0 & -1 & 0 & 1 \\
		0 & 1 & 0 & -1 & 0
	\end{bmatrix}
	\begin{bmatrix}
		\frac{3}{2} \\
		2 \\
		-\frac{1}{2} \\
		-2 \\
		1 	
	\end{bmatrix} \\
	\Longrightarrow
	\begin{bmatrix}
		3 & 0\\
		0 & 2
	\end{bmatrix}
	\begin{bmatrix}
		a \\
		b	
	\end{bmatrix}
	=
	\begin{bmatrix}
		3 \\
		4 	
	\end{bmatrix}
\end{align}
$$
Hence we get the following expression:
$$
\begin{bmatrix}
		a \\
		b	
\end{bmatrix}
= 
\begin{bmatrix}
		1 \\
		2	
\end{bmatrix}
$$
So the coefficients of the parabola with the given that would be as follows:
$$
\textbf{a = 1, b = 2}
$$