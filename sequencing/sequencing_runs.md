# Sequencing Runs

When VariantGrid has access to a network drive (eg a diagnostic lab intranet) it can scan disks for sequencing runs to collect QC metrics, gene coverage and automatically load VCFs.

![Sequencing Samples over time](images/sequencing_samples.png)

![Automatically loaded sequencing runs + VCFs](images/sequencing_runs.png)

![A Sequencing Run](images/sequencing_run_qc.png)

We collect Sequencing QC metrics and display them with interactive graphs. Collecting data over time allows us to see how this run compares to other runs over time (or vs _gold standard runs_).

## Gold Standard Runs

The administrator can mark a [sequencing run](sequencing_runs.md) as "Gold Standard" - which means it has passed validation / is of sufficient quality to be used as a benchmark for other runs.

Gold standard runs have an icon (![](images/gold-medal.png)) on the sequencing run grid.

Gold runs for an enrichment kit are used:

* In boxplots on QC metrics pages for a [sequencing run](sequencing_runs.md) or other sample QC graphs.   
* To calculate average [gene coverage](../genes/gene_coverage.md) on the [GeneGrid](../genes/genegrid.md) page. 

## Finding sequencing data

Sequencing Runs are found by searching for the file 'RTAComplete.txt' on the server disks. You can ignore flow cells by putting a file ".variantgrid_skip_flowcell" in the directory. 

## Triggering a manual scan

Administrators, or users who have been give the permission "SeqAuto scan initiate" can 

Menu: **[sequencing]**, then **manage disk scans** link, then click the button **Scan Disk for Sequencing Data**

