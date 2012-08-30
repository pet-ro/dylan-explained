..  DEP is short for Dylan Enhancement Proposal

..  DEP Format and validation
       
    DEPs must be written in ReStructuredText_ format. 

    The DEP author must verify that the ReStructuredText_ parses correctly.
    For example::

    git clone git@github.com:dylan-lang/website.git
    cd website
    cp your-dep.rst source/proposals/dep-1234.rst
    make html

    Fix any errors that are displayed



.. _dep-generic-programming:

..  DEP Title
======================================================
Generic Progamming definitions: Concept and Model 
======================================================

 

..  DEP Preamble


==============  =============================================
DEP Number:     unassigned
Type:           Standards Track
Author:         Peter Robisch <pet-ro@odendylan.org>
Status:         Draft
Affects-DRM:    Yes
Created:        <first dep number assignment date>
Last-Modified:  <last modified date>
Post-History:   <oldest post date>, <newest post date>
Resolution:     <url pointing to the pronouncement of the dep>
Target-Version: <indicate the OD release version of the DP>
Requires:       <DEP-number-(s)-required-by-this-DEP>
Auxilary-File:  <dep-XXXX-a-name.ext>
==============  =============================================


..  DEP Table of Content

.. contents: Contents
   :local:


..  DEP Abstract

Abstract
=========


The [Article: A Language for Generic Programming in the Large (2007)]_ 
states a list of requirements for a language to 
support generic programming. We will check here what we like to see
to be adopted to the dylan language.


..  DEP Copyright

Copyright
=========

**provide a copyright information** 


..  DEP Specification

Specification
=============

The list of requirements for a language to support generic programming 
as state in [Article: A Language for Generic Programming in the Large (2007)]_.

- The language provides type parameterized functions with the ability 
  to express constraints on the type parameters. The definitions of 
  parameterized functions are type checked independently of how 
  they are instantiated.



- The language provides a mechanism, such as *concepts*, for naming and 
  grouping requirements on types, and a mechanism for composing concepts 
  (refinement).

- Type requirements include:
  - requirements for functions and parameterized functions
  - associated types
  - requirements on associated types
  - same-type constraints

- The language provides an implicit mechanism for providing 
  type-specific operations to a generic function, but this mechanism 
  should maintain modularity (in contrast to argument dependent lookup in C++).

- The language implicitly instantiates generic functions when they are used.

- The language provides a mechanism for concept-based dispatching between 
  algorithms.

- The language provides function expressions and function parameters.

- The language supports conditional modeling.
 
..  DEP Motivation

Motivation
==========



..  DEP Rational

