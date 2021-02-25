# Somalier

Somalier is used to rapidly evaluate relatedness between samples using the vcf data submitted to VariantGrid. Somalier works across tissue types and can be used to compare RNA-seq, WES, bisulfite and WGS data.

This tool is available thanks to Brent Pedersen and team at the Quinlan Lab, University of Utah. See Pedersen, B.S., Bhetariya, P.J., Brown, J. et al. Somalier: rapid relatedness estimation for cancer and germline studies using efficient genome sketches. Genome Med 12, 62 (2020). https://doi.org/10.1186/s13073-020-00761-2 for further details.
 
Technical details are available in the Somalier github repository https://github.com/brentp/somalier

## Method

To detect relatedness Somalier uses a set of 17,766 informative coding sequence sites to build a sketch file of the allele counts of each sample. Somalier can then calculate the site genotype and compare these sketch files across thousands of samples to rapidly generate relatedness data. These sites are high-quality and unlinked with a population allele frequency ~0.5. They are located in coding regions and exclude cytosines to enable use of Somalier on RNA-seq and bisulfite sequencing data. Somalier informative sites also include sex chromosomes to faciliate a sex check, however, only autosomal sites are used for relatedness calculations. 

In addition to relatedness, Somalier can also assess sample ancestry (experimental).  


## VariantGrid Implementation:

* VariantGrid uses Somalier under an MIT licence.
* Version: see **[Annotation]** menu for current details of the current Somalier installation.
* Informative sites: VariantGrid uses the default sites for GRCh37 and GRCh38 as provided by Somalier.
* Minimum allele depth: 7 (default recommendation)


Accepted samples:
* Multi-sample vcf: Ideal input
* Single sample vcf: Missing variants are assumed homozygous for reference allele. 
* Tumour-normal vcf: Not recommended, data are unreliable
* WGS: not tested
* RNA-seq data: not yet implemented in VariantGrid

Note Somalier is not optimised for use with samples called on the Freebayes somatic pipeline.


## Interpreting Somalier Output:
Somalier is used to calculate a pair-wise [relatedness cooefficient](https://en.wikipedia.org/wiki/Coefficient_of_relationship) between all samples in the VariantGrid database. Samples with a relatedness cooefficient > X are displayed as a list at the bottom of the sample page in a relatedness table.

Column Descriptions:
* Relatedness -- relatedness coefficient as described [here](https://en.wikipedia.org/wiki/Coefficient_of_relationship) 
* IBS0 -- the number of sites where one sample is hom-ref and another is hom-alt
* IBS2 -- the number of sites where the samples have the same genotype
* hom_concordance --  not defined
* hets_a	-- the number of sites where sample a is heterozygotes
* hets_b	-- the number of sites where sample b is heterozygotes
* hets_ab -- the number of sites where sample a or b are heterozygotes
* shared-hets -- the number of sites where both samples are heterozygotes
* shared-hom-alts -- the number of sites that are heterzygous in both samples
* hom_alts_a -- the number of sites where sample a is homozygous alternate
* hom_alts_b -- the number of sites where sample b is homozygous alternate
* shared_hom_alts -- the number of sites that are homozygous alternate in both samples
* N -- not defined
* x_ibs0 -- not defined
* x_ibs2 -- not defined


Interpreting relatedness: 
* 1.00  = Identical twins/Clones/Duplicate sample
* 0.50  = Parent/Child/Full Sibling/Parent's Identical twin/Identical twin's child
* 0.35  = 3/4 sibling (e.g. same mother, fathers are siblings)
* 0.25  = Grandparent/Grandchild/Half-sibling/Uncle/Aunt/Niece/Nephew/Double-1st Cousin
* <0.20 = Distant relative/Not related

At least 1000 informative sites are required for robust calculation of the relatedness coefficient. If a large number of unexpected samples are displayed as related, confirm the sample data type is an accepted input and that the sample has passed QC. 


### Ancestry

Ancestry data is provided on the Ancestry tab as a summary table of predicted probabilites. Be aware that Somalier ancestry is experimental and may change in the future. 

### vcf visualisations

The Somalier data is also available as a summary for each vcf on the vcf page. 

Click on the relate tab to see graphical representations of the relationship data for samples in the same vcf. Sample to sample relatedness (ISBO vs ISB2) is plotted on the left. Related samples will locate in the top left and unrelated samples in the bottom right of the graph. Hover over a datapoint to see details of the pair-wise comparison.  The Sample Depth Metrics plot on the right is used to display QC results. 4 commonly used visualisations are provided as quicklinks at the bottom of the graphs. 
See the Somalier [examples](https://brentp.github.io/somalier/ex.html) to explore how data cluster on these graphs.  

An analysis of whole-vcf ancestry can be visualised using the Principal component analysis (PCA) plots on the ancestry tab. 

