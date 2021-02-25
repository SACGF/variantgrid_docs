# Relatedness

Relatedness and ancestry is calculated using [Somalier](https://github.com/brentp/somalier) by Brent Pedersen + team from the Quinlan Lab, University of Utah ([Paper](https://doi.org/10.1186/s13073-020-00761-2))

When a VCF is first uploaded, Somalier records each sample's genotype calls at ~18k unlinked coding sequence sites with ~0.5 allele frequency. 

With every new VCF uploaded, Somalier compare all samples against each other to generate pair-wise [relatedness cooefficient](https://en.wikipedia.org/wiki/Coefficient_of_relationship) scores.

### VCF relatedness

Somalier generates a relatedness report which can be viewed in the **relate** tab on the VCF page ([example report](https://brentp.github.io/somalier/ex.html))

This shows a graph of samples relationships in the VCF. Sample to sample relatedness (ISBO vs ISB2) is plotted on the left. Related samples will locate in the top left and unrelated samples in the bottom right of the graph. Hover over a datapoint to see details of the pair-wise comparison.  The Sample Depth Metrics plot on the right is used to display QC results. 4 commonly used visualisations are provided as quicklinks at the bottom of the graphs. 

### Sample relatedness

Samples with a minimum of 1000 shared HET, 1000 shared HOM and relatedness cooefficient >= 0.2 are displayed as a list at the bottom of the sample page.

Column Descriptions:

| Column  |  Description |
|---------|-------------:|
| Relatedness | [relatedness coefficient](https://en.wikipedia.org/wiki/Coefficient_of_relationship) |
| IBS0 | # sites where one sample is hom-ref and another is hom-alt |
| IBS2 | # sites where the samples have the same genotype |
| hom_concordance | not defined |
| hets_a | # sites where sample a is heterozygotes |
| hets_b | # sites where sample b is heterozygotes |
| hets_ab | # sites where sample a or b are heterozygotes |
| shared-hets | # sites where both samples are heterozygotes |
| shared-hom-alts | # sites that are heterzygous in both samples |
| hom_alts_a | # sites where sample a is homozygous alternate |
| hom_alts_b | # sites where sample b is homozygous alternate |
| shared_hom_alts | # sites that are homozygous alternate in both samples |
| N  | total sites |
| x_ibs0 | IBS0 on chrX |
| x_ibs2 | IBS2 on chrX |

Interpreting relatedness: 

* 1.00  = Identical twins/Clones/Duplicate sample
* 0.50  = Parent/Child/Full Sibling/Parent's Identical twin/Identical twin's child
* 0.35  = 3/4 sibling (e.g. same mother, fathers are siblings)
* 0.25  = Grandparent/Grandchild/Half-sibling/Uncle/Aunt/Niece/Nephew/Double-1st Cousin
* <0.20 = Distant relative (cousins) / Not related

# Ancestry

Somalier creates an ancestry report which can be viewed on the **ancestry** tab of the VCF page [example report](https://brentp.github.io/somalier/ex.somalier-ancestry.html)). This feature is currently "experimental"

Samples are displayed on a PCA plot with individuals from the 1000 genomes project, which have labelled ancestries.

Somalier makes an ancestry prediction by comparing a sample with clusters from data with labelled ancestries. The reported ancestry is the primary one and does not include admixture. 

### Implementation details

The amount of sites used will depend on a Sample's capture regions and sequencing depth (default min of 7). At least 1000 informative sites are required for robust calculation of the relatedness coefficient.

You can view how many sites Somalier used from a sample by going to the **ancestry** tab on the view sample page (under "Extract")

If a large number of unexpected samples are displayed as related, confirm the sample data type is an accepted input and that the sample has passed QC. 

Comparisons work across genome builds and tissue types and can be used to compare RNA-seq, WES, bisulfite and WGS data.

Accepted samples:

* Multi-sample vcf: Ideal input
* Single sample vcf: Missing variants are assumed homozygous for reference allele. 
* Tumour-normal vcf: Not recommended as no common sites due to germline subtraction

