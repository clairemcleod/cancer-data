# Cancer data acquisition and processing for Project Cognoma

This is a mixed notebook and data repository for retrieving cancer data for [Project Cognoma](https://github.com/cognoma/cognoma). Currently, all data is from the [TCGA Pan-Cancer collection](https://genome-cancer.soe.ucsc.edu/proj/site/xena/datapages/?cohort=TCGA%20Pan-Cancer%20%28PANCAN%29 "UCSC Xena Browser cohort: TCGA Pan-Cancer (PANCAN)") of the UCSC Xena Browser.

## Workflow

The data acquisition and analysis is executing by running Jupyter notebooks in the following order:

1. [`1.TCGA-download.ipynb`](1.TCGA-download.ipynb) — download and compress TCGA datasets.
+ [`2.TCGA-process.ipynb`](2.TCGA-process.ipynb) — convert downloaded TCGA datasets into sample × gene matrixes.

The [`execute.sh`](execute.sh) script installs and activates the conda environment and then executes the notebooks in order. Run with the command `bash execute.sh` from the repository's root directory.

## Directories

The repository contains the following directories:

+ [`download`](download) — contains files retrieved from an external location whose content is unmodified. Downloaded files are currently not tracked due to large file size, although associated metadata files are tracked for versioning.
+ [`data`](data) — contains generated datasets. The complete matrix files are not currently tracked due to file size, but randomly-subsetted versions are available for development use (see [`data/subset`](data/subset)).

## Environment

This repository uses conda to manage its environment, which is named `cognoma-cancer-data`. The required packages and versions are listed in [`environment.yml`](environment.yml). If as a developer, you require an additional package, add it to `environment.yml`.
