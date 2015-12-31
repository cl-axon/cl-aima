## Logic (Subsystem of AIMA Code)

[comment]: # (Changed by: Peter Norvig, 14-Apr-1997)

The <b>logic</b> system covers part III of the book.  We define
knowledge bases, and <tt>tell</tt> and <tt>ask</tt> operations on
those knowledge bases.  The interface is defined in the file <A
HREF="#logic/algorithms/tell-ask.lisp">tell-ask.lisp</A>.

<P>
We need a new language for logical expressions,
since we don't have all the nice characters (like upside-down A) that
we would like to use.  We will allow an infix format for input, and
manipulate a Lisp-like prefix format internally.  Here is a
description of the formats (compare to [p 167, 187]). The prefix
notation is a subset of the <A
href="http://logic.stanford.edu/kif/Hypertext/kif-manual.html">KIF
3.0</A> Knowledge Interchange Format.

| Infix                   | Prefix                 | Meaning              | Alternate Infix Notation |
|-------------------------|------------------------|----------------------|--------------------------|
| ``~P``                  | ``(not P)``            | negation             | not P                    |
| ``P ^ Q``               | ``(and P Q)``          | conjunction          | P and Q                  |
| <code>P &#124; Q</code> | ``(or P Q)``           | disjunction          | P or Q                   |
| ``P => Q``              | ``(=> P Q)``           | implication                   
| ``P <=> Q``             | ``(<=> P Q)``          | logical equivalence
| ``P(x)``                | ``(P x)``              | predicate   
| ``Q(x,y)``              | ``(Q x y)``            | predicate with multiple arguments
| ``f(x)``                | ``(f x)``              | function    
| ``f(x)=3``              | ``(= (f x) 3)``        | equality    
| ``forall(x,P(x)``       | ``(forall (x) (P x))`` | universal quantification
| ``exists(x,P(x)``       | ``(exists (x) (P x))`` | existential quantification
| ``[a,b]``               | ``(listof a b)``       | list of elements
| ``{a,b}``               | ``(setof a b)``        | mathematical set of elements
| ``true``                | ``true``               | the true logical constant
| ``false``               | ``false``              | the false logical constant

You can also use the usual operators for mathematical notation: ``+``, ``-``,
``*``, ``/`` for arithmetic, and ``<``, ``>``, ``<=``, ``>=`` for comparison.
Many of the functions we define also accept strings as input,
interpreting them as infix expressions, so the following are
equivalent:

```cl
(tell kb "P=>Q")  
(tell kb '(=> P Q))
```

