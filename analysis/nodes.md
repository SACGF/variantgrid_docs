# Analysis Nodes

## Source Nodes

Provide a source of variants

### All Variants

![](images/nodes/node_all_variants.png "All Variants")

All variants in the database.

### Cohort

![](images/nodes/node_cohort.png "Cohort")

A collection of related samples, eg "control group" or "poor responders"

### Classifications

![](images/nodes/node_classifications.png "Classifications")


### Pedigree

![](images/nodes/node_pedigree.png "Pedigree")

Variants from family samples filtered by genotype according to inheritance models

### Sample

![](images/nodes/node_sample.png "Sample")

A sample, usually one genotype (patient, cell or organism) with a set of variants.

### Trio

![](images/nodes/node_trio.png "Trio")

Mother/Father/Proband - filter for recessive/dominant/denovo inheritance

## Filter Nodes

These nodes filter variants connected to the top of them

### Built In Filter

![](images/nodes/node_built_in_filter.png "Built in Filter")

Built in filters used in node counts eg High or Moderate Impact / OMIM / ClinVar Pathological

### Damage

![](images/nodes/node_damage.png "Damage")

Filter to damage predictions

### Filter

![](images/nodes/node_filter.png "Filter")

Filter based on column values

### Gene List

![](images/nodes/node_gene_list.png "Gene List")

Filter to a list of gene symbols

### Intervals Intersection

![](images/nodes/node_intervals_intersection.png "Intervals Intersection")

Filter based on intersection with genomic ranges (eg .bed files)

### Merge

![](images/nodes/node_merge.png "Merge")

Merge variants from multiple sources

### Phenotype

![](images/nodes/node_phenotype.png "Phenotype")

Filter to gene lists based on ontology keywords

### Population

![](images/nodes/node_population.png "Population")

Filter on population frequencies in public databases (gnomAD/Exac/1KG/UK10K) or number of samples in this database.

![](images/node_editors/population_node_gnomad_population.png)

### Tags

![](images/nodes/node_tags.png "Tags")

Filter variants to those that have been [tagged](tagging.md)

### Tissue Expression

![](images/nodes/node_tissue.png "Tissue Expression")

Filter based on tissue specific expression (from Human Protein Atlas)

### Venn

![](images/nodes/node_venn.png "Venn")

A filter based on set intersections between parent nodes

### Zygosity

![](images/nodes/node_zygosity.png "Zygosity")

Compound HET and other Zygosity filters

