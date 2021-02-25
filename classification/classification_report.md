# Classification Report

## Running the report

To generate the report from a classification, open the classification and scroll to the bottom. You will see a button called "Report". Click on it and you will then be able to copy & paste the report contents into a document.

## Configuring the report

The report can only be configured by admin users. Each "organisation" within variantgrid uses its own report. To edit it go to the admin view, Organisations, (your organisation), and then edit the Classification report template.

The template is run using [Django template](https://docs.djangoproject.com/en/3.0/topics/templates/) and produces HTML

## Values available for the report

### Evidence Keys

All the fields in the classification are exposed here, see the Evidence Keys admin for a list of possible values, e.g. zygosity, mechanism_of_disease, mode_of_inheritance.
In addition you can also suffix `_raw` or `_note` e.g.
``` html
The raw value for Mode of Inheritance is {{ mode_of_inheritance_raw }} and the note for it is {{ mode_of_inheritance_note }}
{% if mode_of_inheritance_raw == 'x_linked' %}
Special case for X Linked
{% endif %}
```
Typically you'll only want to refer to the `_raw` value if you're doing some logic for a specific drop down value. If you ommit the `_raw` then you will get the human friendly label for the value which might subtly change in the future.


### p.hgvs

You can reference the full `p_hgvs` or breakdown
``` html
full p.hgvs = {{ p_hgvs }}<br/>
p amino acid from = {{ p_hgvs_aa_from }}<br/>
p hgvs codon = {{ p_hgvs_codon }}<br/>
p hgvs amino acid to = {{ p_hgvs_aa_to }}
```

### c.hgvs

You can reference the full `c_hgvs` or breakdown
``` html
full c.hgvs = {{ c_hgvs }}<br/>
c hgvs transcript = {{ c_hgvs_transcript }} or {{refseq_transcript_id}}<br/>
c hgvs gene symbole = {{ c_hgvs_gene_symbol }} or {{ gene_symbole }}<br/>
c hgvs short = c.{{ c_hgvs_short }} (this is the value in c_hgvs after "c.")
```

### Evidence weights

A summary of the strength of ACMG critieria met can be accessed with
``` html
Evidence weights = {{ evidence_weights }}
```

### Citations

PMIDs put anywhere in the classification can be accessed, and then specific attributes of those citations can be referenced. `citations` is an array that you must loop through, e.g.
``` html
{% for cit in citations %}
	<tr>
		<td>{{ cit.source }}</td>
		<td>{{ cit.citation_id }}</td>
		<td>{{ cit.citation_link }}</td>
		<td>{{ cit.journal }}</td>
		<td>{{ cit.journal_short }}</td>
		<td>{{ cit.title }}</td>
		<td>{{ cit.year }}</td>
		<td>{{ cit.authors }}</td>
		<td>{{ cit.authors_short }}</td>
		<td>{{ cit.abstract }}</td>
	</tr>
{% endfor %}
```
The example here is in a table but you can display it however you'd like, e.g.
```
{% for cit in citations %}
{{ cit.source }}:{{ cit.citation_id }}
{% endfor %}
```
Which would give you PMID:12334 PMID:4555 etc
