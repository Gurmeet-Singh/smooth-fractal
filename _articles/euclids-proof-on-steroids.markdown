---
layout: article
title:  "Euclid's Proof on Steroids"
categories: Mathematics
comments: true
---

We all know and love the proof of infinitude of primes by Euclid, but one of the most amazing thing about Mathematics is the possibility of generalizing or modify the proofs to obtain many more theorems. So, are there any cool modifications to Euclid's proof as well?

### Euclid's Original Proof
Let's start with Euclid's proof, it is a proof by contradiction, it proceeds as follows -
1. we start by assuming that set of primes is finite, let's say, $$\{p_1, p_2, p_3 ... p_n\}$$
2. construct $$N = \displaystyle \prod_{i=1}^{n}p_i + 1$$
3. by construction, $$N$$ is coprime to each one of $$\{p_1, p_2, p_3 ... p_n\}$$
4. so, $$N$$ must have a prime factor which is not present in $$\{p_1, p_2, p_3 ... p_n\}$$, hence the contradiction. Q.E.D

### Primes of form $$3\ (mod\ 4)$$ and more
It is possible to modify the argument to obtain the proof for infinitude of primes of form $$p=3\ (mod\ 4)$$. The basic idea is the fact that any number of form $$3\ (mod\ 4)$$ must have a prime factor of form $$3\ (mod\ 4)$$. So, if the number generated in the second step is of form $$3\ (mod\ 4)$$ then it must have a new prime of form $$3\ (mod\ 4)$$. So, argument in detail is -
1. we start by assuming that set of primes of form $$3\ (mod\ 4)$$ is finite, let's say, $$\{p_1, p_2, p_3 ... p_n\}$$
2. construct $$N = 4\displaystyle \prod_{i=1}^{n}p_i - 1$$
3. by construction, $$N$$ is coprime to each one of $$\{p_1, p_2, p_3 ... p_n\}$$
4. so, $$N$$ must have a prime factor of form $$3\ (mod\ 4)$$ which is not present in $$\{p_1, p_2, p_3 ... p_n\}$$, hence the contradiction. Q.E.D

Similarly, we can prove primes of form $$p=5\ (mod\ 6)$$ are infinite. In general, we can prove, for any $$n$$, primes of form $$p\neq 1\ (mod\ n)$$ are infinite.

Stronger result on these lines can be obtained by group theoretic considerations. Let's fix a number $$N$$, let $$P_{i, N}$$ is set of primes of form $$i\ (mod\ N)$$, $$U_N$$ is the group of units modulo $$N$$ and $$H$$ is any subgroup of $$U_N$$. Using the argument similar to the above, it's easy to show that $$\bigcup\limits_{i\in {U_N\backslash H}} P_{i, N}$$ is infinite as long as it's non-empty. For the strongest results we can assume $$H$$ to be maximal.

From the above result one can derive many non-trivial interesting conclusions. For example, for $$N=8$$ one can derive that at least 2 of $$P_{3, 8}$$, $$P_{5, 8}$$ and $$P_{7, 8}$$ are infinite.

Now, we know by Dirichlet's theorem on arithmetic progressions that there are infinitely many primes of form $$p=a\ (mod\ b)$$ as long as $$gcd(a, b) = 1$$ (For example, $$P_{3, 8}$$, $$P_{5, 8}$$ and $$P_{7, 8}$$ of last paragraph are all infinite). But the proof of it is very advance and long. On the other hand, the above special cases weren't much harder than Euclid's original proof itself.

So, are there any other special cases that can be proven just by modified Euclid's argument, may be with few bits of extra mathematics? The answer is, of course, yes. Let's look at primes of form $$p=1\ (mod\ 4)$$.

### Primes of form $$1\ (mod\ 4)$$
For the next version of powered up Euclid's argument, we need a fact, that is all the odd prime factors of $$x^2+1$$ are always of the form $$1\ (mod\ 4)$$. For now let's just take it for granted, now we can proceed as -
1. start by assuming that set of primes of form $$1\ (mod\ 4)$$ is finite, let's say, $$\{p_1, p_2, p_3 ... p_n\}$$
2. construct $$N = \displaystyle (\prod_{i=1}^{n}p_i)^2 + 1$$
3. by construction, $$N$$ is coprime to each one of $$\{p_1, p_2, p_3 ... p_n\}$$
4. so, $$N$$ must have a prime factor of form $$1\ (mod\ 4)$$ (because all the odd prime factors of $$x^2+1$$ are always of the form $$1\ (mod\ 4)$$) which is not present in $$\{p_1, p_2, p_3 ... p_n\}$$, hence the contradiction. Q.E.D

