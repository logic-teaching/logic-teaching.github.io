  <script>
  MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
  </script>
  <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js"></script>

Translating into first-order languages {#chap:translating}
======================================

This chapter is a primer of translating into the language of first-order
predicate logic. It is assumed that one has seen propositional logic
before. One reason why translation is important is that we can only
apply the logical apparatus to evaluate natural language arguments if we
have translated them into logic. Another reason why translation is
important is that we are in general much quicker at working with natural
language arguments, and by translating back into (slight extensions) of
natural language, we can often gain a certain amount of intuition about
the logical problems at hand.

N[(mov)](https://drive.google.com/open?id=12mXOwVegewyZLOKyS7FnzsaIkxT7J_fC)
*Motivation for predicate logic*. In propositional logic, we take as our
basic unit the proposition, something that can be true or false. By
taking it as the basic unit, we mean we do not subject it to any further
analysis. For instance, while we translate "Claire is a student and Dave
is a student" as $p \wedge q$, we treat $p$ as a primitive and $q$ as
primitives: they are basic. In predicate logic, the idea is to introduce
another layer of analysis. In particular, the most basic idea is to
further analyze "Claire is a student" as $Sc$ and analyze "Dave is a
student" as $Sd$. So we translate "Claire is a student and Dave is a
student" as as $Sc\wedge Sd$. That is the idea. Why do this?

N*Motivation for predicate logic, continued*. One reason is that "Claire
is a student" and "Dave is a student" seem to have a common structure.
Someone could not understand the one without understanding the other.
And there is a common way to evaluate them: look at the list of
students! So translating as $Sc$ and $Sd$ reveals this common structure.
Consider another example. "Claire is a student and Claire is a
musician." We would translate this as $Sc\wedge Mc$. This level of
analysis lets us see a further consequence of the claim, namely that
there is some $z$ such that $Sz\wedge Mz$. We would not be able to see
this further consequence if we just stuck to propositional logic.

N[(mov)](https://drive.google.com/open?id=1CvYIVGW1q15DMOAgnZekyex0TTW1epEb)
[(con't)](https://drive.google.com/open?id=1DOzZ4PG1fp_AZ0aM8IDkfevt3soB26_6)
[(con't
con't)](https://drive.google.com/open?id=13TxA9ISO1JTQc5HrkfGYwKcP4EGA3XEM)
*Examples of translating*. The easiest way to learn logic is by doing
examples. Here we consider four examples of translations from natural
language into logic.

Consider the example: "Anne is a lawyer and Bill is a musician. So Anne
is not a musician and Bill is not a lawyer" We would translate this as:
$$La \wedge  Mb. \;\;\; \neg Ma \wedge \neg Lb$$ where we use the
following key: $L=$lawyer, $M=$musician, $a=$Anne, and $b=$Bill. This is
much like translating into propositional logic. But here is the new
element: the idea is that $Fd$ translates the statement that "object $d$
is a $F$". That is, in the translation, we suppress the "is", and we
allow the adjacency of $F$ to $d$ in "$Fd$" to signify the "is." Why do
we do that? Recall from propositional logic that we translated both "if
$p$ then $q$" as well as "$p$ only if $q$" by "$p\rightarrow q$". Why
did we do that back then? Well, it was because they had the same
truth-conditions. A similar idea here: we suppress the "is" in "$d$ is
an $F$" and write "$Fd$" instead because some expressions with similar
truth-conditions are not expressed with "is."

Consider the example: "Annes likes hockey. Bill likes soccer. Claire
does not like hockey and Claire does not like soccer." We would
translate this as: $$Ha. \;\;\; Sb. \;\;\; \neg Hc \wedge \neg Sc$$
where we use the following key: $H=$likes hockey, $S=$likes soccer, and
$a=$Anne and $b=$Bill and $c=$Claire. Hence, the idea is "Annes likes
hockey" has the same truth-conditions as "Anne is a fan of hockey." So
we translate them the same way, as $Ha$, even though one does not have
an "is". Much is lost in translation, but we retain compositional
structure: how truth of the whole depends on how things stand with $H$
and $a$.

Consider the example: "Anne is younger than Bill. Bill is younger than
Claire. Therefore, Anne is younger than Claire." We would translate this
as follows: $$Yab. \;\;\; Ybc. \;\;\; Yac.$$ where we have the key:
$Y=$younger than, $a=$Anne, $b=$Bill, $c=$Claire. Now of course $Yab$
differs from our previous $Ha$ in a number of ways: the former is also
about another individual besides Anne (namely, Bill). But we write $Yab$
in a way similar to $Ha$, namely adjacent to each other, because we are
trying to highlight that there is a deep similarity in what makes them
true and false: it is how things stand with $Y$, $a$, and $b$.

Consider the example: "Anne is younger than Claire or Claire is younger
than Anne. If Anne is younger than Claire, then Anne is younger than
Bill." We would translate as follows:
$$(Yac \vee Yca). \;\;\; (Yac \rightarrow Yab)$$ where we have the key:
$Y=$younger than, $a=$Anne, $b=$Bill, $c=$Claire. This example is much
like the third example, except here we have that there is additional
logical structure: we have an "or" and an "if ...then ...." Like with
propositional logic, we translate with the symbols $\vee$ and
$\rightarrow$. Thus you can apply everything you learned in translating
propositional logic to these examples.

N*The recipe for translating*. The general method behind the examples
goes like this:

Step 1. Identify the smallest components of the example which can be
true or false.

Step 2. Analyze smallest components in terms of objects
$a,b,c,d,e, \ldots$ having a property $F, G, H, \ldots$ or standing in a
relations $R, S, T \ldots$. Further, in this step 2, always give your
reader a "key" to work with, so that they can easily tell which symbols
stand for which words, ideas, or concepts.

Step 3. Look for components that are connected by "and", "or", "if
...then ..." or "iff". Then translate via the symbols
$\wedge, \vee, \rightarrow, \leftrightarrow$ Do the same for negation
$\neg$.

N*FAQs about translating*. Here are some commonly asked questions about
translating and their answers:

Q: How do I know what letters to use?

A: It does not matter. You can use whatever letters you want.

Q: Should not you translate "Anne is a Musician" by $aM$ rather than
$Ma$? It seems like you have the word-order backwards.

A: This is purely a matter of tradition. Traditionally, the property $M$
goes first, then the object $a$ which has the property.

Q: If we translate "Annes likes Bill" by $Lab$, should not we translate
"Annes likes hockey" by $LaH$?

A: First-order predicate logic is very limited, and cannot treat $LaH$.
(One can easily find an extension of the second-order logic of
Chapter [\[chap:manysorted\]](#chap:manysorted){reference-type="ref"
reference="chap:manysorted"} which can handle this).

N*A common mistake in translating*. One common mistake in translating is
to use multiple symbols for one and the same natural language word. For
instance, consider "Claire studies and Claire works." The correct
translation is $Sc\wedge Wc$. An incorrect translation is $Sc\wedge Wd$.
For, this translation fails to capture the idea that the truth of the
whole depends just on Claire (and not some other person). Similarly,
consider "Claire studies and Dave studies." The correct translation is
$Sc \wedge Sd$. An incorrect translation is $Sc \wedge Td$. This
translation is incorrect because the truth of the whole only depends on
how things stand with Claire, Dave and studying, and not on some other
property.

N[(mov)](https://drive.google.com/open?id=1WfIfazEP7FGFHUESRIA9-RfWHKO7fH2K)
*Quantifiers: surface grammar vs. truth-conditions*. So now we turn to
quantifiers. Consider the following three sentences.

1.  A. Anne is nice. B. Someone is nice. C. Everyone is nice.

There is an obvious sense in which all of these sentences are formed by
plugging different words into the "$\_\_\_\_$ is nice." This is an
important perspective. But the aim of our translations is to display the
way in which the truth of the whole depends on the truth of the parts.
How the truth of the whole depends on the truth of the parts differs
between A-C. For, observe that when we are trying to figure out whether
"Anne is nice" is true, we go look at Anne and see whether she is nice.
By contrast, to see whether "someone is nice" is true, we go searching
for someone (perhaps Bill?) who is nice. Finally, for "everyone is
nice", we need to make sure that Anne is nice, Bill is nice, etc. Not
only do the truth-conditions differ drastically, but while recognizing
the differences, we should also see that the truth conditions for B and
C are somehow based on those of A: each involves looking, in different
ways, at the list of people and checking for niceness.

N*The existential and universal quantifier*. Our solution is to
translate these as follows:

1.  A. $Na$. B. $\exists \; x \; Nx$. C. $\forall \; x \; Nx$.

where we follow the key: $N=$nice, $a=$Anne. We pronounce
"$\exists \; x \; Fx$" as "there is $x$ such that $Fx$." We pronounce
"$\forall \; x \; Fx$" as "for all $x$, $Fx$." Intuitively, the rule for
the truth of $\exists \; x \; Fx$: it is true exactly when there is at
least one $d$ such that $Fd$. The rule for the truth of
$\forall \; x \; Fx$: it is true exactly when $Fd$ holds for each
individual $d$.

N([mov](https://drive.google.com/open?id=1DwGY_HFKA0_r2r5KvYMMuQ1Xdhj6nuo8))
*Variables: the role they play*. Thus we translate "someone is nice" by
"$\exists \; x \; Nx$." Note that we add something which has no analogue
in the English sentence, namely the $x$. This $x$ is a variable. Note
$x$ is used twice in sentence "$\exists \; x \; Nx$." Its instance in
"$\exists \; x$" is a signal: go look for $d$ such that $Nd$, where you
get $Nd$ from $Nx$ by plugging in $x=d$. To see why this is useful,
consider "Someone is younger than Claire." We would translate this one
by: $$\exists \; x \; Yxc$$ The $x$ signals to us that to evaluate its
truth, we go look for an $d$ such that $Ydc$ as opposed to $Ycd$. The
two instances of $x$ together tell you how to go about applying the rule
for truth.

N[(mov)](https://drive.google.com/open?id=1RV_bpq0nvoJLyHt6fwfVC0kIlkMKQnVx)
*Variables: what they cannot do*. Consider again "Anne is nice" and
"Someone is nice". We translate the first by "$Na$" and the second by
"$\exists \; x \; Nx$." Note that both of these sentences can, of
course, be either true or false. However, consider $Nx$ all by itself.
It seems that $Nx$ is not the kind of thing that can be true or false on
its own. For, the $x$ just marks a spot here, and does not pick out an
individual like Anne or Bill. Hence sentences with variables like $Nx$
but without quantifiers like $\exists \; x \;$ or $\forall \; x \;$ are
not propositions. Our use of the word "variable" coincides with the use
in math: $x+4=5$ is not true or false on its own, while $1+4=5$ is true
and $2+4=5$ is false. Like in math, when we see $x+4=5$ or $Nx$, we
might get some idea for which values of $x$ make it true ("it has got to
be $x=1$!" "it has got to be $x=$Anne!"), but all by itself $x+4=5$ and
$Nx$ are neither true nor false.

N[(mov)](https://drive.google.com/open?id=1Lm-AZanmV1Cx4NtBkSlk03YcNmHh-mVo)
*Some translation
schemas*.[\[para:translation:table\]]{#para:translation:table
label="para:translation:table"} Here is a helpful table which summarizes
and illustrates some common translation schemas:

  Scheme                  Translation                                 Example and ...                   ...its translation
  ----------------------- ------------------------------------------- --------------------------------- -------------------------------------------
  Some $F$ are $G$.       $\exists \; x \; (Fx \wedge Gx)$            Some politicians are lawyers      $\exists \; x\;  (Px \wedge Lx)$
  Some $F$ are not $G$.   $\exists \; x \; (Fx \wedge \neg Gx)$       Some lawyers are not judges.      $\exists \; x \; Lx \wedge \neg Jx$
  All $F$ are $G$.        $\forall \; x \; (Fx\rightarrow Gx)$        All composers are musicians.      $\forall\; x \; (Cx\rightarrow Mx)$
  All $F$ are not $G$.    $\forall \; x \; (Fx\rightarrow \neg Gx)$   All snakes are not warm-blooded   $\forall \; x \; (Sx\rightarrow \neg Wx)$
  No $F$ are $G$.         $\neg \exists \; x \; (Fx \wedge Gx)$       No snakes are warm-blooded        $\neg (\exists \; x \; (Sx\wedge Wx))$

\normalsize
N[(mov)](https://drive.google.com/open?id=1ximMD8A1mKcVlEK9v7Of7Yxuq5ymBfVT)
*Sentences with more than one quantifier*.
[\[para:translating:trustex\]]{#para:translating:trustex
label="para:translating:trustex"} We have been translating
someone/something by the existential quantifier and everyone/everything
by the universal quantifier. But some examples contain both of these
things at once:

Consider the sentence "Everyone trusts someone." This is true in a
situation in which each person trusts at least one other person. To
translate this, we separate out into the noun-phrase "everyone" and the
verb-phrase "trusts someone." We put a variable into the noun-spot
within the verb-phrase to make it "$x$ trusts someone" (it does not
matter which variable you use-- just choose one that does not occur
previously in the problem). Then we translate the verb-phrase using
familiar methods as "$\exists \; y \; Txy$". Then we move back to the
noun-phrase and translate it using the universal quantifier relative to
inserted variable, to get "$\forall \; x \; x$ trusts someone." Then we
put these two translations together to get the translation
"$\forall \; x \; \exists \; y \; Txy$."

Consider the sentence "Someone is trusted by everyone." This is true in
a situation in which there is a single person whom everyone trusts. To
translate, we separate out the noun-phrase "someone" and the verb-phrase
"is trusted by everyone." We put a variable into the noun-spot of the
verb-phrase to make it "$y$ is trusted by everyone." Then we translate
the verb-phrase using familiar methods as "$\forall \; x \; Txy$." Then
we move back to the noun-phrase and translate it using the existential
quantifier relative to the inserted variable, to get
"$\exists \; y \; y$ is trusted by everyone." Then we put these two
translations together to get "$\exists \; y \; \forall \; x \; Txy$."

In general, the recipe for translating is: separate into noun-phrase and
verb-phrase, insert a new variable into the noun-spot of the
verb-phrase, translate the verb-phrase and the noun-phrase separately,
and then combine the two translations.

N[(mov)](https://drive.google.com/open?id=1c1VWKc6-cV0X9gI8xTo_4HlgStXPhLuM)
*Sentences with identity*.
[\[para:translating:identity\]]{#para:translating:identity
label="para:translating:identity"} The identity relation is simply
written as $x=y$. We abbreviate its negation $\neg (x=y)$ as $x\neq y$.
We can use this to translate the following examples:

Consider the sentence "There are at least two geography majors." We
translate it as follows:
$$\exists \; x \; \exists \; y \; Gx \; \wedge Gy \; \wedge x\neq y$$
with the key $Gx=x$ is a geography major.

Consider the sentence "Everyone besides Bill deserves a prize." We
translate it as follows: $$\forall \; x \; (x\neq b\rightarrow Dx)$$
with the key $Dx=$"$x$ is deserves a prize" and $b=$Bill.

In these two examples, the basic idea is that the identity relation just
lets us declare that certain things we are talking about are distinct.
Note that the identity relation is not explicit in the surface grammar:
hence our translations do not preserve surface grammar. What our
translations preserve is truth-conditions: the identity relation helps
us precisely describe the circumstances in which the sentences are true
or false.

N[(mov)](https://drive.google.com/open?id=1a2_06ucg02yE7zdqTbkKvTgBtGbWbJHe)
*Translating with function symbols*.
[\[para:translating:func\]]{#para:translating:func
label="para:translating:func"} Often we will have a function symbol
which takes one object (or a finite collection of objects) to another
object. For instance, we might have a function $m(x)$ for "the mother of
$x$" and a function $k(x,y)$ for "the first-born child of $x$ and $y$."
For instance, we would translate "Anne is the mother of Bill, and Dave
is the first-born child of Bill and Claire" by
$$a=m(b) \wedge d=k(b,c)$$ with the obvious key $a=$Anne, $b=$Bill,
$c=$Claire, and $d=$Dave. These are more familiar from mathematical
examples, such as arithmetic. For instance, we have the successor
operation $S(x)$ which takes any natural number to the number which
immediately follows it. Hence "Three is the successor of two, and four
is the successor of the successor of two" would be translated as
$$3=S(2) \wedge 4=S(S(2))$$ In this example, we are using $2, 3, 4$ as
names for numbers just like we used proper names for names of people.

\newpage
Exercises {#exercises .unnumbered .unnumbered}
---------

Translate each of the following into first-order predicate logic. Use
the key $a=$Anne, $b=$Bill, $Wx=x$ wins, $Px=x$ is a philosophy-major,
$Gx=x$ is a geology-major, $Hx=x$ is happy, $Rxy=x$ respects $y$, and
$f(x)=$ father of $x$.

If Anne wins, then Bill does not win.

Someone wins. Not everyone wins.

If someone wins, then Anne wins.

All philosopher-majors are happy.

No geology-major is happy.

Everyone is respected by someone.

Someone is not respected by everyone.

Everyone besides Anne does not win.

At least three people do not win.

The father of Anne is Bill. Bill's father does not win.

\newpage
Solutions {#solutions .unnumbered .unnumbered}
---------

$Wa\rightarrow \neg Wb$.

$\exists \; x \; Wx$. $\neg \; \forall \; x \; Wx$.

$(\exists \; x \; Wx)\rightarrow Wa$.

$\forall \; x \; (Px\rightarrow Hx)$.

$\neg \; \exists \; x \; (Gx \wedge Hx)$.

$\forall \; y \; \exists \; x \; Rxy$.

$\exists \; y \; \forall \; x \; \neg Rxy$. Another equally good
solution might be: $\exists \; y \; \neg \forall \; x \; Rxy$. It
depends on whether you are parsing the verb-phrase as "not-respected by
everyone" or "not respected-by-everyone."

$\forall \; x \; (x\neq a\rightarrow \neg Wx)$.

$\exists \; x \; \exists \; y \; \exists \; z \; x\neq y \wedge y\neq z \wedge x\neq z \wedge \neg Wx \wedge \neg Wy \wedge \neg Wz$.

$f(a)=b$. $\neg W(f(b))$.
