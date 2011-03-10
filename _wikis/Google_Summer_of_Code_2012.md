---
title: Google Summer of Code 2012
---

Introduction
------------

The Open Bioinformatics foundation is [applying to participate in the
Google Summer of
Code](http://www.open-bio.org/wiki/Google_Summer_of_Code).

We are accepting applicants for projects for BioJava. If you want to
propose a project, have a look at the <BioJava:Modules> page, for areas
which are currently under development.

Please read the [GSoC page at the Open Bioinformatics
Foundation](http://www.open-bio.org/wiki/Google_Summer_of_Code) and the
[main Google Summer of Code page](http://code.google.com/soc) for more
details about the program.

Project Proposals
-----------------

Amino acids physico-chemical properties calculation  

<!-- -->

Rationale  
The calculation of simple physico-chemical properties for biopolymers is
an important tool in the arsenal of molecular biologist. Theoretically
calculated quantities like extinction coefficients, isoelectric points,
hydrophobicities and instability indices are useful guides as to how a
molecule behaves in an experiment. Many tools for calculating these
properties exist, including widely used open-source implementations in
EMBOSS and BioPerl, but only some are currently available in BioJava3.
The aim of this project is to port or produce new implementations of
standard algorithms for a range of calculations within BioJava3.

<!-- -->

Approach  
The following methods will be implemented in pure Java. High performance
will be insured by possibility of multithreaded calculations.

1.  Molecular weight
2.  Extinction coefficient
3.  Instability index
4.  Aliphatic index
5.  Grand Average of Hydropathy
6.  Isoelectric point
7.  Number of amino acids in the protein (His, Met, Cys)

A standalone Java library will be developed and an API for other Java
programs to use these functions as well as the command line executable.

Challenges  
Functional tests will be developed for tools, along with API and high
level documentation for end users. The BioJava3 data model already
provides support for representing the fundamental properties used in
each calculation, but new methods will be needed to apply the
calculations to objects representing biological molecules.

<!-- -->

Involved toolkits or projects  
Java, BioJava3, Eclipse, JUnit.

<!-- -->

Degree of difficulty and needed skills  
This is a simple low risk project as algorithms are independent of each
other and simple. Interested students should have a general knowledge of
core Java programming, knowledge of multi-threaded programming will be
beneficial. There is plenty of scope for the student to implement other
property calculations not listed here which will be beneficial for the
Java Bio- and Medical informatics communities.

<!-- -->

Mentor  

[Peter Troshin](User:Ptroshin "wikilink"), co-mentor (?)

------------------------------------------------------------------------

Extend Sequence Viewer code to become a client for the Distributed Annotation System  
The Sequence Viewer [1](https://github.com/biojava/RCSB_SequenceViewer)
is a project that can display protein annotations projected onto various
types of protein sequences (PDB, UniProt, etc). So far all annotations
are loaded from flat files or local databases. It would be nice to
extend this viewer to add support for the [Distributed Annotation
System](http://www.biodas.org) (DAS).

Challenges  
Existing components that enable DAS communication will be used to extend
the sequence drawing code base. The code is currently single threaded.
In order to enable efficient data display a multi-threaded layer and an
event model be added.

Degree of difficulty and needed skills  

Medium to Difficult. Pre-existing experience with multi threaded
programming will be of benefit. The sequence code is complex and
requires some Java experience to efficiently extend the existing
components.

Mentor  

[Andreas Prlic](User:Andreas "wikilink"), co-mentor (?)

Previous Years
--------------

[Google Summer of Code 2010](Google Summer of Code 2010 "wikilink")