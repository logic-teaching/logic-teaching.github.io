---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Primitive recursion and general recursion

The aim of this chapter is to describe primitive recursive arithmetic and general partial recursive functions. There are three reasons why we need to learn this material well. First, the proofs of G\"odel's Incompleteness Theorems use primitive recursion heavily: they are the main vehicle of the arithmetization of syntax. Second, the statement of G\"odel's Incompleteness Theorems use the notion of computability, which is extensionally equivalent to the notion of recursion which we describe in this chapter. (In the next chapter, we turn to computability proper). Third, primitive recursion has been thought by Hilbert and Bernays to be a paradigmatic example of contentful arithmetic, and so for understanding the secondary literature on this topic one needs to have some sense of what one can and cannot do with primitive recursion.

Finally, a word by way of bibliography. A standard mid 20th century presentation of the rudiments of recursive function theory, and indeed G\"odel's First Incompleteness Theorem, is Kleene's \emph{Introduction to Metamathematics}.\footnote{\cite{Kleene1952-hv}.} This chapter draws heavily off of Kleene's presentation, and I cite accordingly. The reason for not simply assigning Kleene himself is that these portions of Kleene occur sporadically throughout his 500 page text. Further, while Kleene admirably interleaves the development of G\"odel's First Incompleteness Theorem and the foundations of recursion theory, I think that the prevailing view now is that it is best to foreground the computational notions. Finally, I think that Kleene is sometimes more formal than the introductory spirit of our notes recommends.

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%


##Recalling function notation

We work in this chapter with functions on the natural numbers. Recall that our notation for functions is $f:\mathbb{N}^k\rightarrow \mathbb{N}$, which indicates that $f$ takes an ordered $k$-tuple of inputs $(n_1, \ldots, n_k)$ from the natural numbers and return an output $n=f(n_1, \ldots, n_k)$ from the natural numbers. For instance consider $f(n_1, n_2,n_3)=n_1\cdot n_2+n_3$:

$f(3,2,3)=3\cdot 2+3 = 6+3=9, \hspace{5mm} f(3,3,2)=3\cdot 3+2 =9+2=11$

Functions can be identified with sets of their input-output pairs, and if one wanted to formalise this one would develop some set theory. But another way to think about functions is as operations or rules, and a way to set out this approach is to develop the theory of computation, which we shall do in this chapter.

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

(para:pra:pr)=
## Primitive recursive functions

The idea of primitive recursion is to show how to defined functions by saying how they are defined on zero and how they are defined on a successor by how they are defined on the previous step. Formally, this results in the following definition:


:::{prf:definition} Definition by primitive recursion
:label: defn-prim-rec

Suppose a *base function* $B:\mathbb{N}\rightarrow \mathbb{N}$ and an *iterator function* $I:\mathbb{N}^{3}\rightarrow \mathbb{N}$ are given. Then the function $f:\mathbb{N}^{2}\rightarrow \mathbb{N}$ defined by *primitive recursion* from this base and iterator is the function which satisfies the following, for all $n,m$

$$ f(n,0)& =B(n) \\ f(n,S(m)) & = I(n,m,f(n,m))$$

More generally, for $k\geq 0$, suppose a *base function* $B:\mathbb{N}^k\rightarrow \mathbb{N}$ and an *iterator function* $I:\mathbb{N}^{k+2}\rightarrow \mathbb{N}$ are given. Then the function $f:\mathbb{N}^{k+1}\rightarrow \mathbb{N}$ defined by *primitive recursion* from this base and iterator is the function which satisfies the following, for all $n_1, \ldots, n_k,y$:

$ f(n_1, \ldots, n_k, 0) = B(n_1, \ldots, n_k) \\ f(n_1, \ldots, n_k,S(m)) = I(n_1, \ldots, n_k,m,f(n_1, \ldots, n_k,m))$

(In the case where $k=0$, the base is just given by a single natural number $b$ rather than a function $B$).

:::

For the primitive recursive definition of addition, the base is the identity function $B(n)=n$ and the iterator is the successor function $I(n,m,\ell)=S(\ell)$, as one can see by writing it out as follows:

$n+0 = B(n)=n, \hspace{10mm} n+S(m) = I(n,m,n+m) = S(n+m)$

Likewise, for the primitive recursive definition of multiplication, the base is the constant function zero $B(n)=0$ and the iterator function is $I(n,m,\ell)=\ell+n$, as one can see from the following:

$n\cdot 0 = B(0) = 0, \hspace{10mm} n\cdot S(m) = I(n,m,n\cdot m) = n\cdot m+n$

Note that to make this work, we had to be allowed to use the identity function, the constant function zero, and we further had to be allowed to use addition in defining multiplication. 

This then suggests the idea of starting with successor and other simple functions and building up larger and larger classes of functions using primitive recursion. Hence we define the following class of functions:

:::{prf:definition} Primitive Recursive Functions
:label: defn-prim-rec-functions

The *primitive recursive functions* on natural numbers are defined as follows:

- The identity function and constant functions and successor function are primitive recursive. Further, the projection functions $f(n_1, \ldots, n_k)=n_i$ are primitive recursive for each $i\leq k$.

- The composition of primitive recursive functions is primitive recursive. That is, the result of putting primitive recursive functions into the inputs of other primitive recursive functions is primitive recursive. E.g. $f(x,y)=g(h(x,y), k(y))$ is primitive recursive if $g,h,k$ are primitive recursive.

- If the base function and the iterator function are primitive recursive, then the function defined from primitive recursion by this base and iterator is also primitive recursive.

- Nothing else is a primitive recursive function.

:::

Hence, in essence, definition by primitive recursion is defined so that one can draw attention to the collection of functions that contain the identity function, constant functions, successor function, projection functions, and which is closed under composition and primitive recursion.


##

```{code-cell} ipython3
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline

# Fixing random state for reproducibility
np.random.seed(19680801)

# Compute pie slices
N = 20
θ = np.linspace(0.0, 2 * np.pi, N, endpoint=False)
radii = 10 * np.random.rand(N)
width = np.pi / 4 * np.random.rand(N)
colors = plt.cm.viridis(radii / 10.)

ax = plt.subplot(111, projection='polar')
ax.bar(θ, radii, width=width, bottom=0.0, color=colors, alpha=0.5)

plt.show()
```

##

```{code-cell} ipython3
:tags: [hide-input]
def A(m, n, s="%s"):
    print (s % ("A(%d,%d)" % (m, n)))
    if m == 0:
        return n + 1
    if n == 0:
        return A(m - 1, 1, s)
    n2 = A(m, n - 1, s % ("A(%d,%%s)" % (m - 1)))
    return A(m - 1, n2, s)

A(2,2)
```