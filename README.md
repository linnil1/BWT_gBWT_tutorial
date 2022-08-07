# Tutorial for building BWT/graphBWT

I implemented the core of BWT in Python and visualize each step at the same time.

I also implemented graphBWT (gBWT), which can run BWT on graph structure.

Check the jupyter notebook files (bwt.ipynb, gbwt.ipynb) in these repo.

Hope this is helpful for understanding the BWT algorithm.

(I didn't do too much tricks for compression and optimization in this tutorial,
which may make the code harder to understand)


## Introduction

BWT(Burrows–Wheeler transform) is a efficient way to store and search string,
which has more advantages than other methods like suffix arrays or trie,
especially the last first mapping (LF mapping) property.

In bioinformatics, BWT is the core algorithm for read mapping in BWA and bowtie,
those tools are still popular due the the speed and their accuracy.

There are lots of lectures about BWT available online,
I recommend this one https://www.youtube.com/watch?v=4n7NPk5lwbI which inspired me a lot.

Another growing branch of read mapping is graph genome read mapping,
they use graph instead of string structure for indexing.
Graph can naturally include SNPs and indels,
which gives better accuracy in read mapping result.

One of graph genome milestone is HISAT2, which use the gBWT indexing derived from GCSA,
and it claims the speed is faster than linear genome read mapping tools mention above.

To better understand how BWT works on graph,
I first implemented the original BWT methods (bwt.ipynb) and then
extended the code to graph structure (gbwt.ipynb)
by learning from the GCSA paper https://pubmed.ncbi.nlm.nih.gov/26355784/.


## How to run

Assume you have Python enviornment, and then run these command

``` bash
git clone https://github.com/linnil1/BWT_with_graph_tutorial
cd BWT_with_graph_tutorial

# install requirements
pip install jupyter networkx matplotlib

# start the jupyter web serivce
jupyter notebook
```


## References

* BWA: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2705234/
* Bowtie2: https://genomebiology.biomedcentral.com/articles/10.1186/gb-2009-10-3-r25
* HISAT2: https://www.nature.com/articles/s41587-019-0201-4
* gBWT = GCSA = HISAT2's BWT https://pubmed.ncbi.nlm.nih.gov/26355784/


## LICENSE
MIT
