# Quantify transcript expression in paired-end RNA-seq data with kallisto
-----------------------------------------------------------------------
Initiall written by Kamil Slowikowski
https://github.com/slowkow/snakefiles

Adapted by Daniel Lang


# Requirements:

```bash
# optionally create new env
conda install kallisto
conda install -c bioconda r-sleuth
conda install -c bioconda snakemake
conda install r-essentials
```

# Usage: 
```bash
#create DAG
snakemake --dag  --configfile config.yml | dot -Tsvg > dag.svg

#run locally
snakemake --configfile config.yml 

#cluster submission
snakemake \
  	--snakefile kallisto.snakefile \
  	--configfile config.yml \
  	--jobs 100 \
  	--cluster 'your syntax to submit jobs on the cluster'
```