(In the above argument, there we do need to prove that $$x^2+1$$ can't be a power of $$2$$, but that's easy to prove by checking the residue modulo $$4$$.)

Now let's return to the fact we used, that is all the odd prime factors of $$x^2+1$$ are always of the form $$1\ (mod\ 4)$$.
1. Let's say $$p$$ is an odd prime factor of $$x^2+1$$, so -

    $$
    \begin{align}
      & x^2+1 & = &\ 0\ &(mod\ p) \\
      \implies & x^2 & = &\ -1\ &(mod\ p) \\
      \implies & x^4 & = &\ 1\ &(mod\ p)
    \end{align}
    $$

2. that is, the order of $$x$$ in $$U_p$$ (group of units modulo $$p$$) is $$4$$. So, by Langrage theorem, $$4\mid (p-1)$$. Hence proved.

### Primes of form $$1\ (mod\ n)$$
Let's analyze the above argument a bit more. It can be broken down into two part -
1. proving $$\{n^2+1\mid n\in \mathbb{N}\}$$ is prime-rich (see Appendix II) using an argument similar to Euclid's.
2. showing that prime factors of $$n^2+1$$ has to be either $$2$$ or of form $$1\ (mod\ 4)$$.

As it turns out, both of the above parts can be greatly generalized. Final versions will look like -
1. for any monic non-constant polynomial $$P$$, $$\{P(n)\mid n\in \mathbb{N}\}$$ is prime-rich. (can be proved using an argument similar to Euclid's)
2. odd prime factors of cyclotomic polynomial, $$\Phi_n(x)$$, has to be either prime factor of $$n$$ or of form $$1\ (mod\ n)$$.

One easy consequence of the above is the infinitude of primes of form $$1\ (mod\ n)$$.

Proof of the first part is just a more tricky pumped-up version of Euclid's argument. For a monic non-constant polynomial, $$P$$, it follows as -
1. start by assuming that set of primes of elements of $$\{P(x)\mid x\in \mathbb{N}\}$$ is finite, let's say, $$\{p_1, p_2, p_3 ... p_n\}$$
2. construct $$Q(x) = \displaystyle a^{-1}P(\alpha + ax\prod_{i=1}^{n}p_i)$$, where $$a$$ and $$\alpha$$ are such that $$P(\alpha)=a\neq 0$$ (which is always possible as $$P$$ is non-constant)
3. by expanding $$Q(x)$$ using formal Taylor series, we can see $$Q(x)\in \mathbb{Z}[x]$$ and is non-constant too
4. by construction, $$Q(x)=a^{-1}P(\alpha)=1\ (mod\ \displaystyle \prod_{i=1}^{n}p_i)$$
5. so, for some $$\beta$$ (as $$Q$$ is non-constant), $$Q(\beta)\neq 1$$. Hence $$Q(\beta)$$, as well as $$\displaystyle P(\alpha + a \beta\prod_{i=1}^{n}p_i)$$, must have a prime factor which is not present in $$\{p_1, p_2, p_3 ... p_n\}$$, hence the contradiction. Q.E.D

Well now the second part -
1. let $$p$$ is a prime factor of $$\Phi_n(a)$$, so $$\Phi_n(a) = 0\ (mod\ p)$$
2. from above we know $$a^n=1\ (mod\ p)$$, if $$n$$ is the order of $$a$$ then $$n \mid (p-1)$$ by Lagrange theorem, and we are done. So, let's assume the order of $$a$$ is $$m<n$$
3. because the order of $$a$$ is $$m$$, so $$\Phi_m(a) = 0\ (mod\ p)$$
4. so by equality $$x^n-1 = \displaystyle \prod_{d\mid n}\Phi_d(x)$$, $$a$$ is a multiple root of $$x^n-1$$ modulo $$p$$
5. so, it must be a root of the derivative as well, that is $$na^{n-1} = 0\ (mod\ p)$$
6. as $$a$$ is coprime to $$p$$, so $$n = 0\ (mod\ p)$$ and we are done.

### Appendix I - Choice of $$Q(x)$$
The only tricky part of the argument, to prove that for any monic non-constant polynomial $$P$$, $$\{P(n)\mid n\in \mathbb{N}\}$$ is prime-rich, was the selection of $$Q(x)$$, which can be justified as follows - from the proof for polynomial $$x^2+1$$, we know we want the construction to look something like $$N = P(\displaystyle \prod_{i=1}^{n}p_i)$$, and then we can analyze this modulo $$\displaystyle \prod_{i=1}^{n}p_i$$.

But there is a problem with it, that is as, modulo $$\displaystyle \prod_{i=1}^{n}p_i$$, $$N = P(0)$$, if $$P(0)=0$$ then $$N=0$$, which we don't want.

We know $$P$$ has to be non-zero for some input as it is non-constant, let's say $$P(\alpha)=a\neq 0$$, we want to use it somehow to modify $$N$$ such that it's guaranteed to be non-zero.

We know $$a^{-1}P(\alpha)=1$$, in particular $$a^{-1}P(\alpha)=1\ (mod\ \displaystyle \prod_{i=1}^{n}p_i)$$. Note that $$a$$ can be a multiple of any of the prime in the list, so $$a$$ might not have an inverse, in general. So, the simplest way to combine the above ideas would be to choose $$\displaystyle N=a^{-1}P(\alpha + a\prod_{i=1}^{n}p_i)$$, which can easily be shown to be an integer by Taylor expansion.

Our job is almost done, as this $$N$$ is guaranteed to be integer and $$1\ (mod\ \prod_{i=1}^{n}p_i)$$. But there is one little thing to take care of, we don't want $$N=1$$ itself. One way to make sure that can be to again use the non-constancy of $$P$$. That is, construct an infinite list of viable $$N$$s, then by non-constancy of $$P$$ only finitely many of them can be $$1$$. That's where our final construction comes in, that is -

$$
  Q(x) = \displaystyle a^{-1}P(\alpha + ax\prod_{i=1}^{n}p_i)
$$

### Appendix II - Prime-rich sets
We'll say a subset $$S$$ of $$\mathbb{N}$$ is prime-rich if the set of prime divisors of the elements of $$S$$ is infinite. (Note that, we are not talking about the primes but the prime divisors of the elements)

We know a lot about prime-rich sets. For example,
- Euclid's theorem can be stated as $$\mathbb{N}$$ is prime-rich.
- Any infinite subset of set of primes is prime-rich.
- Any superset of prime-rich set is prime-rich.
- For any $$a$$, $$\{a^n\mid n\in \mathbb{N}\}$$ is not prime-rich set.
- Euclid's original argument can be seen as generating a prime-rich set $$\{a_n\mid n\in \mathbb{N}\}$$ by recursion $$a_{n+1} = \displaystyle \prod_{i=0}^{n}a_i + 1$$ and $$a_0 = 2$$.
- Fermat numbers are prime-rich, as it can be generated by recursion $$F_{n+1} = \displaystyle \prod_{i=0}^{n}F_i + 2$$ and $$F_0 = 1$$, then we can proceed with an argument very similar to the above.
- Mersenne numbers are prime-rich, which is clear from the result that $$gcd(2^n-1, 2^m-1) = 1$$ iff $$gcd(n, m) = 1$$.
- Fibonacci numbers are prime-rich, which can easily be seen from the identity $$F_{gcd(a,b)} = gcd(F_a, F_b)$$ as well as from $$p\mid F_{p-(\frac{5}{p})}$$ for any prime $$p$$.
- For any monic non-constant polynomial, $$P$$, $$\{P(x)\mid x\in \mathbb{N}\}$$ is prime-rich. (see above for proof)
- If I define the product $$AB = \{ab\mid a\in A \wedge b\in B\}$$, then for any finitely many non-prime-rich sets $$A_1, A_2, A_3 ... A_i$$, $$A_1 A_2 A_3 ... A_i$$ is also non-prime-rich sets.

My question is - what are some general non-trivial result that can be proved about prime-rich sets? In particular, is there any generalization of the result about polynomials which includes exponentials as well, may be covering the cases like Fermat numbers, Mersenne numbers and may be Fibonacci numbers as well?

## References
- Dummit, David Steven., and Richard M. Foote. Abstract Algebra 3ed. Wiley, 2004.
  Many things in the above article are inspired from the exercises on pages 557.
