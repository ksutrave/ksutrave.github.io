---
layout: post
title: Double Jeopardy
---

a math edition of jeopardy is taking place in my dreams.

> Alex: This type of function can be characterized by the property that it is equal to its own derivative.
>
> [Two buzzers go off at the same time, somehow.]
>
> Contestant 1: What is an exponential?
>
> Contestant 2: What is a linear function?
>
> Alex: correct!

(Please note: I don't watch the show.)

This is my favorite confusion. The answer I would have given when I first learned calculus is the first one. But later I (probably) came across a statement like the following when reading a proof:

> Since $$f$$ is linear, we have $$df = f$$.

And of course it made total sense at the time. The paradox only hit me later in the day, and figuring it out was a real fun test for myself to make sure I understood what was going on, especially in the comprehensive notation of differential geometry. 

The reasoning. Contestant 1 assumes we are working with a (say a real) one-variable function $$x\mapsto f(x)$$. Of course the exponential satisfies the condition.

$$
\frac{\mathrm d}{\mathrm dx}e^x = e^x
$$

Is it true about linear functions as well? Of course not.

$$
\frac{\mathrm d}{\mathrm dx}kx = k
$$

Is it true about *any other* kind of function? No. A simple theorem. Suppose $$f$$ satisfies

$$
f'(x) = f(x) \text{ for all }x\in \R
$$

Then one can do that differential equations process of separating the variables and integrating, and show that $$f$$ must be of the form $$f(x) = Ce^x$$ for some constant $$C$$. And this can be made rigorous, but here's another proof.

$$
\begin{gather*}
	\frac{\mathrm d}{\mathrm dx}\left(f(x)e^{-x}\right) = f'(x) e^{-x} -f(x)e^{-x} = (f'(x)-f(x))e^{-x} = 0
\end{gather*}
$$

Therefore, the function $$f(x)e^{-x}$$ is equal to a constant $$C$$.

The second contestant's answer is easier to see if we use more than one variable, (of course it's true in any dimension). Let's use two, consider $$F:\R^2\to\R^2$$

$$
\begin{bmatrix}x\\y\end{bmatrix}\mapsto F\left(\begin{bmatrix}x\\y\end{bmatrix}\right)= \begin{bmatrix}u(x,y)\\v(x,y)\end{bmatrix}
$$

Suppose $$F$$ is linear. Then it can be described by a matrix.

$$
F = \begin{bmatrix}a & b \\ c & d\end{bmatrix} \\
\\
F\left(\begin{bmatrix}x\\y\end{bmatrix}\right)=\begin{bmatrix}a & b \\ c & d\end{bmatrix}\begin{bmatrix}x\\y\end{bmatrix} = \begin{bmatrix}ax+by\\cx+dy\end{bmatrix}
$$

In multiple variable calculus, there's not just one derivative, there's loads of partial derivatives. The derivative information of a vector-valued function of multiple variables can be described by arranging the partial derivatives into a single matrix (the "Jacobian"). And as long as we order things correctly:

$$
\mathrm dF = \begin{bmatrix}\frac{\partial u}{\partial x} & \frac{\partial u}{\partial y}\\ \frac{\partial v}{\partial x} & \frac{\partial v}{\partial y} \end{bmatrix} = \begin{bmatrix}a&b\\c&d\end{bmatrix} = F
$$

Ah, so this is what's going on. Anytime we arrange (four) numbers into a (2x2) matrix, we can think of it as a linear map (from $$\R^2$$ to $$\R^2$$). So if we treat the Jacobian *as a linear map* rather than as just a package of derivatives, then it happens to be equal to the original linear map $$F$$. In this way, any linear map is equal to its derivative (shown above). Conversely, if $$F$$ is equal to its derivative $$dF$$, then $$F$$ must be linear just because $$dF$$ is linear (it is by definition a matrix!)

Is there any value to treating $$dF$$ as a linear map? And how do we square this with the exponential situation above?
