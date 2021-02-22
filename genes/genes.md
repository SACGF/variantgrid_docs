# Genes

## Genes and symbols

It is worth separate the concepts of a Gene ID (eg ENSG00000179348) from a symbol (eg GATA2)

Ensembl Genes are versioned, eg the most recent version for GATA2 in GRCh37 is ENSG00000179348.7 and GRCh38 is ENSG00000179348.12

RefSeq genes are numbers without versions.

The symbol assigned to a gene can change over time (annoyingly, this is independent of the gene/transcript version). This is usually noticed across genome builds as the versions are often years apart.  

## RefSeq vs Ensembl

VariantGrid contains both Ensembl and RefSeq genes and transcripts, but a server can only be configured to run variant-level annotation (via VEP) for one.

You can classify against either, but on a server configured to use RefSeq, Ensembl transcripts will not have a molecular consequence or data for auto-population such as splicing calculations.  

You can see what your system uses on the annotation page, by looking at "Gene Annotation Release" 

## Gene Annotation Release

A Gene Annotation Release is a snapshot of Gene IDs/versions and symbols - for instance "Ensembl v87" or "RefSeq v204"

This ensures our combination of symbols/gene+transcript versions match what is used by VEP, while allowing us to import new transcripts into the database (useful for resolving HGVS and interoperability between systems)

Each symbol in a gene list is mapped to a gene version in a Gene Annotation Release, so that filtering remains consistent over time, even if we later import new annotation which alters the symbol for a gene version.

You can see what gene versions and symbols are used by going to the genes page  **[genes] -> [genes]**

## Gene Annotation Grid

The data in the gene annotation grid can be explored using the OMIM quick filters that will filter to genes with corresponding OMIM data. Alternatively, use the search link to access the advanced filter.

Enter a gene symbol in the 'Jump to gene' dropdown or click on the gene symbol in the grid to navigate directly to a gene symbol page.  


