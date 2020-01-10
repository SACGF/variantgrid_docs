# VCF / Samples

### VCF import

Variants are normalized (see below) upon import. We only import variants, filters and genotypes (we don't use INFO as we do our own annotations)

The VCF format can vary a lot, we have tested VCFs from the following variant callers:   

* GATK
* FreeBayes

Each sample is assigned a "variants type" of _Unknown_, _Germline_, _Mixed_ (single sample) or _Somatic only_ (tumor minus normal).

This is determined by looking at the "source" entry in the VCF header, and matching it to an entry in **VCFSource** object (setup by your administrator)

Samples with variants type of_somatic only_  are checked for [mutational signatures](mutational_signatures.md)  

### Multi-sample VCFs

Multi-sample VCF files combined using bam files record the genotype for all samples at each variant position.

This allows you to differentiate between reference calls and no coverage - and is extremely important for Trios so that you can make correct calls about inheritance and denovo variants

You must use bam files, to re-call the genotypes for each position.

Consider 3 VCF files:

| Proband | Mum | Dad |
| ------- |:---:| ---:|
| HET | (not present) | (not present) |

There's no way to tell if a variant not being present in a single sample VCF is due to having the reference allele or no coverage.

Merging just the VCFs (without supplying the bams) will give the genotypes of:

| Proband | Mum | Dad |
| ------- |:---:| ---:|
| HET | ./. | ./. |

If you merge them using [GATK](https://software.broadinstitute.org/gatk/)/[Picard](https://broadinstitute.github.io/picard/) using bam files - the caller will re-examine the reads over the locus, and make the genotype call.

Thus, if both parents had reference bases, the calls would be:

| Proband | Mum | Dad |
| ------- |:---:| ---:|
| 0/1 (HET) | 0/0 (HOM_REF) | 0/0 (HOM_REF) |

And you can be confident that it is a denovo variant, rather than just lacking coverage in one of the parent samples.

### VCF Normalization

We [Decompose and Normalise variants using VT](https://genome.sph.umich.edu/wiki/Vt#Normalization) during import, so variants from different VCF files have a consistent representation.

If any variants were altered during an import, a warning appears on the VCF and Sample pages, allowing you to examine the changes. 

You can [search](search.md) on an unnormalized variant, and it will take you to the normalized [variant's details page](../annotation/variant_details.md).
This page lists all VCF records normalized to that variant coordinate.
