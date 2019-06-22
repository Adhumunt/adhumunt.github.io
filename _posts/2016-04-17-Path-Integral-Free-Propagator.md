---
title: The Path Integral Free Propagator
tags: Educational QFT
---

In quantum field theory, the propagator gives a probability amplitude for a particle traveling from some point $(t_i,x_i)$ to $(t_f,x_f)$ with a certain energy and momentum. These propagators are the first steps into quantum field theory, I aim to bring these to the masses. The one that is most interesting and easy to grasp is the free propagator for a free field theory. The following derivation is inspired by Anthony Zee's Quantum Field Theory in a Nutshell of UC Santa Barbara.

<!--more-->

# Free Field Theory

We will consider studying free field theory as a simple example of calculating propagators. The majority of the salient features are found in the explanation below and can be extended to more sophisticated cases. We will only consider non-interacting Lagrangians at this moment.

## The Klein-Gordan Equation

We first begin by inspecting the path integral for a free field theory for which the Lagrangian is given by $L(\phi)=\frac{1}{2}((\partial\phi)^2-m^2\phi^2).$ The Euler-Lagrange equations of motion for this system is

$$
\begin{align*}
	\partial_\mu \frac{\delta L}{\delta(\partial_\mu\phi)}-\frac{\delta L}{\delta \phi} = 0 \implies (\partial^2_\mu+m^2)\phi=0.
\end{align*}
$$

This is the Klein-Gordan Equation, and it is possible to solve this equation! First we have that

$$
\begin{align*}
	\partial^2_\mu\phi(t,\textbf{x})=-m^2\phi(t,\textbf{x}).
\end{align*}
$$

The most general solution is $\phi(t,\textbf{x}) = \exp(ik_{\mu} x^{\mu})$ with a metric signature of $(+,-,-,-)$ because this would allow each derivative in the $\partial_\mu$ to act on its specific component with the appropriate constant. Using this ansatz, we have that

$$
\begin{align*}
	\partial^2_\mu(\exp(ik_\mu x^\mu))&=-k^2_\mu \exp(ik_\mu x^\mu) = -m^2 \exp(ik_\mu x^\mu)\\ &\implies k^2_\mu=m^2.
\end{align*}
$$

Since $k_\mu^2=k_0^2-k_i^2$ and if we let $k^2_0=\omega^2,$ we obtain $\omega^2-k_i^2=m^2$ where $i=1,2,3.$ Therefore $\omega^2=m^2+k_i^2$ and we have solved the Klein-Gordan Equation.

## The Path Integral for the Free Field Theory

Our path integral function for this Lagrangian is

$$
\begin{align*}
	Z[\phi]=\int D\phi \exp{\left(\frac{i}{\hbar}\int d^4 x\left(\frac{1}{2}[(\partial \phi)^2-m^2\phi^2]+J\phi\right)\right)}.
\end{align*}
$$

As usual, we let $ \hbar=1$. Now, suppose that the boundary terms of the $d^4 x$ integral approach 0 at $ \pm \infty$, and let,

$$
S(\phi)=\int d^4 x \left(\frac{1}{2}[(\partial\phi)^2-m^2\phi^2]+J\phi\right),\notag
$$

where $ S(\phi)$ is the action. We integrate the first term in the action by parts in the following manner $ u=\partial\phi$,  $d^4u=\partial^2\phi d^4x,$ $d^4v=\partial\phi d^4 x,$ and $ v=\phi$. Then we obtain

$$
\int d^4 x (\partial\phi)^2  = \phi \partial\phi \bigg|^\infty_{-\infty}-\int_{-\infty}^{\infty}d^4 x \phi \left( \partial^2\phi \right).\notag
$$

Now, we have our ultimate result, keeping in mind that the boundary term disappears,

$$
\begin{align*} 
	Z[\phi]&=\int D\phi\exp{\left( i\int d^4 x\left[ \frac{1}{2}((\partial\phi)^2-m^2\phi^2)+J\phi\right] \right)}\\&=\int D\phi\exp{\left( i\int d^4 x\left[- \frac{1}{2}\phi(\partial^2+m^2)\phi+J\phi\right] \right)}.
\end{align*}
$$

