Dylan Explained
===============

[opendylan]:  https://github.com/dylan-lang/opendylan "opendylan"
[dylan-lang]: https://github.com/dylan-lang           "dylan-lang @ github"
[pet-ro]:     https://github.com/pet-ro               "pet-ro @ github"

[github md]: http://github.github.com/github-flavored-markdown/ "GitHub flavored markdown"
[Success Git branching model] 
[PerlGit]     http://docs.activestate.com/activeperl/5.14/lib/pods/perlgit.html "PerlGit - Detailed information about Git and the Perl Repository"


Dylan Explained is a documentation project related to the project
[openylan][] at [dylan-lang][].

This document is written in 


Goals of the project Dylan Explained
------------------------------------

<dl>
  <dt>Write a dylan language glossary</dt>
  <dd>Writing a *dylan language glossary* is the *core goal* of 
      *Dylan-Explained*. Basically this should help to write 
      DEPs, *D*ylan *E*nhancement *P*roposals.
  </dd>
</dl>

Possible Extensions *maybe* are:

  <dt>Open Dylan Compiler Glossary</dt>
  <dd>Basically that will be use to define the entry point
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
   </dd>

   <dt>Open Dylan IDE Glossary</dt>
   <dd>A revison of the IDE is required. To get the 
       big pictture of its design will write a glossary
       before hacking. Also to fix some useful terms, which
       are nessary the several developers can work as team.
   </dd>

   <dt>A introduction to Dylan Programming</dt>
   <dd>The idea is to use the granularity to rearrange the
       terms of the different glossaries in a way 
       that it becomes a readable introduction to 
       new dylan community members.
   </dd>
</dl>

The branches of this git project
--------------------------------

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
to a proofreading. This will be the **default branch**. The source of HEAD
always reflect the latest proofreading state.

We consider `origin/pet-ro/drafting` to be a branch, where [pet-ro][] 
will invited people to look on first drafts to comment them.
Typically no other user may contribute to that branch directly.
Other contribute will typical use`the default branch 
`origin/proofreading` to create their own drafting branch.

The workflow with git detailed
------------------------------

This worlkflow is inspired by [PerlGit].


Individual committers should create topic branches under 
**yourname/some-descriptive-name**. 
Other committers should check with a topic branch's creator 
before making any change to it.

The simplest way to create a remote topic branch that works 
on all versions of git is to push the current head as a new branch 
on the remote, then check it out locally:

  $ branch="$yourname/$some_descriptive_name"   
  $ git push origin HEAD:$branch  
  $ git checkout -b $branch origin/$branch  

Users of git 1.7 or newer can do it in a more obvious manner:

  $ branch="$yourname/$some_descriptive_name"  
  $ git checkout -b $branch  
  $ git push origin -u $branch  

If you are not the creator of **yourname/some-descriptive-name, you might 
sometimes find that the original author has edited the branch's history. 
There are lots of good reasons for this. 

* Sometimes, an author might simply be rebasing the branch onto 
  a newer source point. 
* Sometimes, an author might have found an error in an early commit 
  which they wanted to fix before merging the branch to proofreading.





[pet-ro][] wrote this project description on 2012-Aug-15. 