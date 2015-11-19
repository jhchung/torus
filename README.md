# TORUS - QTL Discovery utilizing Genomic Annotations 


``torus`` is a free software package that implements a computational procedure for discovering molecular QTLs incorporating genomic annotations. 


## Compilation

The following C/C++ libraries are required for compiling the source code

* GNU GSL library
* Zlib library
* Boost C++ library


## Command line options

### 1. Required input files

* ``-d data_file``: the data_file should be compressed in gzip format and  contain summary statistics from single SNP association analysis. Currently, two formats are supported: 1) gzipped MatrixEQTL output single SNP association result;
2) pre-computed Bayes factors based on single SNP association tests. If 2) is used, it is important to specific ``--load_bf`` in the command line.



### 2. Optional input files

* ``-smap snp_map``: gzipped SNP position files
* ``-gmap gene_map``: gzipped Gene position (transcription start site) file
With both files specified, torus will control for SNP distance to transcript start site (TSS)


### 3. Task options


* ``-est``: output the estimates of enrichment parameters and their confidence intervals
* ``-qtl``: perform Bayesian FDR control, and output the result
* ``-dump_prior``: compute SNP-level priors using the estimated enrichment estimates for each locus


## Sample files

* The example files from the GEUVDAIS project (data_file, snp_map and gene_map) and a tutorial can be found [here](https://github.com/xqwen/torus/tree/master/examples/GEUVADIS). Note the input data file is using format 2 with pre-computed Bayes factors in a meta-analytic setting.

