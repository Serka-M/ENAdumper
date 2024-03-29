<p align="center">
<img align="center" width="250" height="250" src="msc/enadumper_logo.png" alt="logo" style="zoom:100%;" />
</p>
Snakemake workflow for high-throughput upload of sequencing data to the European Nucleotide Archive (ENA)<br/><br/>

**Guides for ENAdumper workflows:**
* [Fast5/Pod5](msc/wf-fast5.md)
* [FastQ](msc/wf-fastq.md)
<br/>

**Installation:** <br/>
It is recommended to use ENAdumper with a Conda environment
```
git clone https://github.com/Serka-M/ENAdumper
conda env create -f ENAdumper/src/conda.yaml -p ./ENAdumper/ENAdumper_env
cp ENAdumper/src/* ENAdumper/ENAdumper_env/bin/.
chmod +x ENAdumper/ENAdumper_env/bin/ENAdumper
```
<br/>

**Quick-start:** 
```
source activate ENAdumper/ENAdumper_env
ENAdumper --help
```
<br/>

**Full usage:**
```
COMPRESSION INPUTS:
-fq		--fastq_dir			Path to directory with FastQ files 
-np		--nanopore_dir			Path to directory with raw Nanopore files
-n		--sample			Sample name 
-p		--processes			Number of processes and batch count
-x		--extension			Filename extension for raw Nanopore data (default:pod5)
 
UPLOAD INPUTS:
-user		--webin_user			Webin username 
-pass		--webin_pass			Webin password 
 
ENA METADATA INPUTS:
-k		--key				Key file with sample names and ENA sample IDs 
-s		--study				ENA study ID 
-ins		--instrument_model		Instrument model category
-lib_n		--library_name			Prefix to be used with sample name for Library name category
-lib_src	--library_source		Library source category
-lib_sel	--library_selection		Library selection category
-lib_strat	--library_strategy		Library strategy category
-lib_lay	--library_layout		Library layout category

EXTRA INPUTS:
-h		--help				Print help information
-v		--version			Print version number
```
<br/>

**Compatibility:** <br/>
ENAdumper has been developed and tested on x86_64 GNU/Linux, Ubuntu 20.04

[//]: # (Written by Mantas Sereika)
