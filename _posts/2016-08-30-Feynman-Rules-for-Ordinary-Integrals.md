---
title: Feynman Rules for Ordinary Integrals
tags: Educational
---

Path integral quantum field theory, perhaps single handedly constructed by Richard Feynman, remains both elusive to undergraduates that wish to study the subject and immensely useful for performing the calculations found in quantum field theory due to the path integral formulation being manifestly symmetric between space and time. Here, we will enter the world of path integral quantum field theory by meticulously performing the calculations so that it is accessible to an advanced undergraduate.

<!--more-->

### General Discussion

Honestly, and I'm being brutally honest here, undergraduates can learn path integral quantum field theory. You might not believe me when I say that its not that hard to perform path integral calculations. The derivation of the path integral can be abstract, however, and so instead of deriving the path integral from scratch, we begin by simply inspecting the form of the path integral for ordinary quantum mechanics. The path integral is given by

$$\begin{equation}Z(q)=\int Dq(t)\exp[iS(q)] =\int Dq(t)\exp\left[i\int_0^TL(q)dt \right],\end{equation}$$

where $\int Dq(t)$ represents the integral over paths, and $L(q) = \tfrac{1}{2}m\dot{q}^2-V(q)$ generally. Say, instead of working in the complex plane, we want a Euclidean, or classical, path integral, then we can perform a Wick Rotation on $Z(q)$ by taking $t\to t/i$ by abusing the fact that the oscillatory phase factors from the different paths included in $\int Dq(t)$ cancel out. And so we obtain that

$$\begin{align} Z(q) &=\int Dq(t)\exp\left[\int_0^T \left(\frac{1}{2}m\left(i\frac{dq}{dt}\right)^2-V(q)\right) dt \right]\nonumber \\ &=\int Dq(t)\exp\left[\int_0^T \left( - \frac{1}{2} m \dot{q}^2-V(q)\right) dt \right]\nonumber \\ &=\int Dq(t)\exp\left[- \int_0^T \left(\frac{1}{2}m\dot{q}^2+V(q)\right) dt \right],\end{align}$$

which is the Euclidean path integral. Wick rotation, although seemingly trivial now, will be of immense use when extending to quantum field theory. In fact, keep wick rotations in mind as we will use them in the next example as well.

### Interacting Lagrangian

Let's move on to a more complicated example. We'll start with a nice quadratic potential with a quartic term given by $$L=-\frac{1}{2}m^2 q^2 -\frac{\lambda}{4!}q^4+Jq.$$ Before we continue,

> why did we choose this Lagrangian?

Well, firstly, we want to eventually be able to do quantum field theory and so, instead of starting with a free theory, which can be found here, without any interactions between the particles, we want to introduce an anaharmonic term, $(\lambda/4!) q^4$. Next, the term $Jq$, actually represents the source and sink term for the particles because, obviously, these particles need to borne out of something[note]This term might make more sense if we were to dip into the field theory for a second. Suppose that we were looking at fields instead of particles, so $\phi$ instead of $q$, and suppose we were specifically looking at the electromagnetic potential, then the source field, $J$, would be the electric current.[/note]. Finally, notice that there is no kinetic term in the Lagrangian, as $q$ has no dependence on time, which also kills of the time integral inside the exponential, and this was done for added simplicity.  So the full path integral becomes,

$$\begin{equation}Z(q,J) = \int_{\infty}^{\infty}dq \exp\left[-\frac{1}{2}mq^2 -\frac{\lambda}{4!}q^4+Jq \right].\end{equation}$$

Now, let's solve this and obtain the Feynman rules.

### Feynman Rules

We expand Equation (3) with respect to $\lambda$ to obtain

\begin{equation*}Z(q,J) =\int_{\infty}^{\infty}dq\ e^\left(-\frac{1}{2}mq^2 +Jq\right) \left(1 - \frac{\lambda}{4!} q^4 + \frac{1}{2}\left(\frac{\lambda}{4!}q^4\right)^2 - \cdots \right).\end{equation*}

Now, the super nifty trick, that is pretty much used to death in path integral QFT, is to represent the series as a sum of derivatives since $$q^{4n}\exp(Jq) = \left(\frac{d}{dJ}\right)^{4n}\exp(Jq).$$ The best part about this is that the derivative can then be pulled out of the integral thereby simplifying to an extent that a common Gaussian trick can be used to solve it.  So, with that in mind, we have

\begin{align*}Z(q,J) &=\int_{\infty}^{\infty}dq\ e^\left(-\frac{1}{2}mq^2 +Jq\right) \left(1 - \frac{\lambda}{4!} q^4 + \frac{1}{2}\left(\frac{\lambda}{4!}q^4\right)^2 - \cdots \right)\\ &= \int_{-\infty}^{\infty} dq\left[\lim_{m\to\infty}\sum_{n=0}^{m}\frac{1}{n!}\left(-\frac{\lambda}{4!}\frac{d^4}{dJ^4}\right)^n \right]e^\left(-\frac{1}{2}mq^2 +Jq\right) \\ &= \left[\lim_{m\to\infty}\sum_{n=0}^{m}\frac{1}{n!}\left(-\frac{\lambda}{4!}\frac{d^4}{dJ^4}\right)^n \right]\int_{-\infty}^{\infty}dqe^\left(-\frac{1}{2}mq^2 +Jq\right) \\ &= \exp \left(-\frac{\lambda}{4!}\frac{d^4}{dJ^4}\right)\int_{-\infty}^{\infty}dqe^\left(-\frac{1}{2}mq^2 +Jq\right). \end{align*}

