# Example Projects
## Prepare your data
1. ONT reads (fasta or fastq file) ，可以通过下面的命令下载我们的测试文件
```
wget https://raw.githubusercontent.com/lrslab/anasfv/main/test_data.fasta
```
2. Other ASFV genomes. These genomes are used for mapping assembly and tree building. You can directly use the single_fasta directory in this project, which contains 312 downloaded ASFV genomes, or you can run download_asfv_genome.py, which will create a single_fasta directory in the working directory and download all the latest ASFV genomes on NCBI to the single_fasta directory.
