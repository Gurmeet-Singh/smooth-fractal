---
layout: article
title:  "Blackhole Kinematics"
categories: Science
comment: true
---
First thing anybody learns in general relativity (GR in short) is that, in GR, gravity is not a force it's a pseudo force, experienced because the space-time is not flat. Now, when I learnt the fact the only question arose in my mind was - how, in the hell, can I even start to quantify such a statement? I can imagine this might be the exact problem that Einstein faced. Soon, I learned that the non-flatness of the spacetime can be represented by a metric tensor. And learnt that, in GR, in spherically symmetric static case the metric turns out to be Schwarzschild metric. But I couldn't figure out how to work out the trajectories. So the purpose of this article is to explain exactly this, that is how to calculate the trajectories in a given metric.

Let's start with reviewing how all this works in Newtonian mechanics. In Newtonian mechanics, we have dynamical laws to calculate forces in given situations, for example Newton's Law of Gravity, and then there are kinematic laws to workout the trajectories given the force, that is Newton's laws of motion.

Similarly, in general relativity first there are dynamic equations, that is Einstein's field equations, which can be solved for the spacetime metric and then there is kinematic equation, that is geodesic equation, which is very similar to Newton's second law of motion.
But using geodesic equation to workout the trajectories is very cumbersome and hides all the fun parts behind the calculations.

So, let's try another approach. For gravity, there is an equivalent Lagrangian formulation for the Newtonian mechanics in which dynamic part is encoded in the potential term and the kinematic part is encoded in the kinetic term and Lagrangian is "kinetic - potential".

