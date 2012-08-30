..  About this file
    The file contains a ReST Chapter titled "References"

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




.. _chapter-references:

*********************************
 References Compiler Glossary          
*********************************

.. toctree::
 

   ./bib/language-common-references

   ./bib/compiler-common-references

   ./bib/compiler-opendylan-references






