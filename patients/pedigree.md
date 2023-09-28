# Pedigree

Menu: **[patient] -> [pedigree]**

Pedigrees describe family relationships, and marks samples as "affected/unaffected"

This and can be used to filter for inheritance models (eg recessive/dominant) in an analyis.

For the common case of 3 samples, perhaps use a [Trio](trios.md)

To create a pedigree

* Create a [.ped file](http://www.helsinki.fi/~tsjuntun/autogscan/pedigreefile.html) for your family, eg using the [Phenotipes editor](https://phenotips.org/UserGuide/PedigreeEditor)
* Upload the .ped file to VariantGrid
* Match the ped file family and cohort samples to create a Pedigree
* Use an analysis [PedigreeNode](../analysis/nodes.md) to apply inheritance models