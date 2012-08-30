..  About this file
    The file contains a ReST Chapter titled "Dylan Language Glossary"


    About the design history
    ------------------------

    Originally designed with the Sphinx directive `glossary`.
    But several drawback occured with this design:
    
    - you can't  have several glossaries, 
      but dylan-explain might contain in the future also other glossaries
    
    - you can't reference a term of the glossary with a glossary entries
      description itsself, when each term is stored in its own file.
      (Note: Sphinx Documentation, Release 1.1 states
       only ref will work across files.)

    - Spinix for unknown reasons does not allow to write  a ReST `include`
      directive directyl after  ``glossary`` directive. 

    The current design
    ------------------

    The glossary now builds on 
  
    - each glossary term is sorted in a file with the extension
      .txt
      
    - the glossary is build up by a list of Sphinx 'include' directives
      One 'include' directive for each glossary term file.      

    - the cross-referencing syntax of Sphinx only
      So you write 
       :ref:`target`    or
       :ref:`title<target>`   which will refer to target, but use title 
                              as link text.
       :ref:`!target`         no reference/hyperlink will be created
  
    - the cross-referencing labels of locations that are
      inside the chapter "Dylan Language Glossary" will
      by convention use the prefix `dylan-term-`.

    Advantage of this design
 
    - The design allows to use a file for each term

    - The design allows to cross-referencing of the terms.
      as :ref:`a-title<a-label>` will work across files.
      The Sphinx Documentation, Release 1.1, states :role: won't
      across files.

    Bugs and know workarounds in using Sphinx with this document
    ------------------------------------------------------------
    -  Bug:
         :samp:`import: {skew-liw => wrap-line}`
         is not show right:
         
         - the curce brackets
 
 
    -  Bug:
         Sphinx generates for the description of the term `binding` 
         html with a smaller font as for other description. 
         Why???
       Workaround:
         bug has gone after copy the folder 
         _static, _templates, _themes.




.. _chapter-dylan-language-glossary:

*********************************
Dylan Language Glossary          
*********************************

Note:

 - we distinguish between internal terms and external terms.
   A link to an *internal* terms stays within the chapter
   *Dylan Language Glossary*. 
   How we distinguish internal terms from other ones: A external
   link will contain a '@' character in its title. Example
   a link to the Dylan Referenc Manual might look like
   :drm:`Colophon@DRM <colophon>` and a link to 
   dylan's history entry on wikipedia might look like
   `History of Dylan Programming Language@wikipedia`_ 

 

 - All other links, which do not contain a '@'  are internal 
   to this *Dylan Language Glossary*.


.. list of external links

.. _History of Dylan Programming Language@wikipedia: http://en.wikipedia.org/wiki/History_of_the_Dylan_programming_language 

.. include:: ./terms/about-dylan.txt
.. include:: ./terms/about-software-development.txt
.. include:: ./terms/binding.txt
.. include:: ./terms/binding-sharing.txt
.. include:: ./terms/class.txt
.. include:: ./terms/classes-built-in.txt
.. include:: ./terms/client-server-interaction-of-modules.txt
.. include:: ./terms/compilation-unit.txt
.. include:: ./terms/definition.txt
.. include:: ./terms/first-class-object.txt
.. include:: ./terms/function.txt
.. include:: ./terms/generic-programming.txt
.. include:: ./terms/module.txt
.. include:: ./terms/sealing-techniques.txt
.. include:: ./terms/sealed-constructs.txt







