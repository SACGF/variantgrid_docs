# Gene Symbol page

The Gene Symbol shows annotation and internal data for a gene.  

To see details of the genes IDs and transcripts associated with the gene symbol click on the RefSeq and Ensembl links at the top of the page. 

## Gene Annotation

Information on the page is combined from a wide-range of sources as follows:

- Aliases: A list of all gene symbol aliases. A warning is shown if the alias maps to multiple gene IDs.
- Summary: imported from RefSeq (if gene symbol linked to RefSeq gene)
- HGNC: Information derived from the HUGO Gene Nomenclature Committee based on the given gene symbol
- Uniprot: Information derived from the UniProt protein database
- Gene/Disease associations: ClinGen gene-disease assertions. Only available for ClinGen curated genes.
- gnomAD gene constraints: "The observed / expected (oe) number of loss-of-function variants in that gene. This a measure of how tolerant a gene is to loss-of-function. When a gene has a low oe value, it is under stronger selection for that class of variation than a gene with a higher value. For the interpretation of Mendelian diseases cases, we suggest using the upper bound of the oe CI < 0.35 as a threshold if needed. Ideally oe should be used as a continuous value rather than a cutoff and evaluating the oe 90% CI is a must." (extract from gnomAD)
- PanelApp: Gene panels from Geneomics England and Australia PanelApp websites. Note that PanelApp data is updated on a periodic basis. The date of last update is available in the annotations menu. Contact your VariantGrid administrator if a PanelApp update is required.
- Ontology terms: HPO and OMIM terms associated with the gene symbol in VariantGrid. Only displayed when linked term identified.

## Internal gene data

The bottom of the page has 3 grids showing internal data (grids only display when data available) 

- Classifications: Summary table of classifications associated with the gene symbol. Click on the links to access the full classification record.
- Variants: A list of all variants located within the genic locus with a Het or Hom_Alt count >= 1 (this excludes low AF somatic variants), as well as any variant that has been tagged or classified in the database (warning: classified/tagged variants may include somatic variants). Columns in the Gene Variants grid below are based on your User Settings. Change your default column selection to alter the display. To explore the data in the grid click the filter link to display the advanced filter controls. 
- Gene Lists: A table of all user entered gene lists containing the gene symbol.
