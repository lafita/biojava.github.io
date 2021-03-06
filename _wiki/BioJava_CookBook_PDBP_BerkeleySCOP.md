---
title: BioJava:CookBook:PDBP:BerkeleySCOP
permalink: wiki/BioJava%3ACookBook%3APDBP%3ABerkeleySCOP
---

BioJava supports by default the [original SCOP
version](http://scop.mrc-lmb.cam.ac.uk/scop/) from the UK (currently at
version 1.75). As of version 3.0.4 it also allows to work with the newer
(version 1.75A) version of SCOP that is [available from
Berkeley](http://scop.berkeley.edu/).

```java

import org.biojava.nbio.structure.scop.BerkeleyScopInstallation; import
org.biojava.nbio.structure.scop.ScopDatabase; import
org.biojava.nbio.structure.scop.ScopFactory;

/\*\* A demo for how to use the Berkeley version of SCOP instead of the
default UK-SCOP

`* `  
`* @since 3.0.4`  
`*`  
`*/`

public class DemoBerkeleyScop {

`   public static void main(String[]args){`

`       ScopDatabase berkeley = new BerkeleyScopInstallation();`

`       ScopFactory.setScopDatabase(berkeley);`

`       // whenever you want to get access to SCOP now request it like this:`  
`       ScopDatabase scop = ScopFactory.getSCOP();`  
`       // ... and do something with it`

`       // eg. you can run all the demos that work for the UK - SCOP (currently at version 1.75) `  
`       // this demo no automatically picks up the Berkeley version (currently 1.75A)`  
`       DemoSCOP scopDemo = new DemoSCOP();`  
`       `  
`       scopDemo.getCategories();`  
`       scopDemo.printDomainsForPDB();`  
`       scopDemo.traverseHierarchy();`  
`       scopDemo.alignSuperfamily();`

`   }`

}
