---
title: BioJava:CookBookItaliano:Translation:SixFrames
---

Come posso tradure una sequenza di nucleotidi secondo tutti i sei frame?
------------------------------------------------------------------------

Questo è probabilmente una dele più frequenti applicazioni della
bioinformatica e una delle questioni più postate all'interno della
mailing list.

La traduzione secondo tutti i sei frame è utile per individuare le più
ampie Cornici di lettura aperte (Open Reading Frames) le quali, è noto,
sono redioni codificanti o al limite sono regioni prive di introni. Per
risolvere il problema della traduzione a sei frame basta prendere una
sotto sequenza della sequenza di interesse e invertirla, traslarla o
crearne il complemento in maniera appropriata. L'unico ostacolo che ci
si pone dinnanzi e come scegliere le sottosequenze in maniera tale da
avere regioni ugualmente divisibili per tre.

L'esempio seguente mostra un semplice programma che data una sequenza ne
fa la traduzione secondo tutti i sei frame e il risultato viene
memorizzato in un file e inviato nello STDOUT in formato FASTA.

*Nota Bene:Segui questo
[link](Biojava:CookBookItaliano:Sequence:SubSequence "wikilink") per
scoprire come ottenere una porzione di una Sequenza per poi tradurla*

<java> import java.io.BufferedReader; import java.io.FileReader;

import org.biojava.bio.Annotation; import org.biojava.bio.seq.DNATools;
import org.biojava.bio.seq.RNATools; import
org.biojava.bio.seq.Sequence; import
org.biojava.bio.seq.SequenceIterator; import
org.biojava.bio.seq.SequenceTools; import
org.biojava.bio.seq.io.SeqIOTools; import
org.biojava.bio.symbol.SymbolList;

/\*\*

`* `

Program to six-frame translate a nucleotide sequence

`*/`

public class Hex {

` /**`  
`  * Call this to get usage info, program terminates after call.`  
`  */`  
` public static void help() {`  
`   System.out.println(`  
`       "usage: java Hex `<file>` `<format eg fasta>` `<dna|rna>`");`  
`   System.exit( -1);`  
` }`

` public static void main(String[] args) throws Exception{`  
`   if (args.length != 3) {`  
`     help();`  
`   }`

`   BufferedReader br = null;`  
`   `  
`   //file format (eg fasta)`  
`   String format = args[1];`  
`   `  
`   //sequence type (eg dna)`  
`   String alpha = args[2];`

`   try {`  
`     br = new BufferedReader(new FileReader(args[0]));`

`     SequenceIterator seqi =`  
`         (SequenceIterator)SeqIOTools.fileToBiojava(format, alpha, br);`

`     //for each sequence`  
`     while(seqi.hasNext()){`  
`       Sequence seq = seqi.nextSequence();`

`       //for each frame`  
`       for (int i = 0; i < 3; i++) {`  
`         SymbolList prot;`  
`         Sequence trans;`

`         //take the reading frame`  
`         SymbolList syms = seq.subList(`  
`               i+1,`  
`               seq.length() - (seq.length() - i)%3);`

`         //if it is DNA transcribe it to RNA`  
`         if(syms.getAlphabet() == DNATools.getDNA()){`  
`           //before BJ1.4 use this method`  
`       syms = RNATools.transcribe(syms);`  
`       //after BJ1.4 use this method`  
`       syms = DNATools.toRNA(syms);`  
`         }`

`         //output forward translation to STDOUT`  
`         prot = RNATools.translate(syms);`  
`         trans = SequenceTools.createSequence(prot, "",`  
`                                              seq.getName()+`  
`                                              "TranslationFrame: +"+i,`  
`                                              Annotation.EMPTY_ANNOTATION);`  
`         SeqIOTools.writeFasta(System.out, trans);`

`         //output reverse frame translation to STDOUT`  
`         syms = RNATools.reverseComplement(syms);`  
`         prot = RNATools.translate(syms);`  
`         trans = SequenceTools.createSequence(prot, "",`  
`                                              seq.getName() +`  
`                                              " TranslationFrame: -" + i,`  
`                                              Annotation.EMPTY_ANNOTATION);`  
`         SeqIOTools.writeFasta(System.out, trans);`  
`       }`  
`     }`  
`   }`  
`   finally {`  
`     //tidy up`  
`     if(br != null){`  
`       br.close();`  
`     }`  
`   }`  
` }`

} </java>