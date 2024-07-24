
# Overview
The **ANASFV** project focuses on analyzing nanopore-sequenced data of PCR-amplified African Swine Fever Virus (ASFV). It contains 4 available tasks:

- [mapping_assembly.py](#mapping-assembly): Using ONT reads of PCR-amplified ASFV to assemble a genome.

- [completeness.py](#genome-completeness-evaluation): Analyzing the completeness of an assembled ASFV genome.

- [recombination_test.py](#recombination-test): Checking for any evidence of recombination between genotypes I and II.

- [make_tree.py](#constructing-a-tree): Constructing a phylogenetic tree.

# Installation

Requirements：
1. python: 3.11 (tested). Most Python 3 versions should work.
2. Software versions tested:
	 \- Medaka: 1.11.3
 	 \- Samtools: 1.17
  	 \- BEDTools: 2.26.0
  	 \- Minimap2: 2.17-r941
  	 \- Homopolish: 0.4.1
  	 \- Prodigal: 2.6.3
  	 \- Exonerate: 2.4.0
  	 \- BLAST: 2.12.0
  	 \- MUSCLE: 5.1
  	 \- uDance: 1.6.5

  	 

Install requirements in conda environment and install ANASFV via PyPI:
```
conda create -n anasfv -c conda-forge python=3.11 -y
conda activate anasfv
conda install -c bioconda samtools bedtools minimap2 prodigal exonerate blast muscle -y
pip install anasfv
```

If you need to use medaka and homopolish for polish, you need to create their corresponding conda environments and install them, because there will be some conflicts if you install them directly in the ANASFV runtime environment.
```
conda create -n medaka -c bioconda -c conda-forge medaka -y
conda config --set channel_priority flexible
conda create -n homopolish -c conda-forge -c bioconda -c defaults more-itertools=8.4.0 homopolish=0.4.1 -y
```

For uDance installation refer to [uDance](https://github.com/balabanmetin/uDance)


If you find the installation too troublesome, we provide a docker image:
```
docker pull xxxx
docker container run -it xxx /bin/bash
```



#  Mapping Assembly
We provide the mapping_assembly.py script to perform the entire process from reads to assembled genomes. In addition, we provide download_asfv_genome.py to download all latest ASFV genomes from NCBI, and find_near_ref.py to select the ASFV genome with the most mapped reads as the reference genome.
## mapping_assembly.py
### Description:
该脚本需要一个参考序列，如果直接通过-r参数指定了一个参考序列，则会直接使用该参考序列。如果通过-r参数指定的是一个包含很多参考序列的文件夹，则
### Arguments:
| Argument name	  | Required | Description |
| --------------  | ----- | -------- |
| -p, --processes |  No  | number of processes (default = 4)   |
| -i,	--input   |  Yes  | input ASFV reads (fasta or fastq file) |
| -r, --ref     |  Yes  | a fasta file of ASFV genome or a folder containing multiple ASFV genomes (if the it is a folder, the program will automatically select the nearest one as the reference)|
| -o, --output   |  Yes  | file name of the output of assembled ASFV genome  |
| --medaka      |  No  | medaka model  |
| --homopolish   |  No  | homopolish model  |

### Example:
```
mapping_assembly.py -p 4 -r single_fasta -i test_data.fasta -o asfv_genome.fasta --medaka r941_min_high_g303 --homopolish R9.4.pkl
```
### Output:
A fasta file of the assembled ASFVgenome.

## download_asfv_genome.py
Description: 大于小于
```
download_asfv_genome.py
```

## find_near_ref.py
Description:
Arguments:
Output:
# Genome Completeness Evaluation
## completeness.py
# Recombination Test
## recombination_test.py
# Constructing a Tree
## make_tree.py
## get_cds_alignments.py
# Example Projects
## Prepare your data
1. ONT reads (fasta or fastq file) ，可以通过下面的命令下载我们的测试文件
```
wget https://raw.githubusercontent.com/lrslab/anasfv/main/test_data.fasta
```
2. Other ASFV genomes. These genomes are used for mapping assembly and tree building. You can directly use the single_fasta directory in this project, which contains 312 downloaded ASFV genomes, or you can run download_asfv_genome.py, which will create a single_fasta directory in the working directory and download all the latest ASFV genomes on NCBI to the single_fasta directory.