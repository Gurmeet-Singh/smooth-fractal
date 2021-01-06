---
layout: article
title: "Structuralist approach to Exponential"
categories: Mathematics
---

Euler's famous identity -

$$
  e^{i\pi} = -1
$$

There are two views I have encountered regarding Euler's identity -
1. it is the most beautiful equation, it connects four really fundamental constants of maths in one simple looking equation
2. it is just a definition, one way to extent the definition of exponential function from real domain to complex domain

My motivation to write this article is that to me both of these views seem unsatisfactory. The first view talks about mathematical beauty which is, to say the least, a vague concept and just saying that it connects four fundamental constants doesn't do justice to the awesomeness of the equation, that is, it doesn't give you anything mathematically relevant. And to counter the second view, it is surely not *just* a definition, it is a definition which works really well. This article will present a structuralist view on exponential, which seems more satisfactory to me. 

So, what is structuralism? Well, borrowing a few words from Wiki, "structuralism maintains that mathematical objects do not possess any intrinsic properties but are defined by their external relations in a system". In simple words, structuralist thinks maths objects as internet gen kids, that is, completely defined by their social interaction with each other. Regardless of your opinion on structuralism, as you will see, structuralist point of view is sometimes helpful in understanding many concepts.

Now, how structuralist point of view can help us understand exponential/Euler's identity? Let us start with elementary school definition of exponential -

$$
  e^x = e * e * e * ... * e\ (x\ times)\ with\ e^0 = 1
$$

Firstly notice, for this equation to work, $$x$$ needs to be a natural number. But still, this definition is not mathematically rigorous as '$$…$$' is not precisely defined. Fortunately, it can be easily remedied as according to structuralist point of view every natural number is either zero or successor of a natural number (it is essentially the natural numbers as in Peano's axioms). So, defining the exponential for zero and successor should be enough -

$$
  e^{x+1} = e^x * e\ with\ e^0 = 1
$$

As you can see, it is just recursion, commonly used in programming.

Now, within natural numbers, an equivalent definition is, a function following -

$$
  f(x+y) = f(x) * f(y)\ with\ f(0) = 1\ and\ f(1) = e
$$

Though it is not a good definition to be used in programming, but for a mathematician it does have some advantages. First, it defines exponential as group homomorphism (simply, a way to convert one operation, $$ + $$, to another, $$ * $$), so the well developed theory of groups and homomorphisms can help us study and use exponential. Second, it doesn't use recursion, so it can be used to extend the definition. It is not hard to verify that it uniquely extends the definition to all integers. Even for rationals, the only ambiguity is with rationals having even denominator, as they can have two values, one positive and other negative. Let us not worry about that for now.

Next step is to extend it for real number inputs. But before that, what is so special about homomorphisms? Homomorphism is all about how similar two operators behave. So, exponential function measures how similar, the structure of multiplication is to the structure of addition. For example, for every equation involving only $$ + $$ you can obtain a respective equation where numbers are replaced by exponentials and $$ + $$ by $$ * $$, like -

$$
  a + b = c \Rightarrow (e^a) * (e^b) = (e^c)
$$

So, in this particular sense homomorphisms are structure preserving maps. On a similar note, what about ordering structure? It turns out exponential function, defined so far, also preserve ordering structure for any number greater than $$1$$ for $$e$$ (if we select positive values for square roots removing the ambiguity mentioned regarding rational inputs). That is -

$$
  a < b \Rightarrow (x^a) < (x^b) \qquad \forall\ x > 1
$$

Similarly,

$$
  a < b \Rightarrow (x^a) > (x^b) \qquad \forall\ 0 < x < 1
$$

Now, returning back to reals. One way to extend the definition to reals is to demand the above identities to hold for real exponents as well. That is because the real numbers can be defined as Dedekind cuts over rationals. Form a structuralist point of view, it can be stated as real numbers have an extra property that the order is complete. That is, for every non-empty subset that has an upper bound, has a least upper bound as well. For example, the sequence

$$
  3 < 3.1 < 3.14 < 3.141 < 3.1415 < 3.14159 < 3.141592 ...
$$

has least upper bound, that is $$\pi$$, in reals but not in rationals. And one can extend the definition of exponent by demanding that this structural is preserved.

Real numbers can also be defined using Cauchy sequences. Again from the structuralist point of view what matters is that the reals have another property known as Cauchy completeness. Stated simply, it ensures that every sequence of reals converge to real, if converges at all. For example -

$$
  \frac{1}{1}, \frac{2}{1}, \frac{3}{2}, \frac{5}{3}, \frac{8}{5}... \rightarrow \phi
$$

The ratio of consecutive fibonacci numbers (which are all rationals, of course) converges to golden ration (which is irrational). So, rationals don't have this property. This type of property is studied in topology (which we don't have to discuss further, fortunately… :-)) and the maps which preserves such a property are, the well known, 'continuous maps'. If we add the condition to preserve this structure as well, that is condition that exponential is a continuous map, we obtain our familiar exponential for reals. So for reals, exponential can be defined as continuous homomorphism from $$ + $$ to $$ * $$ with one anchor, that is its value at $$1$$.

