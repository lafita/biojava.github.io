---
title: BioJava:CookBook:AAPROP:isoelectricpoint
---

### How is Isoelectric Point computed?

The isoelectric point, pI, is the pH at which the net charge of the
peptide is zero. We first computes the net charge for pH 7.0.  
If the charge is \> 0, the next pH to check is 7 + 3.5.  
If the charge is \< 0 then pH 7 - 3.5 is checked.  
This is repeated, using increments/decrements half the size of the
previous, until the modulus of the charge found is less than or equal to
0.0000001.  
Our approach is derived from
[here](http://www.innovagen.se/custom-peptide-synthesis/peptide-property-calculator/peptide-property-calculator-notes.asp#PI).