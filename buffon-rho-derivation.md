# How the Integrand Equals $\rho(x)$ — Problem 1.12

It comes from a **change-of-variables on probability densities** — the result of Problem 1.12.

## The rule

If $\theta$ has density $\rho_\theta(\theta)$ and $x = f(\theta)$ is a smooth (locally invertible) function, then conservation of probability requires

$$\rho_\theta(\theta)\,|d\theta| = \rho(x)\,|dx|,$$

so

$$\rho(x) = \rho_\theta(\theta)\,\bigg|\frac{d\theta}{dx}\bigg|.$$

## Why $\theta$ uniform gives $\rho_\theta(\theta) = 1/\pi$

By the **definition of "uniform"** + **normalization**.

**Uniform means constant density.** "$\theta$ is uniformly distributed on $[0,\pi]$" is just saying every angle in that range is equally likely — so the probability density $\rho_\theta(\theta)$ is some constant $c$, independent of $\theta$:

$$\rho_\theta(\theta) = c \quad \text{for } \theta \in [0, \pi].$$

**Normalization fixes the constant.** Every probability density has to integrate to 1 over its domain (the needle has to point *somewhere*):

$$\int_0^\pi \rho_\theta(\theta)\,d\theta = 1.$$

Plug in $\rho_\theta = c$:

$$\int_0^\pi c\,d\theta = c\cdot\pi = 1 \quad\Longrightarrow\quad c = \frac{1}{\pi}.$$

So $\rho_\theta(\theta) = 1/\pi$.

**General rule:** uniform on $[a, b]$ gives density $\dfrac{1}{b-a}$. The interval $[0, \pi]$ has length $\pi$, so the density is $1/\pi$. If you'd let the needle swing over $[0, 2\pi]$ instead, you'd get $1/(2\pi)$ — but by symmetry only half the range is needed since $\cos\theta$ already covers $[-l, l]$ on $[0, \pi]$.

## Applied to the needle

The needle pivots freely, so the angle is uniformly distributed:

$$\theta \sim \text{Uniform}[0, \pi] \quad\Longrightarrow\quad \rho_\theta(\theta) = \frac{1}{\pi}.$$

The horizontal projection of the tip is

$$x = l\cos\theta.$$

Differentiate:

$$\frac{dx}{d\theta} = -l\sin\theta \quad\Longrightarrow\quad \bigg|\frac{dx}{d\theta}\bigg| = l\sin\theta.$$

Now eliminate $\theta$ in favor of $x$ using $\sin\theta = \sqrt{1 - \cos^2\theta} = \sqrt{1 - x^2/l^2}$:

$$\bigg|\frac{dx}{d\theta}\bigg| = l\sqrt{1 - x^2/l^2} = \sqrt{l^2 - x^2}.$$

Plug in:

$$\rho(x) = \rho_\theta(\theta)\,\bigg|\frac{d\theta}{dx}\bigg| = \frac{1}{\pi}\cdot\frac{1}{\sqrt{l^2 - x^2}}.$$

That's the integrand.

## Sanity check / intuition

- The factor $1/\pi$ is the uniform density in $\theta$.
- The $1/\sqrt{l^2-x^2}$ blows up as $x \to \pm l$ because $dx/d\theta = -l\sin\theta \to 0$ near $\theta = 0, \pi$ — equal $d\theta$ intervals near the endpoints get squeezed into vanishingly small $dx$ intervals, so probability density *piles up* near the tips. Picture the projection of a uniformly spinning needle onto a horizontal axis: the tip lingers near the extremes and zips through the middle. That's exactly the shape of $\rho(x)$.
- Normalization check:

$$\int_{-l}^{l}\frac{dx}{\pi\sqrt{l^2-x^2}} = \frac{1}{\pi}\Big[\arcsin(x/l)\Big]_{-l}^{l} = \frac{1}{\pi}\left(\frac{\pi}{2} - \left(-\frac{\pi}{2}\right)\right) = 1. \checkmark$$