But what about complex inputs? One good natural choice for structure preserving map for complex numbers is analytic map, for example analytic map with non-vanishing derivative is always locally one-to-one. And also non-constant analytic map is, what is called, open map which ensures that, locally, the inverse will be continuous. So, what if we define exponential as analytic homomorphism from $$ + $$ to $$ * $$ with one anchor, that is its value at $$1$$. First note that, it extends our definition over reals, so we can use all what we know about real exponential. In particular -

$$
  \lim_{x\rightarrow 0} \frac{e^x - 1}{x} = 1
$$

And we know that analytic function must follow Cauchy-Riemann equations, that is for $$f(z)=u(x,y)+iv(x,y)$$ where $$z=x+iy$$ -

$$
  \frac{\partial u}{\partial x} = \frac{\partial v}{\partial y}\ and\ \frac{\partial u}{\partial y} = - \frac{\partial v}{\partial x}
$$

Treating $$f$$ as a complex valued function of two real variables $$x$$ and $$y$$ (instead of one complex variable $$z$$), the above equations can be written as -

$$
  \frac{\partial f}{\partial x} = \frac{1}{i}\frac{\partial f}{\partial y}
$$

Using the exponential as $$f$$ and substituting usual first principle definition of derivative, and a bit of cancelling we obtain (let us call it equation $$1$$) -

$$
  \lim_{y\rightarrow 0} \frac{e^{i y} - 1}{y} = i
$$

Which is particularly satisfying because of its parallels with the identity we already know for reals. After a bit of symbol crunching the above can also be written as (let us call it equation $$2$$) -

$$
  \frac{d e^{i y}}{dy} = i e^{i y}
$$

Which is again very satisfying as we already expect it by analogy with chain rule. Finally, substituting -

$$
  e^{i y} = u(y) + i v(y)
$$

In hope of finding the value of $$u$$ and $$v$$ in terms of $$y$$, we obtain -

$$
  \frac{d u}{dy} = - v\ and\ \frac{d v}{dy} = u
$$

For this pair of equations the general solution is know (first by eliminating $$v$$ it turns out $$u$$ follows wave equation, whose general solution, that is scaled trigonometric function, can then be substituted to get the value of $$v$$) -

$$
  u(y) = c_1 \cos(y + c_2)\ and\ v(y) = c_1 \sin(y + c_2)
$$

And finally using equation $$e^{0}=1$$, we obtain -

$$
  c_1 = 1\ and\ c_2 = 0
$$

Giving us the famous Euler's identity -

$$
  e^{i y} = \cos y + i \sin y
$$

And in particular, for $$y=\pi$$ -

$$
  e^{i \pi} = -1
$$

So, as you can see, it is not *just* a definition or *just* a beautiful equation containing four maths constants, rather it is a unique solution to a problem, a problem to find an analytic extension to real exponential. Moreover, as we saw real exponential can itself be seen as the unique solution to the problem of finding a continuous homomorphism from $$ + $$ to $$ * $$ with one anchor, that is its value at $$1$$, in fact the anchor is just to make it unique, power function with any non-identity positive base is continuous homomorphism from $$ + $$ to $$ * $$.

It is also worth noting that analyticity is not the only condition which extends the real exponential to familiar complex exponential, many other natural looking conditions gives the same result, for example, instead of analyticity, we could have used the condition of conformality or following equation $$1$$ or equation $$2$$ mentioned above or can directly use the power series.

## So what's next?

One can ask, can we go further, for example extending to quaternions? Here we encounter a big difficulty that quaternion multiplication is not commutative in general but quaternion addition is, so if we push the condition of exponential being homomorphism from $$ + $$ to $$ * $$, its going to have some weird consequences and consequently  the commonly used definition of quaternion exponential is not in fact an homomorphism from $$ + $$ to $$ * $$. There are many ways to obtain the commonly used quaternion exponential from where we are right now, one of them is just to use the usual infinite series, that is -

$$
  e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} + ...
$$

This series can be derived from our definition and remains true for real as well as complex exponential. This is the approach which is commonly mentioned in the texts.

Another way is to observe the relation between structure of complex numbers and quaternions. We know that the subspace obtained by $$1$$ and any fixed unit quaternion is isomorphic to complex numbers with the fixed unit quaternion identified as $$i$$ of complex numbers. So, what if we treat the unit quaternion part of the given quaternion as complex $$i$$ and use Euler's identity to define exponential, that is -

$$
  e^{n_0 + |n|\hat{n}} = e^{n_0}(\cos |n| + \hat{n} \sin |n|)
$$

It turns out this definition is equivalent to the definition using power series.

There is one more really interesting way, which revolves around a really important property of exponentials and extends to many other mathematical objects and forms the basis for the link between lie groups and lie algebra. But that's a story for another day.
