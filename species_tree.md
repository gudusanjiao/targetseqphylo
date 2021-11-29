# SESSION 5: SPECIES TREE METHODS
Nan Hu, 2021 Nov

---

## 5.1 Why do we need species tree?
Reconstructing species tree is an essential step into assessing relationships among our target species. When we generated trees from our targeted genes, we may noticed that each gene tree only represents its own evolutionary history which differs from expected species tree (because of gene duplication, lost, convention, historical hybridization, incompleted lineage sorting, and presence of deep coalescence). In other word, these gene trees may differ from each other and not agree with species tree which reflects the real phylogeny of associated species. In order to acquire a concensus phylogeny to study in related species, we would like to infer species tree using specific methods.

![Figure1DeepCoalescence](https://github.com/gudusanjiao/targetseqphylo/blob/main/miscellaneous/pic2.png "Fig1")

Figure 1. Deep coalescence may cause discordance between gene tree and species tree.

More information about why gene trees oftenly do not agree with species tree, you can refer to [Gergely J. Szöllősi, Eric Tannier, Vincent Daubin, Bastien Boussau, The Inference of Gene Trees with Species Trees, Systematic Biology, Volume 64, Issue 1, January 2015, Pages e42–e62](https://doi.org/10.1093/sysbio/syu048)
## 5.2 How to infer phylogenies of species?
There are two major ways in inferring species tree. First and simple one is to use a concatenated dataset, which refers to concatenation. To apply this method, every gene will be added together and aligned into a supermatrix. Then, further phylogenetic inferences will be deployed onto this concatenated gene which will be treated as a single gene complex. 

However, evidences implied that the concatenation is not always correctly reconstruct the phylogeny. It lacks of modeling deep coalescence which creates disagreement with the true phylogeny. This is mainly caused by a majority of genes may not share the same history as species do. Thus, when using concatenation method, signals from discordant genes would outweighing the less coalescence ones.

In order to solve the problem of deep coalescence in species tree reconstruction, several methods have been developed to either model the process of deep coalescence or taking shortcuts where deep coalescence trees still consist with real species tree. Full modeling of deep coalescence is more accurate but cannot take large datasets due to the complexity of computational time. Since genomic level sequecing is more and more prevalent nowadays (including our target sequencing strategy), shortcuts methods are becoming popular.

![image](https://user-images.githubusercontent.com/16470742/143940257-bec4517c-f3df-4b03-8e38-fc6239745896.png)

Figure 2. Schematic of the concatenation and coalescent paradigms in phylogenetics. [Liu et al.](https://nyaspubs.onlinelibrary.wiley.com/doi/full/10.1111/nyas.12747)

## 5.3 Practising species tree method using ASTRAL
In today's workshop, we will use ASTRAL, one of the shortcuts methods, to infer our species tree from our gene tree datasets. 

ASTRAL is a Java phylogenetics program that uses the frequency of quartets in gene trees to estimate a species tree. It offers a one command line solution under Linux. Comparing these quartets is not computational intense so this program may finish in a short time. However, to be consistent to other sessions in our workshop, we will still run this under HPCC job submitting system.
> Need a singularity container code to access to new version of ASTRAL (to Yanni)
```bash
#!/bin/bash
#SBATCH -J astral
#SBATCH -o %x.o%j
#SBATCH -e %x.e%j
#SBATCH -p nocona
#SBATCH -N 1
#SBATCH -n 6

java -jar astral -i [unrooted gene tree file, .tre] -o [output species tree file, .tre]
```

### Action 5.3.1
*Use ASTRAL to generate results from gene trees*
```

```

## 5.4 Interpretting ASTRAL results
After generating species tree from ASTRAL, we may view and edit it through FigTree by rerooting, collapsing clades, re-coloring, enhancing branches, showing branch length etc. The goal of customizing it is to better convey our result to readers. Notice that, support values in ASTRAL species tree means the Local Posterior Probability, which indicates how well the shown quartet is compared to the other two possible quartets at that branch. The branch lengths are coalescent units in related to ancestral population size and the amount of change found on the gene trees.

### Action 5.4.1
*Transfer output tree to your computer and view it with FigTree*

### Action 5.4.2
*Customize your tree in FigTree and try to interpret it*


