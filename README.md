# A minimal NF pipeline

Based on but liter than [RNAseq-NF](https://github.com/nextflow-io/rnaseq-nf), for pedagogical purpose.

## Requirements 

* Unix-like operating system (Linux, macOS, etc)
* Java 8 

## Quickstart 

1. If you don't have it already install Docker in your computer. Read more [here](https://docs.docker.com/).

2. Install Nextflow (version 0.24.x or higher):
      
        curl -s https://get.nextflow.io | bash

3. Launch the pipeline execution: 

        ./nextflow run gaow/fastqc-nf -with-docker
        
4. When the execution completes open in your browser the report generated at the following path:

        results/multiqc_report.html 
		
Note: the very first time you execute it, it will take a few minutes to download the pipeline 
from this GitHub repository and the the associated Docker images needed to execute the pipeline.  


## Cluster support

Execution relies on [Nextflow](http://www.nextflow.io) framework which provides an 
abstraction between the pipeline functional logic and the underlying processing system.

This allows the execution of the pipeline in a single computer or in a HPC cluster without modifying it.

Currently the following resource manager platforms are supported:

  + Univa Grid Engine (UGE)
  + Platform LSF
  + SLURM
  + PBS/Torque


By default the pipeline is parallelized by spawning multiple threads in the machine where the script is launched.

To submit the execution to a UGE cluster create a file named `nextflow.config` in the directory
where the pipeline is going to be executed with the following content:

    process {
      executor='uge'
      queue='<queue name>'
    }

To lean more about the avaible settings and the configuration file read the 
Nextflow [documentation](http://www.nextflow.io/docs/latest/config.html).


## Components 

* [FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/) 0.11.5
