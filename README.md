# Kallisto_Snakemake
## Originally forked from https://github.com/bhklab/Snakemake/tree/master/Kallisto_Snakemake

## Snakemake pipeline for RNASeq analysis using Kallisto on Slurm

- Use Kallisto_Index pipeline to build the Kallisto Index using the latest GENCODE transcriptome.
- Use Run_Kallisto pipeline to run Kallisto on raw fastq files. If you have multiple samples.The pipeline will automatically submit news jobs into the cluster.



**STEP 1: Login to cluster:**
```
ssh username@cluster.org
```


**STEP2: Download repo, genome references and example data**
```
Download Kallisto transcriptome and create index

salloc -c 1 -t 2:00:00 --mem=6G -p build

git clone https://github.com/LupienLab/kallisto_snakemake.git

cd kallisto_snakemake/Kallisto_Index

snakemake --snakefile Snakemake --cores 1

```

**STEP 3: Edit config.yaml and samples.tsv:**
```
cd kallisto_snakemake/Run_Kallisto

vi config.yaml 

vi samples.tsv
```
**STEP 4: Run Kallisto with snakemake command on cluster:**
```
sbatch sbatch.sh

```






