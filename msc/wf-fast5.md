### Uploading raw Nanopore data to ENA using ENAdumper

#### Prerequisites
1. Register a [study](https://ena-docs.readthedocs.io/en/latest/submit/study.html) at ENA and get a study ID
2. Register your [samples](https://ena-docs.readthedocs.io/en/latest/submit/samples.html) to acquire the sample sheet from ENA
3. The sample sheet will act as a key-file linking the sample names to the corresponding ENA sample IDs. Example below:

| TYPE | ACCESSION | ALIAS |
| --- | --- | --- |
| SAMPLE | ERS00000001 | sample_1 |
| SAMPLE | ERS00000002 | sample_2 |
| SAMPLE | ERS00000003 | sample_3 |
| SAMPLE | ERS00000004 | sample_4 |
| SAMPLE | ERS00000005 | sample_5 |
| SAMPLE | ERS00000006 | sample_6 |

#### Running the ENAdumper workflow
