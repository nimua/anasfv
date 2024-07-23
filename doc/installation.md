## Installation:

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
  	 \- blast: 2.12.0
  	 \- MUSCLE: 5.1
  	 \- uDance: 1.6.5

  	 
 
Install requirements:
```
conda create -n anasfv -c bioconda python=3.11 samtools bedtools minimap2 prodigal exonerate blast muscle -y
```

Enter the anasfv environment. Install ANASFV by PyPI:：
```
conda activate -n anasfv
pip install anasfv
```

If polish is not needed, the following three lines can be omitted.
```
conda create -n medaka -c bioconda -c conda-forge medaka -y
conda config --set channel_priority flexible
conda create -n homopolish -c conda-forge -c bioconda -c defaults more-itertools=8.4.0 homopolish=0.4.1 -y
```

For uDance installation refer to [uDance](https://github.com/balabanmetin/uDance)


It may not be easy to successfully install all the dependent software. So we provide a docker installation:
```
docker.....
```
