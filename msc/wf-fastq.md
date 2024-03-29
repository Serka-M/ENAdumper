### Uploading FastQ sequencing read data to ENA using ENAdumper

#### Prerequisites
1. Register a [Webin account](https://ena-docs.readthedocs.io/en/latest/submit/general-guide/registration.html) at ENA for submitting files
2. Register a [study](https://ena-docs.readthedocs.io/en/latest/submit/study.html) at ENA and get a study ID
3. Register your [samples](https://ena-docs.readthedocs.io/en/latest/submit/samples.html) to acquire the sample sheet from ENA
4. The sample sheet will act as a key-file linking the sample names to the corresponding ENA sample IDs. Example below:

| TYPE | ACCESSION | ALIAS |
| --- | --- | --- |
| SAMPLE | ERS00000001 | S1 |
| SAMPLE | ERS00000002 | S2 |
| SAMPLE | ERS00000003 | S3 |
| SAMPLE | ERS00000004 | S4 |
| SAMPLE | ERS00000005 | S5 |
| SAMPLE | ERS00000006 | S6 |

#### Running the ENAdumper workflow
1. The workflow assumes that the FastQ datasets have already been compressed to save storage space
2. The main input is a tsv file containing the paths and sample names of the compressed FastQ files. Example below:

| FILEPATH | ALIAS |
| --- | --- |
| /path/to/reads/S1.fastq.gz | S1 |
| /path/to/reads/S2.fastq.gz | |
| /path/to/reads/S3.fastq.gz | |
| /path/to/reads/S4.fastq.gz | S4 |
| /path/to/reads/S5.fastq.gz | |
| /path/to/reads/S6.fastq.gz | S6 |

3. If the sample name is not provided, the basename of the read file will be used instead.
4. Example command for uploading FastQ data with ENAdumper: <br/>
`ENAdumper --fastq_list list.tsv --key sample_sheet.tsv --study PRJEB00001 -n BATCH1 -user Webin-0001 -pass Banana1`
5. ENAdumper will upload FastQ files in parallel, which can be set using the `--processes` option
6. After upload is complete, a template spreadsheet will be generated that can be [submitted](https://ena-docs.readthedocs.io/en/latest/submit/reads/interactive.html#step-3-submit-the-template-spreadsheet) to include the files in the permanent archive
7. It is highly recommended to double-check the template spreadsheet before submitting it to ENA

[//]: # (Written by Mantas Sereika)
