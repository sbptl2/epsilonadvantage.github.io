---
layout: post
---
## Geometric Duality
Linear programming duality has always been a little mysterious. The standard argument looks something like you have some primal linear program

$$
\begin{equation}
\begin{aligned}
\max c \cdot x \\
A x \leq b \\
\end{aligned}
\end{equation}
$$

where $$A \in \mathbb{R}^{m \times n}, b \in \mathbb{R}^m$$, and $$x,c \in \mathbb{R}^n$$. We can then think of the following means of proving a upper bound: take linear combinations of the rows to get a vector that dominates $$c$$ entrywise. This will then clearly give us an upper bound since all the variables are positive. So we get the dual

$$
\begin{equation}
\begin{aligned}
\min y \cdot b \\
y^T A = c^T\\
y \geq 0 \\
\end{aligned}
\end{equation}
$$

It's immediate that the optimum of the dual upper bounds the optimum of the primal. However, it turns out that we should expect the two for them to be equal, which is much less obvious. Unfortunately, the usual proof makes it somewhat unclear what's going on geometrically. It uses teh Farkas Lemma, however, so we should suspect that convex separation is central. To better see what is happening we consider the following slightly more general problem:

$$
\begin{equation}
\begin{aligned}
\max c \cdot x \\
x \in K \\
\end{aligned}
\end{equation}
$$

As such it is clear that we want to understand the separating hyperplanes of the body. Namely, we want to understand the vectors $$y \in \mathbb{R}^n$$ and $$\theta$$ such that
  $$\langle y,x \rangle \leq \theta$$
for all $$x \in K$$. In particular, given a value $$\theta$$ we want to know if it holds that $$\langle c, x \rangle \leq \theta$$ for all $$x \in K$$ (as this would tell us that the value of the primal is at most $$\theta$$.) But for polyhedral bodies it turns out that the separating hyperplanes are precisely those resulting from the conical hull of the rows of the defining matrix.

Namely, we have the following theorem:

**Theorem. (Linear Programming Duality)**  *Let $$K \subseteq \mathbb{R}^n$$ be a closed convex body and $$x \in \mathbb{R}^n \setminus K$$ then there exists a $$y \in \mathbb{R}^n \setminus \{0\}$$ such that $$\langle y,x \rangle < \langle y,z \rangle$$ for all $$z \in K$$.*

We then want to understand a separating hyperplane of this body. As such, we recall the defintion of the polar dual body:

$$K^\circ = \{y \in \mathbb{R}^n : \langle y, x \rangle \leq 1 \} $$

The problem of linear programming is then exactly trying to understanding when $$\lambda c \in \mathbb{K}^\circ$$. Moreover, we can show that if
  $$K = \{x \in \mathbb{R}^n : Ax \geq 0 \} $$
then the polar body will exactly be
  $$\{ \} $$
\ Why should this be the case? Usually this is proved using the separation lemma for convex bodies and Farkas lemma, so there seems to be something geometric happening. So let's try to take a more geometric lens.

## The Polar Dual

We start by recalling a few facts about the polar dual. Recall that given a convex body $$K$$, we can define the polar dual as

$$K^\circ = \{y \in \mathbb{R}^n : \langle y, x \rangle \leq 1\}$$

From a geometric perspective, we interpret $$K^\circ$$ as describing the separating hyperplanes of a body. As such, we will need the following key fact about convex bodies:

**Theorem. (Convex Separation)**   *Let $$K \subseteq \mathbb{R}^n$$ be a closed convex body and $$x \in \mathbb{R}^n \setminus K$$ then there exists a $$y \in \mathbb{R}^n \setminus \{0\}$$ such that $$\langle y,x \rangle < \langle y,z \rangle$$ for all $$z \in K$$.*

<!-- *Proof.* Consider the closest point $$p \in K$$ to $$x$$. We then claim that for all $$z \in K$$ we have that
$$\langle x - p, z - p \rangle \leq 0$$

Indeed, suppose not and let $$\lambda > 0$$. We then have that
$$ \|x - ((1 - \lambda) p + \lambda z)\|^2 = \|x - p\|^2 + \lambda^2 \| p - z\|^2 - 2 \lambda \langle x - p, z - p \rangle $$