And it turns out in the Lagrangian formulation of general relativity, though the dynamic part (Einstein-Hilbert Action, equivalent to Einstein's field equations) is not easy to use, but the kinematic part is really easy.

To calculate the trajectories you just need to minimise the action -

$$
  A = -\int mc\sqrt{g_{\mu\nu}\frac{dx^\mu}{d\tau}\frac{dx^\nu}{d\tau}} d\tau
$$

If you're facing this Lagrangian for the first time, it might seem daunting. So, let's see how to work with such Lagrangian by an example. We know the spherically symmetric static case results in Schwarzschild metric, which is given by -

$$
  g_{\mu\nu}\,dx^\mu dx^\nu = \left(1-{\frac {r_{\mathrm {s} }}{r}}\right)c^2\,dt^2-\left(1-{\frac {r_{\mathrm {s} }}{r}}\right)^{-1}\,dr^2-r^2\left(d\theta ^2+\sin ^2\theta \,d\varphi ^2\right)
$$

where \\(r_{\mathrm {s} } = \frac{2GM}{c^2}\\) is the Schwarzschild radius. Now, let's see if we can reproduce the Newtonian mechanics from above in the limiting case. First, using coordinate time instead of proper time in action and substituting Schwarzschild metric, we get -

$$
  A = -\int dt\, mc\sqrt{\left(1-\frac{r_{\mathrm{s}}}{r}\right)c^2 - \left(1-{\frac{r_{\mathrm{s}}}{r}}\right)^{-1}\,\dot{r}^2 - r^2\left(\dot{\theta}^2+\sin^2\theta\,\dot{\varphi}^2\right)}
$$

And we know -

$$
  v^2 = \dot{r}^2 + r^2\left(\dot{\theta}^2+\sin^2\theta\,\dot{\varphi}^2\right)
$$

So, the Lagrangian will be,

$$
  \begin{align}
    L & = -mc\sqrt{c^2-\frac{2GM}{r} - \frac{r_{\mathrm{s}}\dot{r}^2}{r - r_{\mathrm{s}}} - v^2} \\
    & = -mc^2\sqrt{1-\frac{r_{\mathrm{s}}}{r} - \frac{r_{\mathrm{s}}(\dot{r}/c)^2}{r - r_{\mathrm{s}}} - \frac{v^2}{c^2}}
  \end{align}
$$

Note that, we haven't used any approximations yet. Now, let's apply the approximation -

$$
  c^2 \gg v^2 + \frac{2GM}{r} \gg \frac{r_{\mathrm{s}}\dot{r}^2}{r - r_{\mathrm{s}}}
$$

We can obtain,

$$
  \begin{align}
    L &= -mc^2\left(1-\frac{1}{2\,c^2}\left(v^2 + \frac{2GM}{r}\right)\right) \\
      &= -mc^2 + \frac{1}{2}mv^2 + \frac{GMm}{r}
  \end{align}
$$

Which is, except the rest energy term, just the classical Lagrangian. So, we reproduced Newtonian mechanics without much trouble.

But what about projectiles before approximation? The canonical momentums and Hamiltonian for the Lagrangian before approximations are -

$$
  P_r = \frac{-m^2c^2}{L}\left(1-\frac{r_{\mathrm{s}}}{r}\right)^{-1}\dot{r}
$$

$$
  P_{\theta} = \frac{-m^2c^2}{L}r^2\dot{\theta}
$$

$$
  P_{\phi} = \frac{-m^2c^2}{L}r^2sin^2\theta\dot{\phi}
$$

$$
  H = P_t = \frac{-m^2c^4}{L}\left(1-\frac{r_{\mathrm{s}}}{r}\right)
$$

From above, a bit of symbol crunching produces -

$$
  \left(1-{\frac{r_{\mathrm{s}}}{r}}\right)^{-1}c^{-2}\,H^2-\left(1-{\frac {r_{\mathrm {s} }}{r}}\right)\,P_r^2-r^{-2}P_{\theta}^2-r^{-2}sin^{-2}\theta P_{\phi}^2 = m^2c^2
$$

That is,

$$
  g^{\mu\nu}P_{\mu}P_{\nu} = m^2c^2
$$

We could've used the above relation as the starting point of our analysis. That is, just define Hamiltonian using above relation and then we can use the Hamilton equations of motion.

Anyway, as the Lagrangian is time independent so Hamiltonian is conserved, so we can substitute $$L$$ with it's expression in terms of $$H$$ and as $$\phi$$ is cyclic variable so $$P_{\phi}$$ is also conserved. And for $$\theta$$, we can use Euler-Lagrange equation -

$$
  \dot{P_{\theta}} = \frac{\partial L}{\partial \theta} = \frac{-m^2c^2}{L}\,r^2\,sin\theta\,cos\theta\,\dot{\phi}^2 = cot\theta\,\dot{\phi}\,P_{\phi}
$$

At this point, without the loss of generality we can assume the initial conditions $$\theta(0) = 90^{\circ}$$ and $$\dot{\theta}(0) = 0^{\circ}/s$$. Which implies $$P_{\theta}(0)=0$$.

We know $$\theta$$ and $$P_{\theta}$$ follows the relation -

$$
  \frac{d}{dt}
  \begin{bmatrix}
    \theta \\ P_{\theta}
  \end{bmatrix}
  = c^2\,H^{-1}\,\left(1-{\frac{r_{\mathrm{s}}}{r}}\right)\,r^{-2}
  \begin{bmatrix}
    P_{\theta} \\ \frac{cos\theta}{sin^3\theta}P_{\phi}^2
  \end{bmatrix}
$$

From here it's not very hard to see that the equation above follows the requirements of Picard-Lindel&#x00F6;f Theorem as long as $$r>(1+\epsilon)\,r_{\mathrm{s}}$$ for some fixed $$\epsilon>0$$. So, by Picard-Lindel&#x00F6;f Theorem, the above equation has a unique solution, but we already know a solution that is,

$$
  \begin{bmatrix}
    \theta \\ P_{\theta}
  \end{bmatrix}
  =
  \begin{bmatrix}
    90^{\circ} \\ 0
  \end{bmatrix}
$$

So, $$\theta$$ remains $$90^{\circ}$$ that is the motion is planar! This can be seen as a weak form of Kepler's First Law. But the path is not elliptical, though we haven't seen it in the equations yet.

So, we got something similar to Kepler's First Law, but what about others. Kepler's Third Law doesn't make sense if path is not periodic, which it isn't, in general. But can Kepler's Second Law be true? Kepler's Second Law is equivalent of saying that the force is central, so is the pseudo-force in Schwarzschild space-time central? It turns out the answer is no. The force/pseudo-force is central if $$\vec{r}\times \vec{a} = 0$$ where $$\vec{a}$$ is acceleration, which is same as saying $$\vec{r}\times \vec{v}$$ is constant.

$$
  \begin{align}
    \vec{r}\times \vec{v} & = r\,\hat{r}\times(\dot{r}\,\hat{r}+r\,\dot{\theta}\,\hat{\theta}+r\,sin\theta\,\dot{\phi}\,\hat{\phi}) \\
    & = r^2\,\dot{\phi}\,\hat{\theta} \\
    & = \frac{-L\,P_{\phi}}{m^2\,c^2}\,\hat{\theta} \\
    & = c^2\,P_{\phi}\,H^{-1}\,\left(1-{\frac{r_{\mathrm{s}}}{r}}\right)\,\hat{\theta}
  \end{align}
$$

which isn't a constant, though very close to it. If $$r\gg r_{\mathrm{s}}$$ then it's almost a constant and agrees with the Newtonian case. In general, direction remains constant but magnitude decreases as the projectile get near the event horizon. So, pseudo-force is not central. In particular, acceleration vector and radial vector are not exactly anti-parallel. I'll leave it to the readers to figure out the exact direction of the acceleration, in particular when is the acceleration retarded and when is it advanced.

Finally for the exact analysis, let's work out the corrected version of Newton's Law of Gravity. For that we need to apply Euler-Lagrange equation for $$r$$ coordinate.

$$
  \begin{align}
    \dot{P_r} & = \frac{\partial L}{\partial r} \\
    \frac{d}{dt}\left(c^{-2}H\left(1-{\frac{r_{\mathrm{s}}}{r}}\right)^{-2}\dot{r}\right) & = -\frac{c^{-2}H}{2}\left(1-{\frac{r_{\mathrm{s}}}{r}}\right)^{-1}\left(\frac{2GM}{r^2}+\frac{r_{\mathrm{s}}\dot{r}^2}{(r-r_{\mathrm{s}})^2}\right)
  \end{align}
$$

By simplifying further,

$$
  \ddot{r} = -\left(1-{\frac{r_{\mathrm{s}}}{r}}\right)\frac{GM}{r^2} + \frac{3}{2}\left(1-{\frac{r_{\mathrm{s}}}{r}}\right)^{-1}\frac{r_{\mathrm{s}}\dot{r}^2}{r^2}
$$
