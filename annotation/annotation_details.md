# Annotation Details

Annotation refers to all of the information about a variant, it is made from different components, including:

**Variant-level annotation:** Information specific to a base change. Examples include computational predictions and effects, and existing database entries (such as population frequency for the variant)

**Gene-level annotation:** Information about the gene (from RefSeq/Ensembl + other sources), matched from the variant's assigned transcript_id. 

**ClinVar:** Clinical variant classifications from [ClinVar](https://www.ncbi.nlm.nih.gov/clinvar)

To see a description of each field, use menu: **[annotation] -> [descriptions]** 

Annotation is shown on the [variant details](variant_details.md) page, and in an [analysis](../analysis/analysis_intro.md), where it is used in filters and shown on the grid (see [customise columns](../settings/columns.md))

## Variant Level Annotation

The first time we see a variant, it is annotated by Ensembl [Variant Effect Predictor](https://ensembl.org/info/docs/tools/vep/index.html) (VEP) and then cached in the database. 

To see the VEP fields used, check the "Show Ensembl Variant Effect Predictor source fields" checkbox on the annotation descriptions (**[annotation] -> [descriptions]**) page.  

VEP calculates the effects for each transcripts overlapping a variant, then picks a [representative transcript](representative_transcript.md) - this is what is used for filtering in an [analysis](../analysis/analysis_intro.md) and shown in the grid. 

## Annotation Versions

Each annotation component above is versioned and can be upgraded separately by the site administrator. To see the versions via menu: **[annotation] -> [versions]** 

VariantGrid can store multiple annotation versions, which allows us to load historical analyses which return the same results as when they were first analysed, as well as updating from new sources regularly.  

