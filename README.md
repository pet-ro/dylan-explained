Dylan Explained
===============

[opendylan]:  https://github.com/dylan-lang/opendylan "opendylan"
[dylan-lang]: https://github.com/dylan-lang           "dylan-lang @ github"
[pet-ro]:     https://github.com/pet-ro               "pet-ro @ github"

[github md]: http://github.github.com/github-flavored-markdown/ "GitHub flavored markdown"

[Success Git branching model]: 

[PerlGit]:     http://docs.activestate.com/activeperl/5.14/lib/pods/perlgit.html "PerlGit - Detailed information about Git and the Perl Repository"
[PerlGit: Topic branches]: http://docs.activestate.com/activeperl/5.14/lib/pods/perlgit.html#topic_branches_and_rewriting_history "Topic branches and rewriting history]

Dylan Explained is a documentation project related to the project
[opendylan][] at [dylan-lang][].

This document is written in [github md].


Goals of the project Dylan Explained
------------------------------------

<dl>
  <dt>Write a dylan language glossary</dt>
  <dd>Writing a <em>Ddylan Language Glossary</em> is the 
      <em>core goal</em> of 
      <em>Dylan-Explained</em>. 
 
      <p>Basically this should help to write 
      DEPs, <em>D</em>ylan <em>E</em>nhancement <em>P</em>roposals.
      </p>
  </dd>
</dl>

Possible Extensions in mind are:

 *  **Open Dylan Compiler Glossary**

    Basically that will be use to define the entry point
    for a project which like to enable the *Open Dylan Compiler*
    to read and write PDB files. The issue of not be able to write
    PDB files currently keeps people from contributing to the 
    *Open Dylan IDE*. The reasons for this is that to compile
    the *Open Dylan IDE* by the *Open Dylan IDE* requires
    to use a Microsoft Linker. As long as the Open Dylan
    Compiler can't write PDB files we have to stick to 
    *VisualC++ 6.0*. The basic idea for this project is:
    
    1. use the *PDB Writer* code of the CCI-Project.
       CCI, *C*ommon *C*ompiler *I*infrastructe is an
       open-sourced project from Microsoft Research.
   
    2. get help from the open-source community of MONO.
       Mono is the ppen source implementation of Microsoft's 
       .NET Framework. They have experience in implementing
       a *PDB Writer*.   

 *  **Open Dylan IDE Glossary**
  
    A revison of the IDE is required. To get the 
    big pictture of its design will write a glossary
    before hacking. Also to fix some useful terms, which
    are nessary the several developers can work as team.
   

 *  **A introduction to Dylan Programming**
   
    The idea is to use the granularity to rearrange the
    terms of the different glossaries in a way 
    that it becomes a readable introduction to 
    new dylan community members.
   

[pet-ro][] setup this project description on 2012-Aug-15. 

Appendix
 *  Appendix A: Best Practice: the branches of this git project
 *  Appendix B: A Git workflow example
 *  Appendix C: How this project was set up with Git
 




Appendix A: Best Practice: The branches of this git project
-----------------------------------------------------------

With in the [dylan-lang][]
it is recommended to use the [Successful Git branching model][] for
coding.

As the *Dylan Explained* is a documentation project, not a coding 
project*, we adpt this Git branching model:

The repo holds two main branches with am infite lifetime:

* master
* proofreading

The `master` branch at `origin` should be familiar to every Git user.
Parallel to the *master* branch, another branch exists called 
`proofreading`.

We consider `origin/master` to be the branch, where the source code
of `HEAD` always reflects a *production-ready* state. For example, from
there one can move the code to the [dylan-lang] project 
[opendylan][] / documentation. So this is would some will call the 
*integration branch*.


We consider `origin/proofreading` to be the branch, where invited people
merge their proofreading. This will be the **default branch**. 
The source of HEAD always reflect the latest proofreading state.
of all invited people.

We consider `origin/$yourname/proofreading` to be the branch, where a
invited person do changes during his or her proofreading privately. 
The source of HEAD always reflect your latest proofreading state
before it *may* be  merged to `origin/proofreading`.
You may invited people to look on this before merging to comment on it.
Typically no other user may contribute to that branch directly.
Other proofreader will use their own branch 
`origin/$yourname/proofreading`  branch during their private proofreading.
A stable state gets public by merging it to `origin/proofreading`.


We conside `origin/$yourname/drafting` to be the branch, where you write
your drafts which will be part of the *Dylan Explained* project in the future.
Especially source which is not stable enough for proofreading is located here.

We consider `origin/$yourname/proofreading` to be the branch

Appendix B: A Git workflow example 
----------------------------------

Users of git 1.7 or newer can do it in a more obvious manner:

1. Create your personal proofreading branch.
   It is personalized by prefix your username.

  $ my-proofreading="$my-name/proofreading"  
  $ git checkout -b  $my-proofreading origin/proofreading 
  $ git push origin -u $my-proofreading 

2. Create your personal drafting branch 

  $ my-drafting="$my-name/drafting"  
  $ git checkout -b  $my-drafting  origin/$my-proofreading 
  $ git push origin -u $my-drafting 


This workflow is inspired by the section [PerlGit: Topic branches] of [PerlGit].


Appendix B: How this project was set up with Git
-------------------------------------------------

To push the master branch to origin/master
 
 * git push origin -u master


To push the proofreading branch to origin/pofreading

 * git push origin -u proofreading:pofreading

To show all branches

 * git branch -a

Delete origin/profreading, because of mistyping:

 * git push origin :profreading

To push the proofreading branch to origin/proofreading

 * git push origin -u proofreading:proofreading