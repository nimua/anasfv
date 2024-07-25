# Constructing a Tree
We [provide make_tree.py](#provide make_treepy) for a one step tree generation process. Additionally, we offer [get_cds_alignments.py](#get_cds_alignmentspy) to generate the necessary CDS alignment files for tree construction. You can use these CDS alignments as input to build trees using other methods. You can utilize [download_asfv_genome.py](assembly/#download_asfv_genomepy) to download all the latest ASFV genomes from NCBI. Alternatively, you can use the directory "single_fasta" provided on [github](https://github.com/lrslab/anasfv) containing 312 genomes.
## make_tree.py
### Description
### Arguments
| Argument name	  | Required | Description |
| --------------  | ----- | -------- |
| -p, --processes |  No  | number of processes (default = 4)   |
| -f,	--file   |  Yes  | dir of the ASFV genome fasta files |
| -o, --output   |  Yes  | name of output dir  |
| --udance     |  Yes  | path to udance dir  |

### Example
```
make_tree.py -p 4 -f single_fasta -o tree --udance ./uDance
```
### Output
The final tree file is a Newick file named 'tree.nwk', located in the output dir specified by the -o parameter.

## get_cds_alignments.py
### Description
### Arguments
| Argument name	  | Required | Description |
| --------------  | ----- | -------- |
| -f,	--file   |  Yes  | dir of the ASFV genome fasta files |
| -c, --core |  No  | number of processes (default = 32)   |

### Example
```
get_cds_alignments.py -f single_fasta
```
### Output
