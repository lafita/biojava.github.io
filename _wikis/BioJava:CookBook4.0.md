---
title: BioJava:CookBook4.0
---

BioJava Cookbook for release 3.\*
---------------------------------

BioJava 3 is a major re-write of BioJava 1. As such many things work
differently. This cookbook will provide examples how to work with the
new codebase.

The page was inspired by various programming cookbooks and follows a
"How do I...?" type approach. Each "How do I?" is linked to some example
code that does what you want and sometimes more. Basically if you find
the code you want and copy and paste it into your program you should be
up and running quickly. I have endeavoured to over document the code to
make it more obvious what I am doing so some of the code might look a
bit bloated.

If you have any suggestions, questions or comments contact the [biojava
mailing list](mailto:biojava-l@biojava.org). To subscribe to this list
go [here](http://biojava.org/mailman/listinfo/biojava-l)

If you re-use code from the cookbook please cite:

How Do I....?
-------------

### biojava3-core

-   [Overview of
    biojava3-core?](BioJava:CookBook:Core:Overview "wikilink")
-   [How are sequences
    created?](BioJava:CookBook:Core:Sequences "wikilink")
-   [How do I read or write Fasta
    files?](BioJava:CookBook:Core:FastaReadWrite "wikilink")

### biojava3-genome

-   [Overview of
    biojava3-genome?](BioJava:CookBook:genome:Overview "wikilink")

### biojava3-phylo

-   [Overview of
    biojava3-phylo?](BioJava:CookBook:Phylo:Overview "wikilink")

**Required modules**: ''biojava3-core

**Required external library**: *forester.jar*

### biojava3-alignment

**Required modules**: *biojava3-alignment, biojava3-core,
biojava3-phylo*

**Required external library**: *forester.jar*

-   [How can I calculate a Pairwise Sequence
    Alignment](BioJava:CookBook3:PSA "wikilink")? (Smith Waterman,
    Needleman Wunsch)
-   [How can I create a Multiple Sequence
    Alignment](BioJava:CookBook3:MSA "wikilink")?
-   [How can I profile the time and memory requirements of a Multiple
    Sequence Alignment](BioJava:CookBook3:MSAProfiler "wikilink")?

### Protein Structure

**Required modules**: *biojava-structure, alignment* (will change soon
to new biojava3-alignment)

**Optional module** : *biojava-structure-gui* for the 3D visualisation

**Optional external library** : *JmolApplet.jar* for the 3D
visualisation

-   [How can I parse a PDB
    file?](BioJava:CookBook:PDB:read3.0 "wikilink")
-   [How can I parse a .mmcif
    file?](BioJava:CookBook:PDB:mmcif "wikilink")
-   [How can I access the atoms in a
    structure?](BioJava:CookBook:PDB:atoms "wikilink")
-   [How can I do calculations on
    atoms?](BioJava:CookBook:PDB:atomsCalc "wikilink")
-   [How to work with Groups (AminoAcid, Nucleotide,
    Hetatom)?](BioJava:CookBook:PDB:groups "wikilink")
-   [How can I access the header information of a PDB
    file?](BioJava:CookBook:PDB:header "wikilink")
-   [How does BioJava deal with SEQRES and ATOM
    groups?](BioJava:CookBook:PDB:seqres "wikilink")
-   [How can I mutate a
    residue?](BioJava:CookBook:PDB:mutate "wikilink")
-   [How can I calculate a structure
    alignment?](BioJava:CookBook:PDB:align "wikilink")
-   [How can I use a simple GUI to calculate an
    alignment?](BioJava:CookBook:PDB:alignGUI "wikilink")
-   [How can I interact with
    Jmol?](BioJava:CookBook:PDB:Jmol "wikilink")
-   [How can I serialize to a
    database?](BioJava:CookBook:PDB:hibernate "wikilink")
-   [How can I load data from the SCOP
    classification?](BioJava:CookBook:PDB:SCOP "wikilink")

### biojava3-protmod

**Required modules**: *biojava3-protmod, biojava-structure*

-   [How can I identify protein modifications in a 3D
    struture?](BioJava:CookBook3:ProtMod "wikilink")
