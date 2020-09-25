# Analysis - templates

Menu: **[Analysis]** -> **[Templates]**

## Overview

Analysis templates are used to automatically run similar [analyses](analysis_intro.md) lots of time over different data.

When creating a new analysis from a template, some node fields are set from external data (eg SampleNode’s “sample” is set to your Sample). These are called Analysis Variables. The screenshot below shows an analysis template, nodes colored orange contain analysis variables, which also appear in the top bar.

![Analysis Template screenshot](images/analysis_templates/analysis_templates.png)

Green nodes are “Output nodes” - which means they are expected to have small enough results that a human will want to examine them.

## Running Analysis templates

VariantGrid comes with a number of pre-configured analyses templates - all of which can be configured and modified.

You can create analyses from templates in the "Analysis" section at the bottom of Sample, VCF, Cohort, Trio and Pedigree pages.

Only templates with analysis variables that can be set by data on that page are shown (eg it must only have analysis variables of type Trio for it to show on the trio page)

On the sample page there is a "variants" tab, which automatically runs a template (similar to above screenshot) for that sample, and allows you to switch between the output nodes.

Analyses created via template have a "Template Run" tab in analysis settings, where you can see how the Analysis Varables were set.

## Creating Analysis Templates

* Create a new (blank) template from the Analysis templates page
* Copy an existing analysis. **[Analysis settings]** (cog icon) -> **[Create Template]** tab -> **[Create Template from this analysis]** button.

To save a template, click the **[Save version]** button on the top bar. Templates must be saved before they can be used.

### Analysis Variables

Open a node, then in the node editor click the orange button next to a field to make it an analysis variable. This will make the widget unselectable, and add the field to the top bar.

To remove an analysis variable, click on the field in the top bar.

### Output Nodes

Open a node, then click the **[doc]** tab. Make sure the node has a good, unique name then select the **[output node]** check box and save. This will turn the node green.

### Handling configuration failure

Sometimes parts of an analysis may not make sense depending on the input data. For instance in Trios, whether the parents are affected determines whether you want to use Dominant or X-linked inheritance model filters.

When an analysis is run, nodes run internal checks to make sure they are configured correctly, so for instance a TrioNode configured to "Dominant" on a trio with unaffected parents will be invalid (node and all descendants will error + flash red) 

So to handle this, build all the filters in the template, then for nodes that you expect to sometimes error out due to configuration, go to the Node Editor **[Doc]** tab -> **[Hide node and descendants upon template configuration error]**

![Analysis Template for Trio inheritance - in the template 2 filters overlap, but in the generated analysis only 1 will be shown](images/analysis_templates/analysis_templates_trio.png)

### Tips and tricks

* In the Trio inheritance screenshot above, note the top right node is a TrioNode configured to "Proband HET". If you were building this analysis by hand, you might use a HET SampleNode, however this would then require you to have an anaylsis variable of type "Sample" (which we'd be unable to set via the Trio page)   
* Node editors hide options based on data (eg GeneListNode will not allow you to select "sample gene list" if samples do not have one) so configure the template using data that is as similar as possible to what you intend to use.

### Configuring where templates are shown

You can further configure how/where templates are shown (currently admin only)

* appears_in_autocomplete (default=True)
* appears_in_links (default=False)
* requires_sample_somatic (default=False)
* requires_sample_gene_list (default=False)
