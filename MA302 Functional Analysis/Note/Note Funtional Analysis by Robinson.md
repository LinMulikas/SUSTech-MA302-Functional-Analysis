# Functional Analysis Robinson

- [Functional Analysis Robinson](#functional-analysis-robinson)
- [Ch1.](#ch1)
- [Ch2. Metric Spaces](#ch2-metric-spaces)
  - [2.1 Metric Spaces](#21-metric-spaces)
    - [Metric](#metric)
      - [Product Metric](#product-metric)
    - [Metric Space](#metric-space)
  - [2.2 Open and Close](#22-open-and-close)
    - [Open Ball](#open-ball)
    - [Open Set](#open-set)
    - [Closed set](#closed-set)
    - [Converge, Convergent](#converge-convergent)
  - [2.3 Continuity, Sequential Continuity](#23-continuity-sequential-continuity)
    - [Continuity](#continuity)
    - [Sequential Continuity](#sequential-continuity)
    - [Topological view of Continous](#topological-view-of-continous)
  - [2.4 Interior, Closure, Density and Separatablility](#24-interior-closure-density-and-separatablility)
    - [Interior](#interior)
    - [Closure](#closure)
    - [Dense](#dense)
    - [Separable](#separable)
  - [2.5 Compactness](#25-compactness)
    - [Compact](#compact)
    - [Sequential Compact](#sequential-compact)
- [Ch3. Norms and Normed Spaces](#ch3-norms-and-normed-spaces)
  - [3.1 Norms](#31-norms)
    - [Norm](#norm)
    - [Ball](#ball)
    - [Convex](#convex)
    - [Induced norm with Ball](#induced-norm-with-ball)
  - [3.2 Examples](#32-examples)
    - [$p(x) = x^p$ is convex and convex combination closed in ball.](#px--xp-is-convex-and-convex-combination-closed-in-ball)
    - [$lp$ norm.](#lp-norm)


LinMulikas 2022.02-2022.

# Ch1.

# Ch2. Metric Spaces

## 2.1 Metric Spaces

### Metric

Considering a set $X$, a [metric](#metric) of $X$ is a map: $X \times X \to \mathbb R$, and has the following properties for all $x, y \in X$

- Positive definite.
  $d(x, y) \ge 0$ and $d(x, y) = 0 \iff x = y$.
- Symmetric.
  $d(x, y) = d(y, x)$
- Traingle Inequality.
  $d(x, y) \le d(x, z) + d(z, y)$

> - Induced by inequality.
> 
>   Note that, for a increasing convex function defined on $\mathbb{R^+}$, we have
>   
>   $$a + b \ge c \implies f(a + b) \ge f(c) \implies f(a) + f(b) \ge f(c)$$
>   
>   which usually used to induce a new metric using an exist metric.
> 

#### Product Metric
Metric in product space can be induced by [product metric](). 

Consider $X_1, X_2, \ldots, X_n$ are all metric spaces, then the product metric can be defined as

$$d_p(x, y) := \begin{cases}
  \{\sum_{i = 1}^n d_i(x_i, y_i)^p\}^{1/p} & p < \infty\\
  \max_{i} d_i(x_i, y_i) & p = \infty\\
\end{cases}$$

One can prove that the product metric is also a metric in the product space.(Exercise 2.2)


### Metric Space

The pair $(X, d)$ is called a [metric space](#metric-space). 

> - $L^p$ norm in $X^N$.
>   Considering a series of metric by $d_p$, where $p \in \bar R$, define
>
>   $$
>   d_p(x_i, y_i) = 
>   \begin{cases}
>       |\sum_{i = 1}^N |x_i - y_i|^p|^{1/p} & 1 \le p < \infty\\
>       \max_{i = 1, 2, \dots, N}|x_i - y_i| & p = \infty\\
>   \end{cases}
>   $$
>
>   And here we claim that the $d_p$ is a metric. One can prove the traingle inequality according to _Holder Inequality_.
> - `<a id ="discrete_metric">`Discrete Metric`</a>`.
>
>   Considering a metric defined on a set by
>
>   $$
>   d(x, y) = \begin{cases}1 & x=y\\0 & x \not ={y}\end{cases}
>   $$

## 2.2 Open and Close

### Open Ball

### Open Set

In a [Metric Space](#metric-spcae), a point $x$ in set $A$ is open if there exist an [Open Ball](#open-ball) with positive radius $B(x, r)$ such that $B(x, r) \subseteq A$.

### Closed set

A set is closed if its _complement_ set is open.

> **$\sigma$-algebra**
> $\sigma$-algebra is an algebra such that set operations satisfied, and also the countable union, intersection.

### Converge, Convergent

A sequence $\{x_n\}$ converges to $x \in X$, where $(X, d)$ is a [Metric Space], if $d(x_n, x) \to 0$ as $n \to \infty$. The sequence is said to be [Convergent](#converge).

> - Open set in the topology's view.
>   A sequence $\{x_n\}$ is [converges](#converge-convergent) to $x$ i.f.f every open set $U$ or open ball $B(x, r)$ of $x$ contains the tail infinity terms. (i.e. $\forall\ U$, $\exist\  N,s.t.\forall\ n \ge N,\ x_n \in U$).
> - Closed.
>   Every opoint $x \in A$ is a [limit point]() of $A$.
>   (i.e. Every [convergent]() sequence [converges]() to a point in $A$.)

## 2.3 Continuity, Sequential Continuity

### Continuity

A map $f: (X, d_X) \to (Y, d_Y)$ is [continuous]() at $x$, 
  i.f.f $\forall\ \varepsilon > 0, \exist\ \delta > 0$ such that

$$
d_X(x_1, x_2) < \delta \implies d_Y(f(x_1), f(x_2)) < \varepsilon
$$

### Sequential Continuity

A map $f: (X, d_X) \to (Y, d_Y)$ is [continuous]() at $x$, 
i.f.f $\forall $ sequence $\{x_n\} \to x$, we have $\{f(x_n)\} \to x$, which is also named by [Sequential Continuity]().

### Topological view of Continous

A function $f: X \to Y$ is [continuous]() on $X$,
i.f.f the preimage $f^{-1}(O)$ of any open set $O \subset Y$ is also an open set.

> The condition open can be replaced by closed.

## 2.4 Interior, Closure, Density and Separatablility

### Interior

If $A \subseteq (X, d)$, the interior of $A$ is defined as the union of all the open subsets of $A$. Note the interior of $A$ by $A^\circ$

> - A point $x \in A^\circ$, 
>   i.f.f $\exists \varepsilon > 0, B(x, \varepsilon) \subseteq A$. 
> 

### Closure

If $A \subseteq (X, d)$, then the closure of A, writtern $\bar A$, defined as the intersection of all closed set in $X$ that contain A.

> - The closure $\bar A$ is the smallest closed set contain $A$.
> - The closure $\bar A$ is closed.
> - A point $x \in \bar A$,
>   i.f.f $\forall \varepsilon > 0,\ B(x, \varepsilon) \cap A \ne \emptyset$.

### Dense

A set $A$ is [dense](#dense) in [metric space](#21-metric-spaces) $(X, d)$, if $\bar A = X$.

### Separable

A metric space $(X, d)$ is separable, if it contains a countable [dense](#dense) subset.

> - If $(X, d)$ is separable, then the induced metric space $(Y, b)$ in a subset $Y$ is also separable.
>
> 

## 2.5 Compactness

### Compact

A subset $K$ of metric space $(X, d)$ is compact, if for every open cover of $K$, there exist a finite subcover.

> - Metric space $(X, d)$ is compact if $X$ satisfies the property.
> - If a metric space is not compact, it may also has compact subset.

(i.e.)

Considerint $\{\mathcal{O_i}\}$ is an open cover, (i.e.) every $\mathcal{O_i}$ is a open set and $K \subseteq \bigcup_i \mathcal{O_i}$, there exist a finite subcover $\{\mathcal{O_{i_j}}\}$ such that

$$K \subseteq \bigcup_{j = 1}^N \mathcal{O_{i_j}}$$

> What should be noticed is that the finite subcovet is in the countable union form, which is quite different with the index union.
### Sequential Compact

A subset $K$ of metric space is [sequential compact](#sequential-compact) if every [convergent sequence](#converge-convergent) has a subseqeunce converges and the same point lies in $K$.

**Connection with topology**

> - In [Euclidean Space](), closed set $\implies$ compact.
> - In [metric space](#metric-space), compact subset $\implies$ bounded and closed subset.
> - In [compact metric space](#compact), a subset is compact $\iff$ it's closed.
> - Use the [Product Metric](#metric), the [direct product]() of [compact]() [metric spaces]() is also [compact]().
> - In $\mathbb K^n$, [compact]() $\iff$ closed and bounded.

**Connection with continuity**

> - Continuous function maps compact set to compact set.
> - Continuous function $f:K \to \mathbb R$ maps compact subset of $\mathbb R$ to a [bounded](), both upper and lower bounded, interval.
> - Continuous function defined on a compact set $X$ is also [uniformly continuous]().
>   It can be proved by disolve $X$ into $\delta$-balls. 


# Ch3. Norms and Normed Spaces

## 3.1 Norms

### Norm

On a [Vector Space]() X, a norm $\| \cdot \|$ is a map: $X \to [0, \infty)$, such that

- $\|x\| = 0 \iff x = 0$.
- $\|\lambda x\| = |\lambda|\|x\|$.
- $\|x + y\| \le \|x\| + \|y\|$.


### Ball

A ball $B_X(a, r)$ in a [Vector Space]() is a subset, 

$$B_X(a, r) := \{x \in X: \|x - a\| < r\}$$

Use the symbol $\mathbb{B}$ represente $\bar B(0, 1)$

### Convex

A subset $K$ of a [Vector Space]() is convex, if

$$\forall x, y \in K,\ \forall \lambda \in [0, 1],\ \lambda x + (1 - \lambda)y \in K$$

> It's clearly that Ball is convex.


### Induced norm with Ball

In a vector space, if $N: X \to \mathbb R^+$ satisfies

- Positive Definite.
  $N(x) = 0 \iff x = 0$.

- Linearity.
  $N(kx) = |k|N(x)$.

- Upper bound of Convex Inequality.

  Considering the inverse of Unit Ball,
  
  $$\mathbb B^{-1} := \{x : N(x) \le 1\}$$
  
  then the $\mathbb B^{-1}$ is convex.
  
  Which is also equal to
  $$N(k x + (1 - k) y) \in \mathbb B, \forall x, y \in \mathbb B, k \in [0, 1]$$

  This property provides the upper bound of the convex summary, which usually can be combined with the convex itself to prove 

Then, $N$ induces a norm.

> Proof.
> We need to check the triangle inequality, which can be induced from linearity and convexity in ball.
> 
> - Lemma.
>   1. $x/N(x) \in \mathbb B$.
>       Here, considering
>       $$N(x/N(x)) = \frac{N(x)}{N(x)} = 1 \le 1$$
>
>   2. $\frac{x + y}{N(x) + N(y)} \in \mathbb B$
>       
>       Considering
>       $$\frac{x + y}{N(x) + N(y)} = \frac{N(x)}{N(x) + N(y)}\frac{x}{N(x)} + \frac{N(y)}{N(x) + N(y)}\frac{y}{N(y)} \le 1$$
>
>       Which satisfies the convex inequality.
> 
> Now, we prove it. 
> 
> Considering the case that $N(x) = 0$, it's trivial. $N(y) = 0$ is also trivial.
>
> Otherwise, we consider
> 
>   $$\forall x, y \in X, N(x + y) \le N(x) + N(y) \iff \frac{N(x + y)}{N(x) + N(y)} \le 1$$
> 
> Which is equivalent to prove
> 
>   $$\frac{x + y}{N(x) + N(y)} \in \mathbb B$$
> 
> Wichi is clearly with the Lemma 2.

## 3.2 Examples

Here, we start from $|\cdot|$ is a norm, and the convex of $p(x) = x^p,\ p \ge 1, p \in \mathbb N$.

### $p(x) = x^p$ is convex and convex combination closed in ball.

For every $p \ge 1, k \in [0, 1]$, we have the $p(x)$ is convex, which means

$$p(kx + (1 - k)y) \le kp(x) + (1-k)p(y)$$

> - p = 1.
> 
>   It's clearly.
> 
> - p > 1.
> 
>   Considering the derivative
> 
>   $$p''(x) = p(p - 1)x^{p - 2} \ge 0$$
>
>   Thus, it's convex, thus convex in Unit Ball.

Secondly, considering the convex combination closed in ball,

which means the convex combination for every $x, y,\ s.t.\ p(x), p(y) \le 1$

$$\begin{align*}p(k x + (1 - k)y) &= k^p p(x) + (1 - k)^p p(y) \\ &\le k p(x) + (1 - k)p(y) \\&\le k + 1 - k = 1\end{align*}$$

Thus $p(k x + (1 - k) y) \le 1$.

One can also check that the summary version in vector is also upper convex.

### $lp$ norm.

Claim that, the $lp$ in Euclidean Space, defined by

$$\|x\|_{lp} = (\sum_{i = 1}^n |x_i|^p)^{1/p}$$

is a norm.

One can notice that $\|x\|_{lp}^p = \sum_{i = 1}^n |x_i|^p = \sum_{i = 1}^n p(x_i)$


> Proof.
> 
> Use the lemma, one can find that we need just clarify the convex in ball.
>
> Considering
>
> $$\begin{align*}\|kx + (1 - k)y\| &\le 1 \iff \|kx + (1 - k)y\|^p \le 1\\\end{align*}$$
> 
> And
> 
> $$\begin{align*}\|kx + (1 - k)y\|^p &= \sum_{i = 1}^n p(kx_i + (1 - k) y_i)\\ &\le k^p\sum_{k = 1}^n p(x_i) + (1 - k)^p \sum_{k = 1}^n p(y_i) \\ & \le k\sum_{i = 1}^n p(x_i) + (1 - k)\sum_{i = 1}^n p(y_i)\\ & = k\|x\|_{lp} + (1 - k)\|y\|_{lp} \end{align*}$$
> 