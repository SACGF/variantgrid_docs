# Representative Transcript

Variant Ensembl Predictor calculates effects for each transcript.

A single "representative" transcript annotation is chosen (via [VEP pick](https://asia.ensembl.org/info/docs/tools/vep/script/vep_other.html#pick)) - this is what is used in an analysis and shown in the grid. This is chosen via:

1. Canonical status of transcript
2. APPRIS isoform annotation
3. Transcript support level
4. Biotype of transcript ("protein_coding" preferred)
5. CCDS status of transcript
6. consequence rank according to this table
7. Translated, transcript or feature length (longer preferred)
8. MANE transcript status