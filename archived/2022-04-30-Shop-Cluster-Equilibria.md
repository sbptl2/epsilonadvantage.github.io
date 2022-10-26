---
layout: post
---

A while back, I remember watching an interesting [TED video](https://www.youtube.com/watch?v=jILgxeNBK_8) offering an explanation for why stores tend to cluster together. They tell the story of Hotelling's Model of Spacial Clustering: Imagine two ice cream carts trying to sell ice cream on the board walk, which we'll think of as a one dimensional interval. Customers always go to the closest ice cream cart and come in uniformly distributed. In such a game, it's not hard to see that the Nash equilibrium occurs when both carts are at the middle of the interval. But telling this story to a friend, we bumped into a couple of interesting questions: Is this still the unique equilibrium case for more players? How important is it that we are playing over an interval?

Unfortunately, it's easy to see that things break down as soon as we add a third player on the line. Indeed, there is no pure nash equilibrium: Suppose that the players locate at $$0 \leq x_1 \leq x_2 \leq x_3 \leq 1$$ respectively. If $$x_1 \not = x_2$$ then we can increase $$x_1$$ and the first player gains more territory. So we have that $$x_1 = x_2$$. Similarly, we must have that $$x_2 = x_3$$. But now in the case where $$x_1 = x_2 = x_3$$, all three players share $$\frac{1}{3}$$ of the customers. But if $$x_1$$ decreases, than $$x_1$$ gets roughly $$\frac{1}{2}$$ of the customers. So this is also not a nash equilibrium.

Moving into two dimensions also doesn't seem to change much. Note that if there are only two players, it's easy to see that moving towards one another improves one's position (no matter what the shape of the playing field). If there are three players the computation becomes somewhat more complicated.



## Adding Players on the Line

To address the first question, we note that things break down as soon as we have three players on the line. Indeed, there is no pure nash equilibrium: Suppose that the players locate $$0 \leq x_1 \leq x_2 \leq x_3 \leq 1$$. If $$x_1 \not = x_2$$ then we can increase $$x_1$$ and the first player gains more territory. So we have that $$x_1 = x_2$$. Similarly, we must have that $$x_2 = x_3$$. But now in the case where $$x_1 = x_2 = x_3$$, all three players share $$\frac{1}{3}$$ of the customers. But if $$x_1$$ decreases, than $$x_1$$ gets roughly $$\frac{1}{2}$$ of the customers. So this is also not a nash equilibrium.

This is somewhat unsettling, but it feels like part of the issue is that the the process is not continuous. Namely, if we imagine the three players moving towards each other, they go from having territory $$(\frac{1}{2} - \epsilon, 2 \epsilon, \frac{1}{2} + \epsilon)$$ to $$(\frac{1}{3}, \frac{1}{3}, \frac{1}{3})$$. This is not an issue in two dimensions, so we can hope that the problem is fixed here.

Suppose that there are $$k$$ players on $$[0,1]$$. We can immediately notice that the solution where all players locate at $$\frac{1}{2}$$ is not an equilibria. Any player can just move slightly down to get half of the customers as opposed to $$\frac{1}{k}$$ of it. We can also check that the socially optimal solution where the $$i$$th player locates at $$\frac{1}{2k} + \frac{1}{k}$$ is also not an equilibrium, since the player at $$\frac{1}{2k} + \frac{1}{k}$$ should move to $$\frac{1}{2k} + \frac{2}{k} - \varepsilon$$.

## Playing on $$[0,1]^2$$



## The Fear of Competition

## A Cost to Move




## References
[1] Alexander Barvinok. A Course in Convexity. Graduate Studies in Mathematics.

[2] Gergely Ambrus. Linear Programming Duality for Geometers. Arxiv.

[3] Stephen Boyd and Lieven Vandenberghe. Convex Optimization. Cambridge University Press.
