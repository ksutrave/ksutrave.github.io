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
(x,y)\mapsto F(x,y)=\big(u(x,y),v(x,y)\big)
$$

Suppose $$F$$ is linear. Then it can be described by a matrix.

$$
F = \begin{bmatrix}a & b \\ c & d\end{bmatrix} \\
F\left(\begin{bmatrix}x\\y\end{bmatrix}\right)=\begin{bmatrix}a & b \\ c & d\end{bmatrix}\begin{bmatrix}x\\y\end{bmatrix} = \begin{bmatrix}ax+by\\cx+dy\end{bmatrix}
$$

In multi-variable calculus, there's not just one derivative, there's loads of partial derivatives. The derivative information of a vector-valued function of multiple variables can all be packaged into a single matrix of partial derivatives (the Jacobian). And as long as we order things correctly:

$$
\mathrm dF = \begin{bmatrix}\frac{\partial u}{\partial x} & \frac{\partial u}{\partial y}\\ \frac{\partial v}{\partial x} & \frac{\partial v}{\partial y} \end{bmatrix} = \begin{bmatrix}a&b\\c&d\end{bmatrix} = F
$$

So this is what's going on. Anytime we arrange (four) numbers into a (2x2) matrix, we *can think of it as* a linear map (from $$\R^2$$ to $$\R^2$$). So if we treat the Jacobian as a linear map rather than as just a package of derivatives, then it happens to be equal to the original linear map $$F$$. In this way, any linear map is equal to its derivative (shown above). Conversely, if $$F$$ is equal to its derivative $$dF$$ as a function, then $$F$$ must be linear just because $$dF$$ is linear by it's functional definition!

Can you see what's going on?Do you feel cheated? Is it correct to treat $$dF$$ as a linear map this way? Is there any value to doing so? What exactly are we doing differently in the exponential situation above? And what does the rest of my dream mean?

> Alex Trebek: correct!
>
> [I coolly swagger into the set.]
>
> Me: Hey "AL"! (I call Alex Trebek "Al")
>
> [He flips me a coin. I'm on a skateboard now. I catch it in mid air. The director stands up, tips his hat at me and grins. I kickflip and land in the now-empty directors chair. I yell action. The contestants applaud. Everyone else is awestruck. Except there is only the 4 people there. There is no studio audience because of covid.]

To fix everything, we need to nail down proper definitions.

Let $$f$$ be a (not necessarily linear) $$m$$-component function in the $$n$$-variables $$x=(x_1,\dots,x_n)$$ over some domain $$D\subset \R^n$$. 

$$
f:D\to \R^m\\
f(x) := \big(f_1(x_1,\dots,x_n),\dots,f_m(x_1,\dots,x_n)\big)
$$

The derivative of $$f$$ at the point $$x=a$$ is defined to be a linear map $$L_a:\R^n\to\R^m$$ such that

$$
\lim_{h\to0} \frac{|f(a+h)-f(a)-L_a(h)|}{|h|} = 0.
$$

where $$h=(h_1,\dots,h_n)\in \R^n$$ (is small). This condition says that $$L$$ is a linear approximation to $$f$$ at the point $$a$$, and that it approximates $$f$$ to first order. Now the essential point is this: There are **two different functions** here which are important, (which lead to the 2 situations above).

One is the given linear map,

$$
\begin{align}
	L_a:\R^n &\to \R^m \\
	h&\mapsto L_a(h)
\end{align}
$$

which one can prove is given explicitly by the ($$m\times n$$) matrix of partial derivatives, arranged exactly as we did above.

$$
L_a=\begin{bmatrix} 
			\frac{\partial f_1}{\partial x_1} & \dotsm & \frac{\partial f_1}{\partial x_n} \\
			\vdots & \ddots & \vdots \\
			\frac{\partial f_m}{\partial x_1} & \dotsm & \frac{\partial f_m}{\partial x_n}
\end{bmatrix}
$$

With this formulation of the derivative of $$f$$, the statement that "a linear function is equal to its own derivative" is just the statement that a linear function $$f$$ is the best linear approximation to itself!

The second important function is the assignment

$$
\begin{align}
	\mathrm d f: D &\to \{\R^n\xrightarrow{\small\text{linear}}\R^m\} \\
	a &\mapsto L_a
\end{align}
$$

This is the more comprehensive "derivative" object, if we keep in mind that we could have a different linear map assigned to each point $$a$$. We write $$(df)_a := \mathrm df(a) = L_a$$.

What happens in the $$m=n=1$$ case? Well the linear maps are now $$1\times 1$$ matrices. Unpacking the limit definition, this single entry is the number

$$
\lim_{h\to 0}\frac{f(a+h)-f(a)}{h},
$$

which we typically label as $$f'(x)$$. So the second important function is written as

$$
\mathrm d f :a\mapsto [f'(a)].
$$

The derivative of $$f(x) = x^2$$ should properly be written as

$$
\mathrm d f : a \mapsto [2a]
$$

For an exponential, $$f(x) = e^x$$,

$$
a \mapsto [e^a]
$$

In this case, the equality $$f'(x) = f(x)$$ hides the fact that we identify a $$1\times 1$$ matrix with a single number. 

For a linear function, $$\left(f_i(x) = \sum_{j=1}^n b_i^jx_j\right)_{i=1}^{i=m}$$, the full derivative function should properly be written as

$$
\mathrm df: a\mapsto \left[\left.\frac{\partial f_i}{\partial x_j}\right\vert_{x=a}\right]_{i,j} = [b^j_i]_{i,j} \\
\mathrm (df)_a (v) = \left[\sum_j b_i^j v_j\right]_{i} = f(v)
$$

In this case the equality $$\mathrm df = f$$ hides the fact that $$\mathrm df$$ is constant in the variable $$a\in D$$ and identifies the domains $$D$$ and (at least a subset of) $$\R^n$$.

