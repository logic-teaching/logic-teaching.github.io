Metalogic. Handout. Chapter 11, part 3.

\vspace{5mm}
Recall from Chapter 10:

\vspace{5mm}
**Peano Arithmetic ($PA$)** is a theory in the language of arithmetic
consisting of the eight axioms of **Robinson's Q**:

$\forall \; x \; \mathtt{S}(x)\neq \mathtt{0}$

$\forall \; x \; \forall \; y \; (\mathtt{S}(x)=\mathtt{S}(y)\rightarrow x=y)$

$\forall \; x \; (x\neq \mathtt{0}\rightarrow \exists \; w \; x=\mathtt{S}(w))$

$\forall \; x \; x+\mathtt{0}=x$

$\forall \; x \; \forall \; y \; x+\mathtt{S}(y)=\mathtt{S}(x+y)$

$\forall \; x \; x\cdot \mathtt{0}=\mathtt{0}$

$\forall \; x\; x\cdot \mathtt{S}(y)=x\cdot y +x$

$\forall \; x \; \forall \; y \; (x\leq y \leftrightarrow \exists \; z \; x+z=y)$

together with the **Mathematical Induction Schema**:
$$[\varphi(\mathtt{0}) \wedge \forall \; x \; (\varphi(x)\rightarrow \varphi(\mathtt{S}(x))]\rightarrow [\forall \; x \; \varphi(x)]$$

\vspace{5mm}
Here is a second-order version of this theory:

\vspace{5mm}
**Second-order Peano Arithmetic ($PA^2$)** is a theory in the
second-order language of arithmetic consisting of the eight axioms of
Robinson's Q together with with the **Mathematical Induction Axiom**:
$$\forall \; X \; [X(\mathtt{0}) \wedge \forall \; x \; (X(x)\rightarrow X(\mathtt{S}(x))]\rightarrow [\forall \; x \; X(x)]$$
and the **Comprehension Schema**, wherein $\varphi(x)$ ranges over
formulas in the language of second-order arithmetic with one free object
variable $x$:
$$\exists \; X \; \forall \; x \; (X(x) \leftrightarrow \varphi(x))$$

\vspace{5mm}
Here is the important theorem on $PA^2$ in the standard semantics:

\vspace{5mm}
(Dedekind's Categoricity Theorem) Suppose that $\mathcal{M}$ is a model
in the language of arithmetic. Then $\mathcal{M}^2\models PA^2$ if and
only if $\mathcal{M}$ is isomorphic to $\mathcal{N}$.

\newpage 
(Failure of compactness for second-order logic in standard semantics)

\vspace{2mm}
There is theory $\Sigma$ such that $\Sigma$ does not have a standard
second-order model, and yet every finite subset of $\Sigma$ has a
standard second-order model.

\newpage 
\vspace{5mm}
Now we turn to the extensional theory of types, which is just the a very
traditional way of doing 2nd-order logic together with 3rd-order logic
together with 4th-order logic etc.

\vspace{5mm}
The *types* are defined as follows:

$E$ is a type.

If $A,B$ are types, then $A\Rightarrow B$ is a type.

\vspace{5mm}
Intended interpretation:

\vspace{30mm}
Examples of more complicated types:

\vspace{70mm}
Further, if $A,B$ are types, then $\mathrm{app}^{A,B}$ is a two-place
function symbol of sort $(A\Rightarrow B, A, B)$ whose intended
interpretation is that $\mathrm{app}^{A,B}(f,x)=y$ iff and only
if $f(x)=y$.

If $f$ is a variable of type $A\Rightarrow B$ and $x$ is a variable of
type $A$, then $f(x)$ is just an abbreviation for the
term $\mathrm{app}^{A,B}(f,x)$ of type $B$.

\vspace{5mm}
We abbreviate "$t$ is of type $A$" as $t:A$.

\newpage 
Suppose that $D$ is a set. Then a **standard model $\mathcal{D}$ of the
extensional theory of types** is given by defining $D_E$ just to be $D$,
and one defines $D_{A\Rightarrow B}$ to be the set of all functions
from $D_A$ to $D_B$:
$$D_{E} = D, \hspace{10mm} D_{A\Rightarrow B} = \{f: D_A\rightarrow D_B\}$$
and finally the application functions are defined by application out in
the metatheory:
$$\mathrm{app}^{A,B}_{\mathcal{D}}: ((A\Rightarrow B)\times A)\rightarrow B, \hspace{10mm} \mathrm{app}^{A,B}_{\mathcal{D}}(f,x) = f(x)$$

\vspace{5mm}
Example models $\mathcal{D}$:

\vspace{40mm}
Examples elements of various $D_A$'s:

\vspace{5mm}
Example 1: the identity function

\vspace{40mm}
Example 2: (a family of) constant functions

\vspace{40mm}
Example 3: evaluating at a point

\newpage 
Examples of intuitive lambda notation in number systems:

\vspace{30mm}
[\[defn:term:many:pluslambda\]]{#defn:term:many:pluslambda
label="defn:term:many:pluslambda"} Let $\mathcal{L}$ be an expansion of
the language of the extensional theory of types by new constant symbols.
Then the **terms** of $\mathcal{L}$ are defined as follows:

Each variable of a type or constant of a type is a term of that type.

If $f$ is a term of type $A\Rightarrow B$ and $t$ is a term of type $A$,
then $f(t)$ is a term of type $B$.

If $v$ is a variable of type $A$ and $t$ is a term of type $B$, then
$\lambda v.t$ is a term of type $A\Rightarrow B$.

\vspace{5mm}
Writing our examples from bottom of previous page in lambda-notation:

\vspace{5mm}
Example 1:
$\hspace{3mm} x:A \hspace{3mm} \vdash \hspace{3mm} \lambda x.x : A\Rightarrow A$.

\vspace{40mm}
Example 2:
$\hspace{3mm}  x:A, \hspace{3mm} y:B \hspace{3mm} \vdash \hspace{3mm}\lambda x.\lambda y. x: A\Rightarrow (B\Rightarrow A)$.

\vspace{40mm}
Example 3:
$\hspace{3mm} x:A\Rightarrow A, \hspace{3mm} y:A \hspace{3mm} \vdash \hspace{3mm} \lambda x. x(y): (A\Rightarrow A)\Rightarrow A$.

\newpage 
Prove:
$\hspace{3mm} x:A\Rightarrow (B\Rightarrow C), \hspace{3mm} y:A\Rightarrow B, \hspace{3mm} z:A$

\vspace{2mm}
$\vdash \hspace{3mm}   \lambda x. \lambda y. \lambda z. (x(z))(y(z)):  (A\Rightarrow (B\Rightarrow C))\Rightarrow ((A\Rightarrow B)\Rightarrow (A\Rightarrow C))$

\newpage 
Illustration of the Curry-Howard correspondence:

\vspace{15mm}
First, let's remind ourselves of an easy proof in our Hilbert-style
deductive system from Chapters 7-8:

\vspace{2mm}
\vspace{2mm}
Prove:
$A\rightarrow (B\rightarrow C), \hspace{3mm} A\rightarrow B \hspace{3mm} \vdash \hspace{3mm} A\rightarrow C$.

  ---- ------------------------------------------------------------------------------------------------------------------------------------------------------------ ------------------
                                                                                                                                                                    
                                                                                                                                                                    
  1.   $\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_$   $(\_\_\_\_\_\_)$
                                                                                                                                                                    
                                                                                                                                                                    
  2.   $\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_$   $(\_\_\_\_\_\_)$
                                                                                                                                                                    
                                                                                                                                                                    
  3.   $\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_$   $(\_\_\_\_\_\_)$
                                                                                                                                                                    
                                                                                                                                                                    
  4.   $\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_$   $(\_\_\_\_\_\_)$
                                                                                                                                                                    
                                                                                                                                                                    
  5.   $\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_$   $(\_\_\_\_\_\_)$
  ---- ------------------------------------------------------------------------------------------------------------------------------------------------------------ ------------------

\vspace{10mm}
Here is a parallel argument about types:

\vspace{3mm}
Prove:
$x:A\Rightarrow (B\Rightarrow C), \hspace{3mm} y:A\Rightarrow B \hspace{3mm} \vdash \hspace{3mm} (({\bf S}x)y):A\Rightarrow B$.

  ---- ------------------------------------------------------------------------------------------------------------------------------------------------------------ ------------------
                                                                                                                                                                    
                                                                                                                                                                    
  1.   $\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_$   $(\_\_\_\_\_\_)$
                                                                                                                                                                    
                                                                                                                                                                    
  2.   $\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_$   $(\_\_\_\_\_\_)$
                                                                                                                                                                    
                                                                                                                                                                    
  3.   $\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_$   $(\_\_\_\_\_\_)$
                                                                                                                                                                    
                                                                                                                                                                    
  4.   $\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_$   $(\_\_\_\_\_\_)$
                                                                                                                                                                    
                                                                                                                                                                    
  5.   $\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_$   $(\_\_\_\_\_\_)$
  ---- ------------------------------------------------------------------------------------------------------------------------------------------------------------ ------------------

\newpage 
[\[defn:Qsem:den:many:mabda\]]{#defn:Qsem:den:many:mabda
label="defn:Qsem:den:many:mabda"} Let $\mathcal{L}$ be an expansion of
the language of the extensional theory of types by new constant symbols.
Let $\mathcal{D}$ be a model, and further let $s$ be a variable
assignment. Then for a term $t$ of type $A$, we define its
**denotation** $\mathrm{den}^s_{\mathcal{D}}(t)$, an element of $D_{A}$,
as follows:

If $t$ is a variable symbol $v$ of type $A$,
then $\mathrm{den}^s_{\mathcal{D}}(t)=s_{A}(v)$.[\[defn:Qsem:den:1:many:lambda\]]{#defn:Qsem:den:1:many:lambda
label="defn:Qsem:den:1:many:lambda"}

If $t$ is a constant symbol $c$ of type $A$,
then $\mathrm{den}^s_{\mathcal{D}}(t)=c_{\mathcal{D}}$.
[\[defn:Qsem:den:2:many:lambda\]]{#defn:Qsem:den:2:many:lambda
label="defn:Qsem:den:2:many:lambda"}

If $f$ is a term of type $A\Rightarrow B$ and $t$ is a term of type $A$,
then
$\mathrm{den}^s_{\mathcal{D}}(f(t)) = (\mathrm{den}^s_{\mathcal{D}}(f))(\mathrm{den}^s_{\mathcal{D}}(t))$.

If $v$ is a variable of type $A$ and $t$ is a term of type $B$, then
$(\mathrm{den}^s_{\mathcal{D}}(\lambda v.t))(a) = \mathrm{den}^{s[v/a]}_{\mathcal{D}}(t)$.

\vspace{2mm}
In last clause, $s[v/a]$ is the $v$-variant of $s$ which sends $v$ to
element $a$ of $D_A$.

\newpage 
Suppose that $\mathcal{D}$ is a standard model of the extensional theory
of types.

\vspace{20mm}
Example 1: Suppose that $v:A$. Recall that $\lambda v.v:A\Rightarrow A$.
Further, suppose that $a$ in $D_A$. Then:

\vspace{5mm}
$$\begin{aligned}
(\mathrm{den}^s_{\mathcal{D}}(\lambda v.v))(a) & =  \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_   \\ 
& \\
& = \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_  \\
& \\
& = \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ \end{aligned}$$

\vspace{20mm}
Example 2: recall that if $x:A$ and $y:B$ then ${\bf K}$ is
$\lambda x.\lambda y. x$, and it has
${\bf K}:A\Rightarrow (B\Rightarrow A)$. Further suppose that $a$ in
$D_A$ and $b$ in $D_B$. Then:

$$\begin{aligned}
((\mathrm{den}^s_{\mathcal{D}}(\lambda x.\lambda y.x))(a))(b) &  = \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_   \\ 
& \\
& = \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_  \\
& \\
& = \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ \\
& \\
& = \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ \\
& \\
& = \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ \end{aligned}$$
