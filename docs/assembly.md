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