Now we can tackle the integral, first we need to complete the square to get the argument of the exponent into the correct form such that we evaluate it as a gaussian integral, so $$-\left(\frac{m}{\sqrt{2}}q-bJ^2\right)^2 = -\left(\frac{m^2}{2} q^2-2b\frac{m}{\sqrt{2}}J + J^2b^2\right).$$Clearly $b=1/(\sqrt{2}m)$, substituting this back in we find that we have an extra $-\frac{J^2}{2m}$ so we add a $\frac{J^2}{2m}$ term to the argument of the exponent. Therefore

\begin{align*} &Z(q,J) =\exp\left(-\frac{\lambda}{4!}\frac{d^4}{dJ^4}\right)\int_{-\infty}^{\infty}dq e^\left(-(mq/\sqrt{2} - Jb)^2 + J^2/(2m^2) \right)\\ &=\exp\left(-\frac{\lambda}{4!}\frac{d^4}{dJ^4}\right)\exp\left(\frac{J^2}{2m^2}\right) \int_{-\infty}^{\infty}dq \exp\left[ -\frac{m^2}{2} \left(q-\frac{J}{m^2}\right)^2\right]\end{align*}

If we perform the change of variables $x=q\ - J/m^2$, such that $dx =dq$, we can use the familiar result[note]It still weirds me out that $\pi$ somehow creeps up, its almost as if physics needs $\pi$.[/note] that

\begin{equation*}\int_{-\infty}^{\infty} dx \exp\left(-\frac{m^2}{2}x^2\right) = \left(\frac{2\pi}{m^2}\right)^{1/2}, \end{equation*}

to obtain

\begin{equation}\boxed{Z(q,J)=\sqrt{\frac{2\pi}{m^2}}\exp\left(-\frac{\lambda}{4!}\frac{d^4}{dJ^4}\right)\exp\left(\frac{J^2}{2m^2}\right).}\end{equation}

And there we have it, for the Lagrangian given above, we have solved the path integral exactly! Notice that $Z$ no longer has an explicit dependence on $q$, so we will drop it. Next, if $J=0$ and $\lambda=0$, then we would be left with the common factor $$Z(J=0,\lambda=0) = \sqrt{2\pi/m^2} \equiv Z_0.$$ So the meat, and the bones, of $Z(J)$ are the exponential terms. Now, let's just ask a standard question,

> what's the first expansion of both exponentials such that we get a nontrivial answer?

By non-trivial, we mean a case where two particles were to interact. Well, as we will soon see, this corresponds to the term that is of order $J^4$ and $\lambda$ which we can pull from the expansion. In fact, we have that

\begin{align*} Z(J)&=Z_0\left(1-\frac{\lambda}{4!} \frac{d^4}{dJ^4} + \frac{1}{2} \left(\frac{\lambda}{4!} \frac{d^4}{dJ^4}\right)^2+\cdots\right)\exp\left(\frac{J^2}{2m^2}\right)\\ &=Z_0\left(1-\boxed{\frac{\lambda}{4!} \frac{d^4}{dJ^4}} + \frac{1}{2} \left(\frac{\lambda}{4!} \frac{d^4}{dJ^4}\right)^2+\cdots\right)\\ &\times\left(1+\frac{J^2}{2m^2}+\frac{1}{2}\left(\frac{J^2}{2m^2}\right)^2+\cdots \boxed{\frac{1}{4!}\left( \frac{J^2}{2m^2}\right)^4}+\cdots\right).\end{align*}

If we multiply and operate the boxed terms, we will obtain the term

$$Z(J)=\cdots - \frac{\lambda}{4!} \left(\frac{8!}{4!4!}\right) \left(\frac{1}{2m^2}\right)^4 J^4 +\cdots.$$

Alright, so what do we know? We know that

Two particles will interact. So they must meet at a point.
Each particle has a source and a sink. Therefore we need, and have four $J$ terms.
Each particle needs to have a line associated with before and after their interaction.
Interaction at $\lambda$ between two particles arising from the source $J$ and dying at sink $J$.

So with that physical intuition, we can quickly assign $\lambda$ to the first item, $J^4$ to the second item, and $(1/2m^2)^4$ to the third point. Voila;

And so, we have our first Feynman diagram. Well done. We'll list the Feynman rules for completeness below, but this is the extent of studying path integral quantum field theory. Only more complicated iterations of this same procedure exist ahead, but we have ushered into mastering path integral quantum field theory.

### Feynman Rules

Diagrams are made of lines & vertices. Four lines must meet to form a vertex.
Each vertex has a $-\lambda$[note]The negative is supposed to be on the figure above.[/note] associated with it.
Each line has a $1/m^2$ associated with it.
Each end has a $J$.