Rational
========
The goal:

  "That is the fundamental point: algorithms are
  defined on algebraic structures."

  - Alexander Stepanov 
   
    - see also: [Concept definitions from Elements of Programming
      <http://www.elementsofprogramming.com/eop-concepts.pdf>], 
      which summarizes the concept definition detailed in
      [Book: Elements of Programming (2009)
      <http://www.elementsofprogramming.com/book.html>]
      

  "My working definition of generic programming is *programming with concepts*,
  where a concept is defined as a family of abstractions that are all related 
  by a common set of requirements."

  - [David R. Musser @ www.cs.rpi.edu <http://www.cs.rpi.edu/~musser/gp/>]
    - see also Musser's work on 
      [Formal Specification of STL Container and Iterator Concepts @ www.cs.rpi.edu
      <http://www.cs.rpi.edu//~musser/gp/formal.html>]

   "The signature of an algorithm gives the necessary carries
   and operators, the adjectives of an algorithm gives 
   minimal conditions under which the algorithm works correctly

   - Christoph Schwarzweller
   
     - see also:
      
       - [Habilitation thesis: Towards Formal Support for Generic Programming (2003)
         <http://delta.math.univ.gda.pl/~schwarzw/papers/habil.pdf>]
    
       - together with David Musser and S. Schupp: [The Tecton Concept Library (1999)
         <http://delta.math.univ.gda.pl/~schwarzw/papers/tecalg.pdf>]


  "Using generic programming concepts to define algebraic structures creates
  a symbios between generic programming and algebra"

  - Peter Goldschling
   
    see also [Fundamental Algebraic Concepts in Concept-Enables C++ ("006)
    <http://www.cs.indiana.edu/pub/techreports/TR638.pdf>]


These are relevant topics:

- :ref:`generic programming - model passing @ programming language glossary
  <language-term-generic-programming-model-passing>`

- :ref:`generic programming - model passing @ the language G
  <language-term-generic-programming-the-language-G>`

- What is a test field for generic programming?
   
  - G uses Boost Graphic Library
 



..  DEP Use Case Example

Example
=======

** provide an example **


..  DEP Backwards Compatibility

Backwards Compatibility
=======================

** provide a backwards compatibility information**


..  DEP Reference Implementation
    Reference Implementation -- The reference implementation must be
    completed before any DEP is given status "Final", but it need not
    be completed before the DEP is accepted.  It is better to finish
    the specification and rationale first and reach consensus on it
    before writing code.

    The final implementation must include good test code and
    documentation.




Terminology
===========

_dep-generic-programming(gp-terminology):

Generic Programming Terminology
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

based on [Habilitation thesis: Towards Formal Support for Generic Programming (2003)].

_dep-generic-programming(gp-term-generalized-algorithm):

Generic Programming
     Generic programming is a  discinpline of computer science that aims 
     at developing methods to write and organize algorithms that are broadly 
     adaptable and interoperable, this allowing a maximum of reuse. 
     Compared with ordinary algorithms generic algorithms are more abstract. 
     Generic algorithm can be considered as algorithm schemes. 
     Generic algorithm should work for every instantiation, that is 
     for every  completion of the scheme. This means a great part of 
     program code can be reused for different types. The identification of 
     these generic parts leads to the expression of algorithms with minimal 
     assumption about the data abstractions: generic programming deals with 
     finding abstract representations of algorithms with respect to minimal 
     requirements that make such an algorithm work. Therefore generic 
     programming is also called *requirement oriented programming*. 
     Requirements for generic algorithms have to be carefully identified 
     so that the efficiency of a method is kept. Requirements have to be 
     represented in order to make clear for which class of specialization 
     a generic algorithm is suited.



Generalized algorithm
    A generalized algorithm  supports to  abstract from details and 
    allows to plug in different data structures, representation 
    or even algorithms.
 
    What can be plugged in is not completely arbitrary. For example, 
    sorting algorithms expect that the elements of a sequence can be compared. 
    The  code plugged in must come with a number of properties so that the 
    resulting algorithm works properly. This leads to the requirement 
    that their must be a notation for these properties which both side, 
    algorithm and plug-in can trust on. The Tecton, a Generic Programming
    Methodology, introduces *concept* as an entity which bundles together
    coherent sets of requirements. In Tecton *model* are data types that
    implement the concepts.
 


_dep-generic-programming(gp-term-formal-support-for-gp):

Formal Support for Generic Programming
    - has to

      - prove that if an instance come with the properties required
        by teh generic algorithm, the resulting instance meets the
        algorithm's specification.
   
      - handle the questions: 
     
        -  what requirements are necessary in order that a generic algorithm 
           works correctly for a class of instantiations 
        and 
   
        -  how this can be expresed in formal manner.

    and

    - should

      - support to check whether a generic algorithm is
        applicable in a particular situation 
    
      and, the other way around,

      - inform the user if a generic algorithm is not applicable.


Tecton
   Exact representation of requirements are necessary for
   :ref:`generalized algorithm
   <dep-generic-programming(gp-term-generalized-algorithm)>`.
   Tecton provides such an exact representation. Tecton is
   a description language for concepts. In Tecton classes of
   algebras represent exact requirements and are called 
   concepts*. 
   
   Tecton's concept desription language allows to heavily
   reuse already existing concept descriptions.


_dep-generic-programming(common-dylan-terminology):

Common Dylan Terminology
^^^^^^^^^^^^^^^^^^^^^^^^
Dylan Reference Manual (DRM)
    The manual written by Andrew Shalit, plus its errata.

Dylan language specification
    The DRM *plus* all **Accepted** DEPs that modify the Dylan
    language specification.

Open Dylan (OD)
    The reference implementation of the Dylan language specification.

Standard libraries
    The set of libraries that are officially maintained alongside Open
    Dylan.  They are officially maintained in the following sense:

      * Commits are reviewed for bugs and style.
      * They are tested prior to each OD release.
      * They are packaged with each OD release.





References and Footnotes
========================

.. [Habilitation thesis: Towards Formal Support for Generic Programming (2003)]
   *Towards Formal Support for Generic Programming* (2003) authored by
   Christoph Schwarzweller. Habilitation thesis, Informatik, 
   Eberhard-Karls-University, u'Tübingen', Germany, 2003-Jan. 
   [online accessed 2012-08-29 <http://delta.math.univ.gda.pl/~schwarzw/papers/habil.pdf>]
    

.. [Paper: The Tecton Concept Description Language (1998)]  *The
   Tecton Concept Description Language* (1998)
   authored by David R. Musser (Rensselaer Polytechnic Institute
   Troy, New York). Published at 


.. [Article: A Language for Generic Programming in the Large (2007)]  
   *A Language for Generic Programming in the Large* (2007)
   authored by Jeremy G. Siek (Department of Electrical 
   and Computer Engineering, University of Colorado at Boulder, USA)  
   and  
   Andrew Lumsdaine(Computer Science Department, Indiana University, USA).
   Pubished by  [arXiv:0708.2255v1 <DEP-Link: arXiv:0708.2255v1>]_ 
   in the rubrik cs.PL.
.. _[DEP-Link: arXiv:0708.2255v1]: http://arxiv.org/abs/0708.2255v1

.. [2] *The C++0x Concept Effort* (2010). Slides authored by
   Jeremy G. Siek (Department of Electrical 
   and Computer Engineering, University of Colorado at Boulder, USA).
   Published at SSGIP2010. [Online<Slides: The C++0x Concept Effort (2010)>]_
   at www.docstoc.com, 
   [PDF of slides <Slides (PDF): The C++0x Concept Effort (2010)>]_ at www.arxiv.org.
.. _[Slides: The C++0x Concept Effort (2010)]: http://www.docstoc.com/docs/76031207/The-Concept-Effort
.. _[Slides (PDF): The C++0x Concept Effort (2010)]: http://arxiv.org/pdf/1201.0027.pdf


.. [3] *Groups Lecture 1* (2011) 
   authored by Prof. O P Dogra ().
   Published by [www.mathematicsoncommand.com 
   <Groups Lecture 1 @ www.mathematicsoncommand.com>]_
.. _[Groups Lecture 1 @ www.mathematicsoncommand.com]: http://www.mathematicsondemand.com/wp-content/uploads/2011/06/Groups-Lect-1.pdf


.. _Open Publication License: http://www.opencontent.org/openpub/

.. _reStructuredText: http://docutils.sourceforge.net/rst.html


Copyright
=========

This document has been placed in the public domain.







