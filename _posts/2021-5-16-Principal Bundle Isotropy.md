---
layout: post
title: Principal Bundle Isotropy
---

Just some simple facts which have come up from my research.

Let $$M$$ be a (smooth) manifold with a distinguished point $$x_0\in M$$. Suppose $$K$$ is a (Lie) group acting (smoothly) on $$M$$ on the left. So

$$
\begin{align}
	K\times M &\to M \\
	(k,x) &\mapsto kx.
\end{align}
$$

Each point defines a **stabilizer** subgroup. Let $$H$$ denote the stabilizer for $$x_0$$. So

$$
H:= \text{Stab}_K(x_0)=\{h\in K~:~hx_0=x_0\} \leq K.
$$

If we pick a different point $$kx_0$$ in the orbit of $$x_0$$, the stabilizer $$H$$ changes to a conjugate subgroup in $$K$$. That is,

$$
H_{kx_0} = kH_{x_0}k^{-1} = \{khk^{-1}~:~h\in H_{x_0}\}\cong H_{x_0}
$$

because $$(khk^{-1})(kx_0) = khx_0 = kx_0$$.

Now suppose $$P\to M$$ is a **principal $$G$$-bundle**. That is, it is a bundle with fiber diffeomorphic to $$G$$, equipped with a right $$G$$ action

$$
\begin{align}
	P\times G &\to P \\
	(p,g) &\mapsto pg
\end{align}
$$

which only moves along the fibers of $$P$$, and further is free and transitive along those fibers, so that $$M= P/G$$. Also we have local $$G$$-equivariant trivializations from $$U\subset M$$ to the bundle $$U\times G\to U$$, which are equivariant with respect to right $$G$$ action on $$U\times G$$ of just right multiplying on the $$G$$ component.

Suppose further that $$P$$ is $$K$$-**homogeneous**, which means that we have a **lift** of the left $$K$$ action to $$P$$ which commutes with the right $$G$$ action. By lift, we mean that we have a $$K$$ action on $$P$$, still on the left, which "covers" the $$K$$ action on $$M$$, (so $$k$$ sends the fiber over $$x$$ to the fiber over $$kx$$). 

If we distinguish a point $$p_0\in P$$ which lies in the fiber over the point $$x_0$$, then this defines an "isotropy homomorphism" $$\lambda:H\to G$$ by the following: Let $$h\in H$$. Since $$H$$ fixes $$x_0$$, when we look at the lifted action to $$P$$, it can only possibly jumble up the fiber over $$x_0$$. Since the $$G$$ action on the fiber is free and transitive, there is a unique element $$\lambda(h)$$ for which

$$
hp_0 = p_0\lambda(h).
$$

Note this is actually a homomorphism by

$$
p_0\lambda(hh') = (hh')p_0 = hp_0\lambda(h')=p_0\lambda(h)\lambda(h'),
$$

which, since the $$G$$ action is free on the $$p_0$$ fiber, says that $$\lambda(hh') = \lambda(h)\lambda(h')$$.

If we pick a different point $$p_0g$$ in the fiber over $$x_0$$, then $$\lambda$$ changes to a conjugate homomorphism. That is,

$$
\lambda_{p_0g}= g^{-1}\lambda_{p_0}g
$$

because

$$
p_0\lambda_{p_0g}(h) = hp_0g = p_0\lambda_{p_0}(h)g = p_0g (g^{-1}\lambda_{p_0}(h)g).
$$

So $$H$$ depends conjugately on $$x_0$$ (in its $$K$$-orbit), and $$\lambda$$ depends conjugately on $$p_0$$ (in its $$G$$-orbit / fiber over $$x_0$$).

There is another point of view of the lifted action on $$P$$. Since $$K$$ acts on the left, and $$G$$ acts on the right, and these actions commute, we have a (left) action by the group $$\hat K := K\times G$$ (using a classic trick to turn a right action into a left action):

$$
\begin{align}
	\hat K\times P &\to P \\
	(k,g).p &\mapsto kpg^{-1}
\end{align}
$$

Now given $$x_0,p_0,H$$ and $$\lambda$$ as above, I ask "what is the stabilizer of $$p_0$$?"

Well, note that by the defining equation for $$\lambda$$, the element $$(h,\lambda(h))$$ fixes $$p_0$$. 

$$
hp_0\lambda(h)^{-1} = p_0
$$

Conversely, if any $$(k,g)$$ fixes $$p_0$$, note that $$k$$ must lie in $$H$$, as it sends the fiber over $$x_0$$ to itself (the $$G$$-action doesn't change fiber). Then

$$
p_0 = (h,g).p_0 = hp_0g^{-1} = p_0\lambda(h)g^{-1}
$$

which implies that $$g=\lambda(h)$$. Thus the stabilizer of $$p_0$$ is the graph of $$H$$ in $$\hat K$$, and is isomorphic to $$H$$.

$$
\hat H:= \text{Stab}_{\hat K}(p_0) = \{(h,\lambda(h))~:~h\in H\} \cong H.
$$
