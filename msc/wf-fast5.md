### Uploading raw Nanopore data to ENA using ENAdumper

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
1. Given the typical size of a usual Fast5 dataset, ENAdumper processes and uploads one sample at a time
2. The main input is a path to a directory containing Fast5 files that the user wants to upload
3. Example command for uploading Fast5 data with ENAdumper: <br/>
`ENAdumper --fast5_dir /path/to/fast5 --key sample_sheet.tsv --sample S1 --study PRJEB00001 -user Webin-0001 -pass Banana1`
4. ENAdumper will split and compress the Fast5 files into multiple batches, which can be set using the `--processes` option
5. After upload is complete, a template spreadsheet will be generated that can be [submitted](https://ena-docs.readthedocs.io/en/latest/submit/reads/interactive.html#step-3-submit-the-template-spreadsheet) to include the files in the permanent archive
6. It is highly recommended to double-check the template spreadsheet before submitting it to ENA

[//]: # (Written by Mantas Sereika)
