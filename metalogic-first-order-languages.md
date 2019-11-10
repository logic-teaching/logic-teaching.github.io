 <script>
  MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
  </script>
  <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js"></script>



This chapter is one of the building blocks of this course. In this
chapter we formally define a first-order language, which systemizes the
formal languages which we were translating into in the previous chapter.

# Definition of language {#para:languages:defnlanguage}

The first key definition is that of language. Perhaps "language" is not the best word: as the formal
definition below makes clear, it is really more like a "fragment of a
lexicon." Some people use the more neutral "signature" in lieu of
"language":

[\[defn:symbols\]]{#defn:symbols label="defn:symbols"} All **languages**
we consider will have the following symbols:

**variables** $v_1,\,v_2,\,v_3,\ldots$

**propositional connectives**
$\wedge, \vee, \neg, \rightarrow, \leftrightarrow$

**parentheses** $($ and $)$

**identity symbol** $=$

**quantifiers** $\forall$ and $\exists$

Further, a **language** might have some of the following symbols:

**constant** symbols

$n$-place **predicate** symbols, for each $n\geq 1$

$n$-place **function** symbols, for each $n\geq 1$

Hence, all languages have (i)-(v) but they can differ in terms of which
of (vi)-(viii) they have. A language is thus distinguished by its
constant, predicate, and relation symbols, and hence we will think of a
first-order language as the set of these. We will see some examples
shortly.

Notational remarks*.
[\[para:first:notation:variables\]]{#para:first:notation:variables
label="para:first:notation:variables"} Before turning to examples, we
make some brief notational remarks:

First, a synonym for "predicate symbol" is "**relation symbol**". A
synonym for "one-place" is "**unary**", a synonym for "two-place" is
"**binary**," and a synonym for "three-place" is "**ternary**." Hence "a
binary relation" means the same thing as "a two-place relation."

Second, we use lower-case Roman letters from the very beginning of the
alphabet, like $a,b,c,d,e$, for constant symbols, as well as,
typewriter-scripted, subscripted, and superscripted versions thereof
like $\mathtt{a,b,c,d,e}$, $a_i, b_i, c_i, d_i, e_i$,
$a^{\prime}, b^{\prime}, c^{\prime}, d^{\prime}, e^{\prime}$.

Third, we use lower-case Roman letters from the very end of the
alphabet, like $x,y,z,u,v,w$ for variables, as well as subscripted, and
superscripted versions thereof. That is, even though our list of
variables is technically just $v_1, v_2, v_3, \ldots$, it becomes very
cumbersome to actually write out the subscripts on the $v$'s, and so we
just use the more intuitive notation $x,y,z,u,v,w$ for variables.

Fourth, we use lower-case Roman letters $f,g,h,k$ for function symbols,
as well as typewriter-scripted, subscripted, and superscripted versions
thereof.

Fifth, we use upper-case Roman letters $Q,R,S,T$ for relation symbols,
as well as as typewriter-scripted, subscripted, and superscripted
versions thereof.

Finally, we use letters like
$\mathcal{L}, \mathcal{L}_i, \mathcal{L}^{\prime}$ for languages. The
letter '$L$' reminds us of "language". The cursive is conventional and
helps distinguish from circumstances where one might like to use $L$ for
a relation symbol.

N[(mov)](https://drive.google.com/open?id=1q0vL9j2IBlEEmVVkemQ1_E4_3G6LFxAI)
*Four examples*.
[\[para:languages:fourexamples\]]{#para:languages:fourexamples
label="para:languages:fourexamples"}

The **language of trust** consisting of three constants $a,b,c$ and one
two-place relation $T$. It is well-suited to describethe trust examples
from
§[\[para:translating:trustex\]](#para:translating:trustex){reference-type="ref"
reference="para:translating:trustex"}. For instance, in addition to
$\forall \; x \; \exists \; y \; Txy$ and
$\exists \; y \; \forall \; x \; Txy$, one can write sentences such as
$Tab$ and $\forall \; x \; Txa$ in this language.

The above example make clear that a function symbol or a relation symbol
has its "number of places" written into it from the very beginning. That
is, part of what one specifies when one specifies a language as above is
whether a predicate symbol is one-place or two-place or three-place etc.
Often the symbols have some prior meaning to us and it probably is clear
in advance what the places of these symbols are.

The **language of identity** consisting of no constant, relation, or
function symbols. It is called the language of *identity* because the
only formulas in this language will concern identity statements. Similar
to the example in
§[\[para:translating:identity\]](#para:translating:identity){reference-type="ref"
reference="para:translating:identity"}, one can write the following in
this language, expressive of their being at least two things:
$\exists \; x \; \exists \; y \; x\neq y$.

The **language of ordering** consisting of one two-place relation
symbol $\leq$. This symbol is chosen because, in its intended
applications, it will be interpreted as usual less-than-or-equal-to of
numbers, and thus it is two-place because one is comparing the size of
two numbers. As such, instead of $\boldleq xy$ we write $x\boldleq y$.
Since all our languages include identity, one can write sentences such
as
$$\forall \; x \; \forall \; y \; ((x\boldleq y \wedge y\boldleq x)\rightarrow x=y)$$
which expresses that two numbers are identical if each is
less-than-or-equal to the other.

The **language of arithmetic** contains the language of ordering, and
adds a constant symbol $\boldzero$, a one-place function symbol $\boldS$
for successor which intuitively stands for the function "add one", a
two-place function symbol $\boldplus$ for addition, and a two-place
function symbol $\boldtimes$ for multiplication. One can write things
such as the following in this language:
$$\forall \; x \; x\boldtimes \boldS(\boldzero) = x$$ We cannot quite
write the arithmetical examples from
§[\[para:translating:func\]](#para:translating:func){reference-type="ref"
reference="para:translating:func"} since we don't have primitive names
for numbers besides zero. But we can write related things such as:
$$\boldS(\boldS(\boldS(\boldzero))) = \boldS(\boldS(\boldzero)\boldplus \boldS(\boldzero))$$
which is just an awkward way of saying that three (the third successor
of zero) is equal to the successor of "one plus one."

The reason why symbols such as $\boldzero$ are in typewriter-script is
to distinguish the number $0$ from the symbol $\boldzero$ (you might
even have to squint to see the difference in the fonts). The number $0$
is what the number-theorist studies, and according to the philosophers
of mathematics it is an abstract object which is not spatiotemporal. The
symbol $\boldzero$ is a symbol of a formal language, and could be
identified with a concrete object, like a specific token of the written
symbol. This distinction is perhaps more obvious in the case of other
constant symbols. For instance, if one wanted a language to describe
people, then it might be natural for the constant symbols to be thought
of like names. But obviously the name "Bill," which consists of four
letters, should be distinguished from the flesh-and-blood person Bill.
The name "Bill" is like the symbol $\boldzero$, and the flesh-and-blood
person Bill is like the object $0$, the least natural number.

N[(mov)](https://drive.google.com/open?id=16ip_yno6AsyyJozKPvAdtDvea6nDZgg3)
*The definition of term, and examples*.
[\[para:languages:term\]]{#para:languages:term
label="para:languages:term"} Terms are what you get by taking the
variables and constants and closing under the function symbols.

[\[defn:term\]]{#defn:term label="defn:term"} Let $\mathcal{L}$ be a
language. Then the **terms** of the language $\mathcal{L}$ are defined
as follows:

Each variable or constant is a term.

If $n\geq 1$, if $f$ is an $n$-place function symbol, and if
$t_1,\ldots,t_n$ are terms, then $f(t_1,\ldots,t_n)$ is a term.

Finally, a **closed term** is a term with no variables.

To illustrate, let us identify the terms in each of the four example
languages from the previous paragraph:

In the language of trusts, the only terms are the three constants
$a,b,c$ and the variables. This is because this language does not have
any function symbols and so clause (ii) is never activated. The
constants are closed terms and the variables are not closed terms.

In the language of identity and the language of ordering, the only terms
are the variables. This is because these languages have no constant
symbols and no function symbols. Hence there are no closed terms in this
language.

In the language of arithmetic, there are lots of terms, such as the
following:
$$\boldzero, \hspace{5mm} x, \hspace{5mm} \boldS(\boldzero), \hspace{5mm} \boldS(x), \hspace{5mm} \boldS(\boldS(\boldzero)), \hspace{5mm} \boldS(\boldS(x))$$
$$\boldzero\boldplus x, \hspace{5mm} \boldS(\boldzero)\boldplus \boldS(x), \hspace{5mm} \boldS(\boldS(\boldzero))\boldplus \bold(\boldS(x))$$
Some of these terms have special names. In particular, we recursively
define, for $n\geq 0$, the terms
$$\boldS^0(x)=x, \hspace{5mm} \boldS^{n+1}(x) = \boldS(\boldS^n(x))$$
That is, the idea is that $\boldS^3(x)=\boldS(\boldS(\boldS(x)))$, the
third successor of $x$. Further, the terms $\boldS^n(\boldzero)$ for
$n\geq 0$ are called the **numerals**. The idea is that the numerals are
just the terms that one gets by iterating the successor operation
starting at zero. Hence, in the language of arithmetic, the numerals are
just names for the numbers. The numerals are closed terms, and so too
are applications of the addition and multiplication symbols to these.

The definition of formula*.
[\[para:first:formula\]]{#para:first:formula label="para:first:formula"}
We now define formula:

[\[defn:formula\]]{#defn:formula label="defn:formula"} Let $\mathcal{L}$
be a language. Then the **formulas** of the language $\mathcal{L}$ are
defined as follows:

[\[defofformula\]]{#defofformula label="defofformula"}

If $t_1$ and $t_2$ are terms, then $t_1=t_2$ is a formula.

If $n\geq 1$, and if $P$ is an $n$-place predicate symbol, and if
$t_1,\ldots,t_n$ are terms, then $P(t_1,\ldots, t_n)$ is a formula.

If $\varphi, \psi$ are formulas, then $\neg \varphi$ and
$(\varphi \wedge \psi)$ and $(\varphi \vee \psi)$ and
$(\varphi\rightarrow \psi)$ and $(\varphi\leftrightarrow \psi)$ are
formulas.

If $\varphi$ is a formula and $x$ is a variable, then
$\forall \; x \; \varphi$ and $\exists \; x \; \varphi$ are formulas.

Formulas given by (i) or (ii) are called **atomic** formulas. Another
way to state the definition of "formula" is to say that the collection
of all formulas is gotten by starting with the atomic formulas and
closing under the propositional connectives and the quantifiers.

Notational remarks*.[\[para:first:notation\]]{#para:first:notation
label="para:first:notation"} Before we look at more examples and
non-examples of formulas, we make some brief notational remarks.

First, we use lower-case Greek letters for arbitrary formulas. Usually
we use the letters $\varphi$ (phi), $\psi$ (psi), $\theta$ (theta),
$\chi$ (chi), $\xi$ (xi) for these, as well as subscripted and
superscripted versions thereof. It is traditional to use these letters,
and anyways as far as languages go we have already reserved Roman
letters for constant symbols, function symbols, and relation symbols. If
one is not familiar with these five lower-case Greek letters, one should
get familiar with them immediately and practice reading and writing
them.

Second, we often omit parentheses when convenient. We always allow
ourselves to drop outermost parentheses and write e.g.
$\varphi \wedge \psi$ instead of $(\varphi \wedge \psi)$. Further,
instead of writing $\varphi \wedge (\psi \wedge \theta)$ or
$(\varphi \wedge \psi) \wedge \theta$, we just drop parentheses and
write $\varphi \wedge \psi \wedge \theta$ since these are equivalent in
any reasonable proof system and any reasonable semantics. Likewise,
$\forall \; x \; x=c\rightarrow \theta$ is technically ambiguous between
its intended reading $\forall \;x \; (x=c\rightarrow \theta)$ and the
unintended reading $(\forall \;x  \; x=c)\rightarrow \theta$. But since
context usually makes clear which is intended (e.g. context would make
clear that it is unreasonable to assert that everything is equal to
$c$), we simply write $\forall \; x \; x=c\rightarrow \theta$. Finally,
in relation and function symbols, we allow ourselves to drop parentheses
too when convenient. For instance, we may write $Rxy$ instead of
$R(x,y)$ (we did this in our translations in
Chapter [\[chap:translating\]](#chap:translating){reference-type="ref"
reference="chap:translating"}); and likewise we may write $fx=y$ instead
of $f(x)=y$ (sometimes we do this with the successor operation in the
language of arithmetic). But including parentheses can be useful when
there are complicated terms such as $R(f(x), f(y))$ and
$g(f(a,b),h(c))$.

Third, we assume that negation binds tightly. That is,
$\neg \varphi \wedge \psi$ is intended to be
$(\neg \varphi) \wedge \psi$ rather than $\neg (\varphi \wedge \psi)$.

Fourth, we abbreviate $\neg (x=y)$ as $x\neq y$.

N[(mov)](https://drive.google.com/open?id=1Dyn5ITKCyGp45C8D2_PSIkZScTEb-oMB)
*Examples and non-examples of formulas*. We have already seen a bunch of
examples of formulas relative to our four example languages in
§[\[para:languages:fourexamples\]](#para:languages:fourexamples){reference-type="ref"
reference="para:languages:fourexamples"}. But let us look at some more,
and include some non-examples.

In the language of trusts, $\forall \; y \; \exists \; x \; Txy$ is a
formula, as is $\exists \; x \; Txy$. Indeed, the first was formed from
the second by adding on a universal quantifier. There is another
difference between these two formulas: the first is intuitively true or
false in a situation-- it might be the translation of "everyone is
trusted by someone." However, the second is not similarly evaluable for
truth or falsity, since no information is given by who or what $y$ is.
Now, for a *non*-example of a formula, consider $T x$. This is not a
formula in this language since we declared that $T$ was a binary
relation and hence has to take two things coming after it.

In the language of identity, we have formulas like
$\forall \; x \; \exists \; y \; x=y$ and
$\exists \; v \; \forall \; w \; v=w$. The first is intuitively true
since everything is identical to itself, but the second is presumably
not true in most situations since in most situations there is more than
one thing. For something which is *not* a formula in this language,
consider $\exists \; x \; x$. This is not a formula since if it were,
then taking the existential quantifier off would still be a formula, but
what one obtains when one removes it is just the variable $x$ (which is
a term, not a formula).

In the language of ordering, we have formulas like $x \boldleq y$ and
$y\boldleq z$, and we can make further formulas out of these, like
$x\boldleq y \wedge y\boldleq z$ and
$\forall \; x \; \forall \; z \; \exists \; y \; x\boldleq y \wedge y\boldleq z$.
For a *non*-example of a formula, consider $\forall \; x \; \boldleq y$.
If this were a formula, then so too $\boldleq y$ would be a formula: but
since the ordering is two-place, one would need to have two terms
involved.

In the language of arithmetic, we have lots of formulas, like
$\forall \; x \; \exists \; y \; x\boldleq y \wedge x\neq y$, which
intuitively says that the numbers have no greatest element (e.g. for
every number $x$ one can find a greater one $y$). One also has formulas
like $\boldS(x)\boldplus y = \boldS(\boldS(\boldzero))$. Using the
numerals from
§[\[para:languages:term\]](#para:languages:term){reference-type="ref"
reference="para:languages:term"}, this formula could also be written as
$\boldS(x)\boldplus y = \boldS^2(\boldzero)$. However, note that
$\boldS(x)\boldplus y = \boldS^z(\boldzero)$ is *not* a formula. For,
while $\boldS^n(0)$ is a term for each natural number $n$, it is not the
case that we can replace the '$n$' with a variable '$z$.' For instance,
for each $n$, the numeral $\boldS^n(0)$ is a term consisting of $3n+1$
many symbols in it: there is one symbol for $\boldzero$ and there are
three symbols-- the successor and two parentheses-- for each further
application of the successor operation. However, if $z$ is one of the
variables from our definition of a language in
§[\[para:languages:defnlanguage\]](#para:languages:defnlanguage){reference-type="ref"
reference="para:languages:defnlanguage"}, then we can cannot put it in
the '$n$' spot in the term $\boldS^n(0)$ to obtain a term $\boldS^z(0)$.

N[(mov)](https://drive.google.com/open?id=17eSZ8OjayP-A7nPXE1M9SaTjEM4Mq_RF)
*Free and bound occurrences*.
[\[para:languages:freebound\]]{#para:languages:freebound
label="para:languages:freebound"} We can capture the difference between
formulas which are eligible for truth or falsity relative to a situation
by the free vs. bound distinction. Informally, we define an occurrence
of a variable $x$ in a formula to be **free** if it is not in the scope
of a quantifier expression $\forall \; x\;$ or $\exists \; x \;$;
otherwise we say it is **bound**.

For example, the first occurrence of $x$ in the following is free, while
the second and third occurrences are bound, where $P$ is a two-place
relation: $$\forall \; y \; (P(x,y)\rightarrow \forall \; x \; P(x,x))$$

The official definition is as follows:

Every occurrence of a variable in an atomic formula is free.

An occurrence of a variable $x$ in $\varphi \wedge \psi$ is free just in
case the corresponding occurrence of $x$ in either $\varphi$ or $\psi$
is free (and similarly for $\neg \varphi$, $\varphi \vee \psi$,
$\varphi\rightarrow \psi$, $\varphi\leftrightarrow \psi$).

An occurrence of a variable $x$ in $\forall \; y \; \varphi$ or
$\exists \; y \; \varphi$ is free just in case it corresponds to a free
occurrence of $x$ in $\varphi$ and $x$ and $y$ are different variables.

Note on this way of talking, the variables which come immediately after
quantifiers are not occurrences. For instance, in $\forall \; x \; x=x$,
the variable $x$ only occurs twice, not three times.

Here are some more examples.

Supposing that $T$ is a three-place relation, then both instances of $y$
and $z$ in the following are free, whereas both occurrences of $x$ are
bound: $$\forall \; x \; (T(x,y,z)\rightarrow T(y,x,z))$$

In the following formula, the occurrences of $u,v$ in the antecedent are
bound, the occurrence of $v$ in the consequent is bound, and the
occurrence of $u$ in the consequent is free:
$$(\forall \; v \; \exists \; u \; u=v) \rightarrow (\forall \; v \; u=v)$$

The free vs. bound distinction helps us define the following important
notion:

A **sentence** is a formula with no free occurrences of variables.

This is important because, again, sentences are eligible for truth or
falsity in a situation, whereas formulas are not.

N[(mov)](https://drive.google.com/open?id=10MkEnZfYvZM6cn6wgQA8kTP1-dbvABdl)
*Free variables and
substitution*.[\[para:first:substitution\]]{#para:first:substitution
label="para:first:substitution"} Since a formula is finite, only
finitely many variables occur freely in it. The set of **free
variables** of a formula is simply the set of variables which have free
occurrences in the formula. To avoid having to persistently say out loud
that a variable occurs freely in a formula, we introduce some notation.
In particular, writing $\varphi(x_1, \ldots, x_k)$ is just another way
of writing $\varphi$, but with the default that $x_1, \ldots, x_k$ occur
freely in $\varphi$. This notation is useful when it comes to
substitution.

If $\varphi(x_1, \ldots, x_k)$ is a formula, and $t_1, \ldots, t_k$ are
terms, then the **substitution** $\varphi(t_1, \ldots, t_k)$ is just the
result of replacing each free occurrence of $x_i$ by $t_i$.

Here are some examples.

Suppose that $\varphi(x)$ is
$(\exists \; y \; x=\boldS(y)) \rightarrow \boldS(x)\neq  \boldzero$.
Then $\varphi(\boldS^2(\boldzero))$ is
$(\exists \; y \; \boldS^2(\boldzero)=\boldS(y)) \rightarrow \boldS(\boldS^2(\boldzero))\neq  \boldzero$,
while $\varphi(\boldzero)$ is
$(\exists \; y \; \boldzero=\boldS(y)) \rightarrow \boldS(\boldzero)\neq  \boldzero$.

Suppose that $\psi(x,y)$ is $\exists \; z \; Txz \wedge Tzy$. Then
$\psi(a,b)$ is $\exists \; z \; Taz \wedge Tzb$, while $\psi(b,a)$ is
$\exists \; z \; Tbz \wedge Tza$.

In these examples, none of the free variables had bound occurrences. But
our definition works in this case too, since we only replace the free
occurrences. For instance, suppose $\theta(x,y)$ is
$x\leq y \wedge \exists \; x \; x\neq \boldS(\boldzero)$. Then
$\theta(\boldzero, \boldzero)$ is
$\boldzero \leq \boldzero \wedge \exists \; x \; x\neq \boldS(\boldzero)$.
That is, we do not take any action on the last occurrence of $x$ since
it is bound.

However, if $t_i$ have free variables, it can happen that these
variables become bound as a result of the substitution. For instance,
consider $\chi(x)$ to be $\forall \; y \; y = x$, where $x$ occurs
freely. If we take the term $y$ and substitute it in for $x$, we get
that $\chi(y)$ is $\forall \; y \; y =y$. Usually when we substitute, we
require that this does not happen, that is we require that the free
variables of the terms which we are substituting in do not become bound
as a result of the substitution. The reason for this is that we want to
assert things like the indiscernibility of identicals with substitution:
$$\forall \; x \; \forall \; y \; (x=y \rightarrow (\chi(y)\rightarrow \chi(x)))$$
However, this becomes false if we allow the type of behavior we just
noticed with our $\chi$. After all, just choose an object like $5$ and
set $x=y=5$. Then we have $\chi(y)$ because this just says that
everything is self-identical (look again at what $\chi(y)$ was up
above-- it does not have anything to do with $5$ because the variable
$y$ was bound in the original formula). But we do not have $\chi(x)$
since this says that everything is equal to $5$. Hence, we solve this
problem simply by requiring that if we substitute, then no free
variables of our terms become bound as a result of the substitution.

\newpage
Exercises {#exercises .unnumbered .unnumbered}
---------

[\[exc:langages:1\]]{#exc:langages:1 label="exc:langages:1"} Consider
the language which has two constant symbols $a,b$, a one-place function
symbol $g$, a two-place function symbol $f$, and a binary relation $R$.
Which of the following four are terms in the language and which are not?
$$g(f(a,b)) \hspace{5mm} f(g(y,a)) \hspace{5mm} f(g(x),g(b)) \hspace{5mm} R(a,g(b))$$

[\[exc:langages:2\]]{#exc:langages:2 label="exc:langages:2"} Consider
the language which has one constant $c$, one one-place function symbol
$h$, and one three-place function symbol $k$. Which of the following
four are closed terms in the language and which are not?
$$h(h(h(c))) \hspace{5mm} h(h(x)) \hspace{5mm} k(c,h(c), h(h(c))) \hspace{5mm} h(k(y,h(c), h(h(c))))$$

Consider the language from
Exercise [\[exc:langages:1\]](#exc:langages:1){reference-type="ref"
reference="exc:langages:1"}. Which of the following four are atomic
formulas and which are not?
$$R(x,g(a)) \hspace{5mm} \neg R(a,b) \hspace{5mm} \exists \; x \; x=g(x) \; \hspace{5mm} y=g(b)$$

Consider the language from
Exercise [\[exc:langages:2\]](#exc:langages:2){reference-type="ref"
reference="exc:langages:2"}. Which of the following four are formulas
and which are not?
$$\forall \; x \; h(x)  \hspace{5mm} \exists \; x \; h(c)=h(x) \hspace{5mm} k(x,y,z) =h(c) \; \wedge \; k(x,y,z)\neq h(h(c)) \hspace{5mm} h(c)\rightarrow h(h(c))$$

[\[exc:languages:truthnumbers\]]{#exc:languages:truthnumbers
label="exc:languages:truthnumbers"} Consider the language of arithmetic
from
§[\[para:languages:fourexamples\]](#para:languages:fourexamples){reference-type="ref"
reference="para:languages:fourexamples"} and the numerals from
§[\[para:languages:term\]](#para:languages:term){reference-type="ref"
reference="para:languages:term"}. Using the numerals, translate the
following from natural language into formulas in the language of
arithmetic:

One plus one is two.

One plus one is less-than-or-equal to three.

Two times two is not equal to five.

There is some number such that five is less than or equal to it.

Consider the language from
Exercise [\[exc:langages:1\]](#exc:langages:1){reference-type="ref"
reference="exc:langages:1"}. Which of the following are sentences and
which are mere formulas?

$\forall \; x \; \exists \; y \; f(x,y)=g(a)$.

$\forall \; x \; \exists \; y \; f(f(x,y),z)=g(b)$.

$\forall \; x \; (R(x,a)\rightarrow R(x,b))$.

$\forall \; x \; (R(a,y)\rightarrow R(b,x))$.

Consider the language from
Exercise [\[exc:langages:2\]](#exc:langages:2){reference-type="ref"
reference="exc:langages:2"}. For each of the below formulas, determine
whether the last occurrence of $x$ is free or bound.

$(\exists \; y \; (k(y,y,y)=h(c)) \rightarrow k(c,c,c)\neq h(x))$

$\forall \; x \; \forall \; y \; \exists \; z \; (k(h(x),h(y),h(z))=c \rightarrow k(x,x,x)=c)$.

$(\forall \; x \; k(x,x,x)=c)\rightarrow (\exists \; x \; k(c,c,x)=x)$.

$(\forall \; z \; \exists \; x \; k(z,z,x)=c)\rightarrow (k(c,c,x)\neq c)$.

Consider the language from
Exercise [\[exc:langages:1\]](#exc:langages:1){reference-type="ref"
reference="exc:langages:1"}. For each of the below formulas, determine
whether the first occurrence of $y$ is free or bound. Recall from after
the definition in
§[\[para:languages:freebound\]](#para:languages:freebound){reference-type="ref"
reference="para:languages:freebound"}, that in this sense of
"occurrence" we are not counting the instances that appear immediately
after the quantifiers. E.g. in $\exists \; y \; R(y,a)$, the $y$
variable only occurs once.

$(\exists \; y \; R(y,a))\rightarrow R(y,b)$.

$R(b,y)\rightarrow \exists \; z \; R(b,z)$.

$\forall \; x \; \exists \; y \; R(b,x)\wedge R(a,y)\rightarrow g(y)=a$.

$R(a,b)\rightarrow \exists \; x\; R(g(y),b)$.

[\[exc:first:terms\]]{#exc:first:terms label="exc:first:terms"} Consider
the language of arithmetic from
§[\[para:languages:fourexamples\]](#para:languages:fourexamples){reference-type="ref"
reference="para:languages:fourexamples"} and the numerals from
§[\[para:languages:term\]](#para:languages:term){reference-type="ref"
reference="para:languages:term"}. Let $\theta(x,y,z)$ be the formula
$x\boldplus y \boldleq z$. Let $t_3$ be the term $\boldS^3(\boldzero)$,
let $t_4$ be the term $\boldS^4(\boldzero)$, and let $t_5$ be the term
$\boldS^5(\boldzero)$. Do substitution and write out the following
formulas involving less-than-or-equal to:

$\theta(t_3,t_4,t_5)$

$\theta(t_4,t_3, t_5)$

$\exists \; x \; \theta(x,t_4,t_5)$

$\forall \; x \; \exists \; y \; \theta(x,y,t_5)$.

Consider the language from
Exercise [\[exc:langages:1\]](#exc:langages:1){reference-type="ref"
reference="exc:langages:1"}. Suppose that $t_1$ is $f(x,g(y))$ and $t_2$
is $g(f(x,x))$. Suppose that $\theta(u)$ is $\exists \; y \; R(y,u)$,
and $\chi(v)$ is $\forall \; x \; g(x)=g(v)$.

If we substitute $t_1$ for $u$ in $\theta(u)$, would any variables of
$t_1$ become bound as a result of the substitution?

If we substitute $t_2$ for $u$ in $\theta(u)$, would any variables of
$t_2$ become bound a result of the substitution?

If we substitute $t_1$ for $v$ in $\chi(v)$, would any variables of
$t_1$ become bound as a result of the substitution?

If we substitute $t_2$ for $v$ in $\chi(v)$, would any variables of
$t_2$ become bound as a result of the substitution?

\newpage
Solutions {#solutions .unnumbered .unnumbered}
---------

$g(f(a,b))$ is a term: one gets it by taking the constants $a,b$ and
applying the two-place function symbol $f$ to get $f(a,b)$, and then
applying the one-place function symbol $g$ to get $g(f(a,b))$.

$f(g(y,a))$ is not a term: for, $g$ is one-place but here it is given
two arguments $y,a$.

$f(g(x),g(b))$ is a term: for, one gets it by taking variables $x,b$,
and applying the one-place function symbol $g$ to them individually to
get $g(x), g(b)$, and then one applies the two-place function symbol $f$
to these to get $f(g(x), g(b))$.

$R(a,g(b))$ is not a term: it is rather an atomic formula, since it
involves predicates. No term will contain a predicate.

The term $h(h(h(c)))$ is closed and $k(c,h(c), h(h(c)))$ is closed since
they have no variables. But $h(h(x))$ and $h(k(y,h(c), h(h(c))))$ are
not closed since they have variables.

The atomic formulas are $R(x,g(a))$ and $y=g(b)$. The non-atomic
formulas are $\neg R(a,b)$ since it includes a negation, and
$\exists \; x \; x=g(x)$ since it includes a quantifier.

$\exists \; x \; h(c)=h(x)$ is a formula: it is formed from the atomic
$h(c)=h(x)$ by adding an existential quantifier. Likewise
$k(x,y,z) =h(c) \; \wedge \; k(x,y,z)\neq h(h(c))$ is a formula: it is
formed from an atomic and a negated atomic by adding a conjunction.

But $\forall \; x \; h(x)$ is not a formula: if it were, then removing
the quantifier would also result in a formula $h(x)$, but $h(x)$ is not
a formula but rather a term. Likewise, $h(c)\rightarrow h(h(c))$ is not
a formula: if it were, then removing the arrow would also result in two
formulas $h(c)$ and $h(h(c))$-- but these two are again not formulas but
terms.

These get translated respectively as:

$\boldS(\boldzero)\boldplus \boldS(\boldzero) = \boldS^2(\boldzero)$.

$\boldS(\boldzero)\boldplus \boldS(\boldzero) \boldleq \boldS^3(\boldzero)$.

$\boldS^2(\boldzero) \boldtimes \boldS^2(\boldzero) \neq \boldS^5(\boldzero)$.

$\exists \; x \; \boldS^5(\boldzero)\boldleq x$.

The first and third are sentences. The second has a free variable
(namely $z$) the fourth has a free variable (namely $y$).

The answers are the following, along with a little bit of explanation:

In $(\exists \; y \; (k(y,y,y)=h(c)) \rightarrow k(c,c,c)\neq h(x))$,
the last occurrence of $x$ is free since there is no quantifier which
binds $x$.

In
$\forall \; x \; \forall \; y \; \exists \; z \; (k(h(x),h(y),h(z))=c \rightarrow k(x,x,x)=c)$,
the last occurrence of $x$ is bound since it is bound by the initial
universal quantifier.

In
$(\forall \; x \; k(x,x,x)=c)\rightarrow (\exists \; x \; k(c,c,x)=x)$,
the last occurrence of $x$ is not free since it is bound the existential
quantifier.

In
$(\forall \; z \; \exists \; x \; k(z,z,x)=c)\rightarrow (k(c,c,x)\neq c)$,
the last occurrence of $x$ is free since the existential quantifier's
scope ends right after the $k(z,z,x)=c$ (as indicated by the "close
parentheses" appearing at that point).

The answers are the following, along with a little bit of explanation:

In $(\exists \; y \; R(y,a))\rightarrow R(y,b)$, the first occurrence of
$y$ is in the $R(y,a)$, where it is bound by the existential quantifier
and so is bound.

In $R(b,y)\rightarrow \exists \; z \; R(b,z)$, the first occurrence of
$y$ is in the $R(b,y)$, where it is free.

In
$\forall \; x \; \exists \; y \; R(b,x)\wedge R(a,y)\rightarrow g(y)=a$,
the first occurrence of $y$ is in $R(a,y)$, where it is bound by the
existential quantifier, and so is bound.

In $R(a,b)\rightarrow \exists \; x\; R(g(y),b)$, the first occurrence of
$y$ is in $R(g(y),b)$, where it is free.

[\[exc:first:number\]]{#exc:first:number label="exc:first:number"} The
formulas are the following:

$\boldS^3(\boldzero)\boldplus \boldS^4(\boldzero) \boldleq \boldS^5(\boldzero)$

$\boldS^4(\boldzero)\boldplus \boldS^3(\boldzero) \boldleq \boldS^5(\boldzero)$

$\exists \; x \; x\boldplus \boldS^4(\boldzero) \boldleq \boldS^5(\boldzero)$

$\forall \; x \; \exists \; y \; x\boldplus y \boldleq \boldS^5(\boldzero)$.

The answers are the following, along with a little bit of explanation:

If we substitute $t_1$ for $u$ in $\theta(u)$, the result is
$\exists \; y \; R(y,f(x,g(y)))$, and the free variable $y$ of $t_1$
becomes bound as a result of the substitution.

If we substitute $t_2$ for $u$ in $\theta(u)$, the result is
$\exists \; y \; R(y,g(f(x,x)))$, and no free variables of $t_2$ become
bound as a result of the substitution.

If we substitute $t_1$ for $v$ in $\chi(v)$, the result is
$\forall \; x \; g(x)=g(f(x,g(y)))$, and the free variable $x$ of $t_1$
becomes bound as a result of the substitution.

If we substitute $t_2$ for $v$ in $\chi(v)$, the result is
$\forall \; x \; g(x)=g(g(f(x,x)))$, and the free variable $x$ of $t_2$
becomes bound as a result of the substitution.