which would be strictly less than $$\|x - p\|^2$$ be large for $$\lambda$$ sufficiently small. Since $$K$$ is a closed convex body, it follows that $$x \pm \epsilon p \not \in K$$ for $$\epsilon$$ sufficiently small. Observe now that for $$z \in K$$
$$\| x \pm \epsilon p - z\| = \| x \pm \epsilon p - z\| \geq \|x - z\| - \epsilon \| p \| \geq \|x - p\| - \epsilon \| p \| = \|x \pm \epsilon p - p\| $$

\|x - p + \lambda (p - z) \|^2 \|x\|^2 + \|(1 - \lambda) p + \lambda z \|^2 - 2 \lambda (1 - \lambda) \langle p, z \rangle  $$
$$\square$$ -->

We won't prove the result here and refer the reader to a proof in Boyd and Vandenberghe's text. Indeed, with some more work we can generalize this to other topological spaces. Namely,

**Theorem (Convex Separation in Topological Vector Spaces)** *Let $$V$$ be a topological vector spaces and $$A,B \subseteq V$$ be convex sets. Suppose that $$A \cap B = \emptyset$$ and that the interior of $$A$$ is non-empty. Then there exists a continuous, non-identically zero linear functional $$f$$ such that $$f(x) \leq f(y)$$ for all $$x \in A$$ and $$y \in B$$.*

We again won't prove this statement and refer the interested reader to the text of Barvinok. With this, we now have the following simple lemma:

**Lemma** *Let $$K \subseteq \mathbb{R}^n$$ be a closed, convex set containing the origin then $$(K^\circ)^\circ = K$$.*

*Proof.* We first note that by definition $$K \subseteq (K^\circ)^\circ$$. Conversely, suppose that $$x \not \in K$$. By the separation theorem, it follows that there exists a hyperplane $$y$$ such that $$\langle y, x \rangle > 1$$. But then it follows that $$x \not \in (K^\circ)^\circ$$, as desired. $$\square$$

Indeed, we more generally have that

**Lemma** *Let $$K \subseteq \mathbb{R}^n$$ be a closed, convex set containing the origin then $$(K^\circ)^\circ = \overline{conv(0,K)}$$.*

*Proof.* Note that $$K^\circ = \overline{conv(K,0)}^\circ$$. The result then follows from the previous lemma.

Polar duals also interact well with intersections. Namely,