### Meet the Free Propagator

We can see that the above integral can be taken from the continuum limit to discrete limit using matrices. The benefit of this is that the transformation causes the integral to be exactly solvable, in the discrete limit, which can then be converted back again using the continuum limit. This transformation is explained briefly on page 22 of Quantum Field Theory in a Nutshell $-$ the major results is listed here

$$
\begin{align*} 
	\int_{-\infty}^\infty\int_{-\infty}^\infty\cdots\int_{-\infty}^\infty dq_1 dq_2 &\cdots dq_N e^{(i/2)q\cdot A \cdot q + i J\cdot q}\\ &=\left(\frac{(2\pi i)^N}{\det[A]}\right)^{1/2}e^{-(i/2)J\cdot A^{-1} \cdot J},\end{align*}
$$

where the vector $ q$ represents the variable $ \phi$ and the matrix $ A$ is the discrete limit of $ -(\partial^2+m^2)$. Now that we know the form of $ A$, the question that eventually incorporates Greens' functions and more is: What is $ A^{-1}$?

To tackle that issue, first notice that $ A\cdot A^{-1}=A^{-1}\cdot A = I$. If we let, say $ D(x-y)$ represent $ A^{-1}$ in the continuum limit, we have that

$$
-(\partial^2+m^2)D(x-y)=\delta^4(x-y).\notag
$$

If we can obtain $ D(x-y)$ we will know our complete solution because that would also determine $ A^{-1}.$ To solve this, we need to use Fourier Transforms. In fact, by transforming both sides of the above equation and then by performing the Fourier inverse, we obtain the form of the propagator, $ D(x-y)$, shown at the bottom of this derivation. First, we push our equation into the dual Fourier basis by

$$
\begin{align*}
	\mathcal{F}[-(\partial^2+m^2)D(x-y)]&=\mathcal{F}[D(x-y)(-\partial^2-m^2)]\\ &=\mathcal{F}[\delta^4(x-y)].
\end{align*}
$$

Then since

$$
\begin{align*}
	\mathcal{F}[D(x-y)(-\partial^2-m^2)]&=\int_{-\infty}^{\infty}D(x-y)[-\partial^2-m^2]e^{-ikx}d^4 x\\ &= \int_{-\infty}^{\infty} d^4 x D(x-y)[k^2-m^2]e^{-ikx}.
\end{align*}
$$

While the right hand side becomes

$$
\mathcal{F}[\delta(x-y)]=\int_{-\infty}^{\infty}\delta(x-y)e^{-ikx}d^4 x=e^{-iky}.\notag
$$

Since the $[k^2-m^2]$ term on the left hand has no dependence on $x^\mu$, we are allowed to remove it from the integral. So we obtain

$$
[k^2-m^2]\int_{-\infty}^{\infty} d^4 x D(x-y)e^{-ikx}=[k^2-m^2]\mathcal{F}[D(x-y)]=e^{-iky}\notag
$$

Now, we are tantalizingly close to our solution, dividing the $$ [k^2-m^2] $$ term to the other side and taking the Fourier inverse we have that

$$
\begin{align*}
	\mathcal{F}^{-1} [\mathcal{F}[D(x-y)]] &=D(x-y)=\mathcal{F}^{-1}\left[\frac{e^{-iky}}{k^2-m^2} \right] \\ &= \int_{-\infty}^{\infty}\frac{d^4 k}{(2\pi)^4}\frac{e^{-iky}e^{ikx}}{k^2-m^2}.\\
	&\therefore \boxed{ D(x-y) = \int_{-\infty}^{\infty}\frac{d^4 k}{(2\pi)^4}\frac{e^{ik(x-y)}}{k^2-m^2}}
\end{align*}
$$

We have arrived at our desired conclusion! Usually, however, we transform $ m^2 \to m^2 -i\epsilon$, where $ \epsilon$ is a positive infinitesimal that goes to 0. With this transformation, we arrive at the beautiful result

$$
\boxed{\boxed{ D(x-y) = \int_{-\infty}^{\infty}\frac{d^4 k}{(2\pi)^4}\frac{e^{ik(x-y)}}{k^2-m^2+i\epsilon} .\ }}
$$
