# Epigenomics 01
From Professor Chongzhi Zang's lecture slides "Regulatory DNA, Transcription factors, Sequence motifs". Scribed by Zhaoxia Ma.
## Epigenome
Different cells with similar genome sequences have different genes expression. The epigenome can control gene activities to decide which genes are turned on or off.

*The epigenome is a multitude of chemical compounds that can tell the genome what to do. The epigenome is made up of chemical compounds and proteins that can attach to DNA and direct such actions as turning genes on or off, controlling the production of proteins in particular cells.          <p align="right">--from genome.gov</p>*

## Epigenomic marks

| |Chemical compounds |Proteins |Other molecules <th rowspan=1>Other information</th>
|---|---|---|---
|DNA-associated|DNA methylation|Histones;<br> DNA-binding proteins<br> (transcription factors*)|RNA<br>(e.g., R loops)<td rowspan=2> -nucleosome positioning;<br> - chromatin accessibility;<br> - 3D genome organization</td>
|Chromatin-associated|Histone modifications: methylations, acetylations, ... |Histone variants;<br> Chromatin regulators;<br> Histone modifying enzymes: writer, readers, erasers;<br> Chromatin remodeling complexes|Non-coding RNAs

## Epigenomics
### Transcription factors
- The transcription factors (TF) is one of the most important group of proteins which can directly interact with DNA. In this case, the DNA region should be open/accessible to proteins.
- The transcription factors should have DNA-binding domains which are used to recognize specific DNA sequences and sites. They also have effector domains which can regulate TF activity, such as ligand binding domains, can mediate protein-protein interactions, such as BTB domain, and can have enzymatic activities, such as SET domain.
- There are some functional studies related to transcription factors, such as studying for the cell-type specific gene expression, binding DNA sequence motif, genome-wide binding sites, target genes, TF co-factors, etc. 

### Sequence motif
In general, a motif is a distinctive pattern that occurs repeatedly. In biomelecular studies, a sequence motif is a pattern common to a set of DNA, RNA, or protein sequences that share a common biological property, such as functioning as binding sites for a particular protein.
#### Sequence motif finding
For motif finding, the input data is a set of DNA sequences and the output is enriched sequence patterns (motifs).
- Motif representation
  
  Single-letter and ambiguity codes for nucleotides (Table)

|Symbol|Meaning|Origin of designation|
|---|---|---|
|G|G|**G**uanine|
|A|A|**A**denine|
|T|T|**T**hymine|
|C|C|**C**ytosine|
|R|G or A|pu***R***ine|
|Y|T or C|p**Y**rimidine|
|M|A or C|a**M**ino|
|K|G or T|**K**eto|
|S|G or C|**S**trong interaction (3H bonds)|
|W|A or T|**W**eak interaction (2H bonds)|
|H|A or C or T|not-G, H follows G in the alphabet|
|B|G or T or C|not-A, B follows A|
|V|G or C or A|not-T (not-U), V follows U|
|D|G or A or T|not-C, D follows C|
|N|G or A or T or C|a**N**y|

It is derived by IUPAC. one limitation is that they can not measure continue relation/difference because it is binary decision.

- Entropy

    Entropy is used to measure the orderliness. 
    
    Boltzmann entropy: $S_B=-k_B\sum\limits_ip_i\ln(p_i)$
    
    Shannon entropy: $H(X)=-\sum\limits_iP(x_i)\log_2P(x_i)$


- Position weight matrix
    
    Here are some DNA sequences. The first line is the position: 
    \begin{matrix}1&2&3&4&5&6&7&8&9\\\\
    G&A&G&G&T&A&A&A&C\\\\
    T&C&C&G&T&A&A&G&T\\\\
    C&A&G&G&T&T&G&G&A\\\\
    A&C&A&G&T&C&A&G&T\\\\
    T&A&G&G&T&C&A&T&T\\\\
    T&A&G&G&T&A&C&T&G\\\\
    A&T&G&G&T&A&A&C&T\\\\
    C&A&G&G&T&A&T&A&C\\\\
    T&G&T&G&T&G&A&G&T\\\\
    A&A&G&G&T&A&A&G&T
    \end{matrix}
    
    In each position, we count the number of A, C, G, and T, respectively. Then we get the corresponding position frequency matrix (PFM):
    $$M=\begin{matrix}
    A\\\\
    C\\\\
    G\\\\
    T
    \end{matrix}\begin{bmatrix}
    3&6&1&0&0&6&7&2&1\\\\
    2&2&1&0&0&2&1&1&2\\\\
    1&1&7&10&0&1&1&5&1\\\\
    4&1&1&0&10&1&1&2&6
    \end{bmatrix}$$
    
    Then we simply do a normalization. Each number is divided by the total number of sequences. The corresponding position probability matrix (PPM) is:
    $$M=\begin{matrix}
    A\\\\
    C\\\\
    G\\\\
    T
    \end{matrix}\begin{bmatrix}
    0.3&0.6&0.1&0.0&0.0&0.6&0.7&0.2&0.1\\\\
    0.2&0.2&0.1&0.0&0.0&0.2&0.1&0.1&0.2\\\\
    0.1&0.1&0.7&1.0&0.0&0.1&0.1&0.5&0.1\\\\
    0.4&0.1&0.1&0.0&1.0&0.1&0.1&0.2&0.6
    \end{bmatrix}$$
    
- Graphic representation: sequence logo
![sequence logo source:[myhub](https://github.com/mzxj/scribe/blob/main/figs/motif_eg.PNG)](figs/motif_eg.PNG)
![sequence logo](https://github.com/mzxj/scribe/blob/main/figs/motif_eg.PNG)