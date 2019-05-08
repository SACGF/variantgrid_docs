# Gene Coverage

Gene Coverage refers to how well a gene was covered by high throughput sequencing reads. This is useful to know how confident you can be about a lack of variant calls in a region.

Having gene coverage associated with a VCF sample allows you to be warned in an [analysis](../analysis/analysis_intro.md) when a gene in a gene list is below a threshold (default: 20x) and you may be missing some variants. The node will flash yellow, and the "genes" tab will be highlighted yellow so you can view which genes have low coverage.

Boxplots of sample coverage for genes are on the [gene page](gene_page.md)

## Canonical Transcripts

Many genes have multiple transcripts, but people want only one value for each gene. 

This is achieved by choosing a single (representative or canonical) transcript, and use that transcripts value for the gene.

A CanonicalTranscriptCollection is a list of gene:transcript mappings imported into the system. The administrator can import different collections, linking them to EnrichmentKits and setting a system default.

## Sample QC metrics

You can [upload](../data/upload.md) gene coverage files (.txt files) which use the system default canonical transcripts. You can then associate them with a [sample from a VCF](../data/vcf_samples.md)

Sample QC coverage loaded via [sequencing features](../sequencing/sequencing_runs.md) - and automatically choose transcripts based on EnrichmentKit

## GeneGrid EnrichmentKit coverage

The per-gene QC metrics for an EnrichmentKit on the GeneGrid page are from [Gold Standard Runs](../sequencing/gold_standard_runs.md), using the canonical transcripts for that EnrichmentKit.

