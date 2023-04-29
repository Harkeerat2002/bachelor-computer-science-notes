
*Harkeerat Singh Sawhney* & *Mak Fazlic*

# Exercise 2
## Task 1:
The value of **r** can be calculated by using the mirror reflection formula:
$$
l + r = 2 (n \cdot l)n
$$
$$
r = 2 (n \cdot l)n - l
$$
The formula above is assuming that the **l** has been normalized, hence **l** is as follows:
$$
l = \left( \frac{1}{2}, \frac{2}{3}, \frac{2}{3} \right)
$$
We know that the ground plane is `y = 0`, therefore the surface model for that would be `n = (0,1,0)`. Therefore, imputing n into the formula we get:
$$
r = 2 ( (0, 1, 0) \cdot  \left( \frac{1}{2}, \frac{2}{3}, \frac{2}{3} \right)) \space (0,1,0) - \left( \frac{1}{2}, \frac{2}{3}, \frac{2}{3} \right)
$$
$$
r = 2 \cdot \left( \frac{2}{3} \right) \space (0,1,0) - \left( \frac{1}{2}, \frac{2}{3}, \frac{2}{3} \right)
$$
$$
r = \left( 0, \frac{2}{4},0 \right) - \left( \frac{1}{2}, \frac{2}{3}, \frac{2}{3} \right)
$$
$$
r = \left( \frac{-1}{3}, \frac{2}{3}, \frac{-2}{3} \right)
$$
This must be passing through the camera which is at `(4, 6, 7)`. Therefore, the following expression is there:
$$
(x, y, z) = (4, 6, 7) + q \cdot r
$$
Since we know that this line intersects the `y = 0` plane, we would have the following expression:
$$
0 = 6 + q \cdot \frac{2}{3}
$$
$$
q = \frac{3 \cdot -6}{2} 
$$
$$
\textbf{q} = -9
$$
Therefore,
$$
x = 4 + (-9) \cdot (-\frac{1}{3})
$$
$$
\textbf{x} = 7.
$$
And, 
$$
z = 7 + (-9) (-\frac{2}{3})
$$
$$
\textbf{z} = 13.
$$
This, the peak of the highlight occurs at
$$
\textbf{(x, y, z) = (7, 0, 13)}
$$

## Task 2
We know the following, that the shininess coefficient of the plane is **k = 2** and the intensity of the directional light is **I = 1**. We also know that **1/2** is reflected of the incoming light according to the specular reflection. Hence we have the following expression:
$$
I = \frac{1}{2} \cdot cos(\phi) + \frac{1}{2} \cdot cos^k (\phi)
$$
$$
cos(\phi) = (r\cdot n)
$$
$$
r = (-1, 2, -2)
$$
$$
r = \frac{2}{3}
$$
Therefore,
$$
\textbf{I} = \frac{5}{6}
$$

# Exercise 3
There are several reasons as to why the moon appears as a white disk with constant brightness rather than a sphere shaded according to the Phong illumination. Firstly this is due to poor approximation done  by the diffuse lighting. This happens because of the cosine falloff in the intensity which is not being exhibited of the reflected light due to change in the surface of the moon. 

Another reason is that similarly to diffuse lighting, Phong lighting is not able to approximate the moon as well. Due to this the moon does not have the share specular highlight on its surface, which makes it just look a white disk with a constant brightness. However, the moon itself could be considered as a specular object, as the source for its light during night is due to it reflecting from the sun.