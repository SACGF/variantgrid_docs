# VCF / Samples

### Multi-sample VCFs

Multi-sample VCF files combined using bam files record the genotype for all samples at each variant position.

This allows you to differentiate between reference calls and no coverage - and is extremely important for Trios so that you can make correct calls about inheritance and denovo variants

You must use bam files, to re-call the genotypes for each position.

Consider 3 VCF files:

Proband 	Mum 	Dad
HET 	(not present) 	(not present)

There's no way to tell in a VCF if a variant not being present is due to the sample having the reference allele at that position or no coverage.

Merging just the VCFs (without supplying the bams) will give the genotypes of:

Proband 	Mum 	Dad
HET 	./.	./.

If you merge them using GATK/Picard using bam files - the caller will re-examine the reads over the locus, and make the genotype call.

Thus, if both parents had reference bases, the calls would be:

Proband 	Mum 	Dad
0/1 (HET) 	0/0 (HOM_REF)	0/0 (HOM_REF)

And you can be confident that it is a denovo variant, rather than just lacking coverage in one of the parent samples.