**Lemma** *For closed, convex bodies, $$K_1, K_2 \subseteq \mathbb{R}^n$$ we have that $$(K_1 \cap K_2)^\circ = \overline{(conv(K_1^\circ \cup K_2^\circ)}$$.*

Note that while the closure is a little annoying, it is necessary in general.

*Proof.* We'll instead prove that $$K_1 \cap K_2 = \overline{(conv(K_1^\circ \cup K_2^\circ)}^\circ = conv(K_1^\circ \cup K_2^\circ)^\circ$$. Indeed, it is immediate that $$K_1 \cap K_2 \subseteq conv(K_1^\circ \cup K_2^\circ)^\circ$$. Conversely, we note that $$K_1^\circ \subseteq conv(K_1^\circ \cup K_2^\circ)$$ and thus $$K_1 = (K_1^\circ)^\circ \supseteq conv(K_1^\circ \cup K_2^\circ)^\circ$$. Similarly, $$K_2 \supseteq conv(K_1^\circ \cup K_2^\circ)^\circ$$.

## Linear Programming Duality
With these tools, we now move towards, convexity. We begin by considering a more general form of linear programming. Namely, given a convex body $$K$$ containing the origin and a vector $$v$$ we wish to understand the support function

$$h_K(v) = \sup_{x \in K} \langle v, x \rangle.$$

Since this a question about supporting hyperplanes, it seems natural to change this into a question about the polar dual. Namely, we define the radial function as

$$\rho_{K}(v) = \sup \{\lambda: \lambda v \in K\}.$$


We then have that

**Lemma** *For any body $$K \subseteq \mathbb{R}^n$$ containing the origin, we have that $$\rho_{K^\circ}(v) \cdot h_K(v) = 1$$ for all $$v \in \mathbb{R}^n$$, where we take the convention that $$\frac{1}{\infty} = 0$$ and $$\frac{1}{0} = \infty$$*

*Proof.* First observe that $$\frac{1}{h_K(v)} v \in K^\circ$$, so it follows that $$\rho_{K^\circ}(v) \geq \frac{1}{h_K(v)}$$. Applying this to the polar dual, we get that $$\rho_{K}(v) \geq \frac{1}{h_{K^\circ}(v)}$$. On the other hand, we note that if there exists an $$x \in K$$ such that $$v \cdot x \geq \lambda$$ then $$\rho_{K^\circ}(v) \leq \frac{1}{\lambda}$$. Taking the limit then gives us that $$\rho_{K^\circ}(v) \leq \frac{1}{h_K(v)}$$ as desired.
$$\square$$

We can now take the polar dual (using the properties we derived earlier) of the corresponding convex body for linear programs to get

<!-- So, how can we prove that $$h_K(v) \leq \lambda$$? We simply show that $$\lambda^{-1} v \not \in K^\circ$$. Moving back to our original setting, we have that $$K = \{x \in \mathbb{R}^n : Ax \leq b \}$$ where $$A \in \mathbb{R}^{m \times n}$$ and $$b \in \mathbb{R}^m$$. -->

**Lemma** *Let $$K = \{x \in \mathbb{R}^n : Ax \leq b \}$$ for a matrix $$A \in \mathbb{R}^{m \times n}$$ and vector $$b \in \mathbb{R}^m$$ with $$b \geq 0$$, then $$K^\circ$$ is given by $$\sum_i \frac{\mu_i}{b_i} a_i^T$$ where $$a_i^T$$ are the rows of $$A$$, $$\mu_i \geq 0$$, and $$\sum_i \mu_i \leq 1$$.*

<!-- *Proof.* Let $$L = conv(0, \frac{1}{b_i} a_i^T)$$. We'll show that $$L^\circ = K$$, which will then imply that $$K^\circ = L$$. We first note that indeed for all $$x \in K$$ we have that

 $$\sum_i \frac{\mu_i}{b} a_i^T x \leq 1.$$

 So $$K \subseteq L^\circ$$. On the other hand, suppose that $$x \not \in K$$. It then follows that for some $$i$$ we have that $$a_i^T x > b_i$$. But then we have that $$\frac{1}{b_i} a_i^T y > 1$$, so $$y \not \in L^\circ$$.
 $$\square$$ -->

 So moving from the support function to the radial function, we want to minimize $$\lambda^{-1}$$ such that there exists $$\mu_i$$'s with $$\sum_i \frac{\mu_i}{b_i} a_i^T = \lambda c$$. Massing this, we can alternatively write this as minimizing $$\langle b,y \rangle$$ such that $$y^TA = c^T$$ and $$y \geq 0$$, as desired. Note that while we assumed that $$0 \in K$$, we can get around this by simply shifting our convex set $$K$$, as it is non-empty.

We can also consider a slightly more general form of linear programming. Namely,

 $$
 \begin{equation}
 \begin{aligned}
 \min \langle c, x \rangle \\
 A x \leq b \\
 x \in K \\
 \end{aligned}
 \end{equation}
 $$

for some convex body $$K$$. We again assume that $$0$$ is a feasible solution and that $$conv(K \cup \{\frac{1}{b_i} a_i^T \} )$$ is closed. In this case, we want to minimize $$\lambda^{-1}$$ subject to $$\sum_{i} \frac{\mu_i}{b_i} a_i^T + \psi v = \lambda c$$ for some $$v \in K^\circ$$. Again after massaging, we can write this as

$$
\begin{equation}
\begin{aligned}
\min \langle b, y \rangle + z \\
y^TA + z v = c^T \\
v \in K^\circ \\
y,z \geq 0
\end{aligned}
\end{equation}
$$

If $$K$$ is symmetric, then this takes on an even cleaner form

$$
\begin{equation}
\begin{aligned}
\min \langle b, y \rangle + \| y^TA - c^T \|_{K^\circ} \\
y \geq 0
\end{aligned}
\end{equation}
$$

## References
[1] Alexander Barvinok. A Course in Convexity. Graduate Studies in Mathematics.

[2] Gergely Ambrus. Linear Programming Duality for Geometers. Arxiv.

[3] Stephen Boyd and Lieven Vandenberghe. Convex Optimization. Cambridge University Press.
