Around 1740, Leonard Euler discovered a formula that connected functions of complex arguments to trigonometric functions, effectively forming a link between analytic functions and geometric functions which eventually extended to topology, differential equations, and mathematical physics. All of this began with one simple formula, lauded by Richard Feynman as "the most remarkable formula in mathematics," and it is

$$e^{ix}=\cos(x)+i\sin(x), \text{ with } x\in\mathbb{R}. $$

<!--more-->

Here, we aim to prove the above formula. In 1702, Johann Bernoulli discovered the relationship

$\displaystyle \frac{1}{1+x^2} = \frac{1}{(1+ix)(1-ix)} =\frac{1}{2}\left(\frac{1}{1+ix}+\frac{1}{1-ix}\right),$

which was instrumental for Gauss as mathematicians at the time were unable to solve the integral

$\displaystyle \int^x\frac{dx}{1+x^2}.$

With Bernoulli's relationship, the integral can be rewritten as

$\displaystyle \int^x\frac{dx}{1+x^2}=\frac{1}{2}\left(\int^x\frac{dx}{1+ix}+\int^x\frac{dx}{1-ix}\right).$

Now, these integrals can be evaluated by a change of variables to obtain the solution as a combination of complex logarithms. Clearly, we have

$\displaystyle \frac{1}{2}\left(\int^x\frac{dx}{1+ix}+\int^x\frac{dx}{1-ix}\right)=\frac{1}{2i}\text{Log}(1+ix)-\frac{1}{2i}\text{Log}(1-ix).$

Definition $-$ The complex principle logarithm is defined as

$\displaystyle \text{Log}(z)=\ln\|z\|+i\theta,\text{ where } -\frac{\pi}{2} \le \theta \doteq \text{Arg}(z)  < \frac{\pi}{2}.$

Now, we switch to a geometric interpretation to determine the form of $\|z\|$ and $\text{Arg}(z)$. In fact, $\|z\|$ is the hypotenuse of the right triangle shown below, while $\text{Arg}(z)$ is the angle between the horizontal and the hypotenuse and can be obtained by considering $\arctan(b/a)$ since $z=a+ib.$

The geometric intrepretation for $z=1+ix$ may be seen here. The quantities of interest are $||z||=1+x^2$ and $\theta=\arctan(x/1).$ Returning to the logarithms, we have that

$$\displaystyle \begin{align*} \frac{1}{2i}\text{Log}(1+ix)-\frac{1}{2i}\text{Log}(1-ix) &= \frac{1}{2i} (\ln(1+x^2)+i\arctan(x)) \\ & -\frac{1}{2i} (\ln(1+x^2)+i\arctan(-x)).\end{align*}$$

Since $\arctan(-x)=-\arctan(x)$, we have that

$\displaystyle \frac{1}{2i}\text{Log}(1+ix)-\frac{1}{2i}\text{Log}(1-ix)$

$\displaystyle  =\frac{1}{2i}(\ln(1+x^2)-\ln(1+x^2)+i\arctan(x)+i\arctan(x)).$

By the properties of the Log, we can collapse the left hand side

$\displaystyle \frac{1}{2i} \text{Log}\left(\frac{1+ix}{1-ix}\right)=\arctan(x).$

Collecting the complex parts to the right hand side and exponentiating, we obtain

$\displaystyle \frac{1+ix}{1-ix}=\exp(2i\arctan(x)).$

Here, we have to be a bit more clever to realize that

$\displaystyle  \cos(\arctan(x))=\frac{1}{\sqrt{1+x^2}}\text{ and } \sin(\arctan(x)) = \frac{x}{\sqrt{1+x^2}}.$

Then, we can write

$\displaystyle \exp(2i\arctan(x))=\frac{1+ix}{1-ix}=\frac{(1+ix)^2}{1+x^2}=\cos^2(\arctan(x))(1+ix)^2.$

When we take the square root of both sides, we take the positive principle branch cut, as dictated by the principle logarithm, in order to obtain

$\exp(i\arctan(x))=\cos(\arctan(x))(1+ix)= \cos(\arctan(x)) + ix \cos(\arctan(x)).$

With the simple relation, $x\cos(\arctan(x))=\sin(\arctan(x))$, and our definition, $\theta=\arctan(x)$, we arrive at our desired result:

$\exp(i\theta)=\cos(\theta)+i\sin(\theta).$

A beautiful consequence of this is $\displaystyle \exp(i\theta)=-1.$

Photo Credit: The unit circle constructed by Euler's formula is shown here, clearly forming a link between geometry and analyticity. Credit to "Euler's formula" by gunther for the image. Licensed under CC BY-SA 3.0 via Wikimedia Commons.
