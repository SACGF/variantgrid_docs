# Annotation Details

Annotation refers to all of the information about a variant, it is made from different components, including:

**Variant-level annotation:** Information specific to a base change. Examples include computational predictions and effects, and existing database entries (such as population frequency for the variant)

**Gene-level annotation:** Information about the gene (from RefSeq/Ensembl + other sources), matched from the variant's assigned transcript_id. 

**ClinVar:** Clinical variant classifications from [ClinVar](https://www.ncbi.nlm.nih.gov/clinvar)

To see a description of each field, use menu: **[annotation] -> [descriptions]** 

Annotation is shown on the [variant details](variant_details.md) page, and in an [analysis](../analysis/analysis_intro.md), where it is used in filters and shown on the grid (see [customise columns](../settings/columns.md))

## Variant Level Annotation

The first time we see a variant, it is annotated by the variant annotation pipeline.

## Annotation Versions

Each annotation component above is versioned and can be upgraded separately by the site administrator. To see the versions via menu: **[annotation] -> [versions]** 

VariantGrid can store multiple annotation versions, which allows us to load historical analyses which return the same results as when they were first analysed, as well as updating from new sources regularly.  

## IVAT

VariantGrid uses IVAT developed by Jinghua (Frank) Feng from the CCB ACRF Cancer genomics facility.

### SACGF Tiers

#### Tier 1
Novel variants, with evidence of being strongly damaging, and without any evidence of being artificial:

* Not in dbSNP, 1KG, UK10K, ExAC or ESP
* HIGH or MODERATE snpEFF impact, or mutating at branch point, at miRNA binding site, or at transcription factor binding site
* For a SNV: GERP > 4 or CADD > 30
* For an INDEL: not in LowComplexRegion
* Not in SegmentDup region
* No multi-ALT alleles were called 

#### Tier 2
Extremely rare variants, with evidence of being strongly damaging, and without any evidence of being artificial:

* Not Tier 1
* Minor allele frequency (MAF) < 0.05% in 1KG, UK10K and ExAC.
* HIGH or MODERATE snpEFF impact, or mutating at branch point, at miRNA binding site, or at transcription factor binding site
* For a SNV: GERP > 3 or CADD > 20
* For an INDEL: not in LowComplexRegion
* Not in SegmentDup region
* No multi-ALT alleles were called 

#### Tier 3
Very rare variants, with evidence of being potentially functional, and without any evidence of being artificial:

* Not Tier 1 or 2
* MAF < 0.2% in 1KG, UK10K and ExAC.
* HIGH, MODERATE or LOW snpEFF impact, or mutating at branch point, at miRNA binding site, or at transcription factor binding site
* For a SNV: GERP > 2 or CADD > 20
* For an INDEL: not in LowComplexRegion
* Not in SegmentDup region
* No multi-ALT alleles were called 

#### Tier 4
Rare variants, with evidence of being potentially damaging. They can locate within the SegmentDup regions, and hence are with increased chance of being artificial:

* Not Tier 1, 2 or 3
* MAF < 0.5% in 1KG, UK10K and ExAC.
* HIGH, MODERATE or LOW snpEFF impact, or mutating at branch point, at miRNA binding site, or at transcription factor binding site
* For a SNV: GERP > 2 or CADD > 20
* For an INDEL: not in LowComplexRegion 

#### Tier 5
Uncommon variants with potential damage effect, and can located in SegmentDup and LowComplexRegion and hence with significantly increased chance of being artificial:

* Not Tier 1, 2, 3 or 4
* MAF < 1% in 1KG, UK10K and ExAC
* Satisfying ***any one** of the three criteria below:
  * Annotated with HIGH, MODERATE or LOW snpEFF impact (aka. altering the exon or splice region)
  * Altering splicing branchpoint, miRNA binding site, or transcription factor binding site
  * GERP > 2 or CADD > 20

#### Tier 6

* Not Tier 1, 2, 3, 4 or 5 

Notes:

A variant is classified as Tier 6, when all your samples are HOM-ALT at the variant and that ALT allele is common in 1KG, UK10K and ExAC (i.e. The frequency of the ALT allele is > 0.5 in anyone of 1KG, UK10K and ExAC). This applies before all the tiering above. From a trio sequenced with the Medical Exome Capture on our NextSeq machine in September 2016, below are the numbers of variants (called by GATK, mostly germline) for each tier:

| Tier | # Variants |
| ---- | -------:|
| 1 | 96 |
| 2 | 233 |
| 3 | 246 |
| 4 | 282 |
| 5 | 3343 |
| 6 | 223008 |