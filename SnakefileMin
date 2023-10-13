## Check minimum Snakemake version

from snakemake.utils import min_version

min_version("5.20.1")

## Run all analyses
rule all:
    input:
        f"test.html",

rule fastqc:
    input:
        fastq=f"test.fastq.gz",
    output:
        html=f"test.html",
        zip=f"test_fastqc.zip", 
    params:
        extra="--quiet",
    log:
        f"test.log",
    threads: workflow.cores
    resources:
        mem_mb=1000,
    wrapper:
        "v2.6.0/bio/fastqc"