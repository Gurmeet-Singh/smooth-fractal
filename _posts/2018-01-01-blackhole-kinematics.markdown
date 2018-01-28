---
layout: post
title:  "Blackhole Kinematics"
date:   2018-01-01 09:04:23 +0530
categories: Science
---
First thing anybody learns in general relativity (GR in short) is that, in GR, gravity is not a force it's a pseudo force, experienced because the space-time is not flat. The first question arised in my mind when I learnt the fact was how, in the hell, can I even start to quantize such a statement? I can imagine this might be the exact problem that Einstein faced. Soon, I learned that the non flatness of the spacetime is represented by a metric tensor. And learnt that, in GR, in spherical symmetric static case the metric turns out to be Schwarzschild metric. But I couldn't figure out how to work out the trajectory. So the purpose of this article is to explain exactly this, that is how to calculate the trajectories in a given metric.

Let's start with reviewing how all this works in newtonian mechanics. In newtonian mechanics, we have dynamical laws to calculate forces in given situations, for the examples Newton's Law of Gravity, and then there are kinematic laws to workout the trajectories given the force, that is Newton's laws of motion.
Similarly, in general relativity first there are dynamic equations, that is Einstein's field equations, which can be solved for the spacetime metric and then there is kinematic equation, that is geodesic equation, which is very similar to Newton's second law of motion.
But using geodesic equation to workout the trajectories is very cumbersome and hides all the fun parts behind the calculations.
So, let's try another approach. For gravity, there is an equivalent Lagrangian formulation for the newtonian mechanics in which dynamic part is encoded in the potential term and the kinematic part is encoded in the kinetic term and Lagrangian is kinetic - potential.
And it turns out in the Lagrangian formulation of general relativity, do dynamic part (Einstein-Hilbert Action, equivalent to Einstein's field equations) is still not easy to use, but the kinematic part becomes really easy.
To calculate the trajectories you just need to minimise the action -
