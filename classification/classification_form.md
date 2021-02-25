# Classification Form

The Classification Web Form can be used to create and edit classifications directly within VariantGrid.

### View

![](images/classification_form.png)

To quickly see all fields that have values for a classification, enter "*" into the filter box at the top of the classification.
To see all possible fields, enter "**" in the filter box.
To find an individual field, start typing the label of the field into the filter e.g. "gnomad".

### Identify Errors

A record might not be shared as there are outstanding validation errors. In the Messages box on the form it will list any errors. If possible fix those errors in your curation system and then they should be fixed on the next sync.

### Change History / Diff

Each version of a record published in VariantGrid is recorded, by clicking on "Compare historical versions of this record".

If there are other classifications for the same variant, there will be a link to compare them there too.

### ACMG Guidelines

The classification form has fields for the ACMG Guidelines, e.g. PM4, BA1 - the meaning of each is given in the help.
See [Guidelines](https://www.acmg.net/docs/Standards_Guidelines_for_the_Interpretation_of_Sequence_Variants.pdf)

VariantGrid displays a grid of ACMG fields with each row being a category of data, and each column representing the strength of evidence for benign or pathogenic.
* The number of met criteria for a given box will be shown as a number.
* Explicitly unmet criteria will show as "/"s.
* Criteria not yet marked as met or unmet will show as "?"s.

The various values will be plugged into the ACMG formulae and a recommended overall clinical significance will be displayed.
This calculated value has no affect on any of the data, the user is still able to set the overall clinical significance to whatever (hopefully justifiable) value they like.

### Actions

![](images/classification_form_actions.png)

At the bottom of the form there will be a list of action buttons.


![Tick](images/classification_form_action_button_tick.png) - re-submits the classification at its current change level. For any manual changes to be seen, this button will need to be ticked.

![Share](images/classification_form_action_button_share.png) increases who can see the classification, see [Classification Sharing](classification_sharing.md)

![Delete/Widthdraw](images/classification_form_action_button_delete.png) - Delete an unshared classification, or withdrawal (hide/ignore) a shared one. 

### Export

You can also export the single record as CSV, a preview of the [Clinvar](https://www.ncbi.nlm.nih.gov/clinvar/) format or as a [report](classification_report.md).
(The report does require that your lab has a report template pre-configured.)

### Literature Citations

![](images/classification_form_literature.png)


Any PMID references in the form of PMID:123456 from anywhere within the classification will be summed together and listed at the bottom of the classification.
