# SESSION 5: SPECIES TREE METHODS
Nan Hu, 2021 Nov

---

## 5.1 Why do we need species tree?
Reconstructing species tree is an essential step into assessing relationships among our target species. When we generated trees from our targeted genes, we may noticed that each gene tree only represents its own evolutionary history which differs from expected species tree (because of gene duplication, lost, convention, historical hybridization, incompleted lineage sorting, and presence of deep coalescence). In other word, these gene trees may differ from each other and not agree with species tree which reflects the real phylogeny of associated species. In order to acquire a concensus phylogeny to study in related species, we would like to infer species tree using specific methods.

## 5.2 How to infer phylogenies of species?
There are two major ways in inferring species tree. First and simple one is to use a concatenated dataset, which refers to concatenation. To apply this method, every gene will be added together and aligned into a supermatrix. Then, further phylogenetic inferences will be deployed onto this concatenated gene treated as a single gene complex. However, evidences implied that the concatenation is not always correctly reconstruct the phylogeny. It lacks of modeling deep coalescence

## 5.3 Practising species tree method using ASTRAL

> Need a singularity container code to access to new version of ASTRAL (to Yanni)
```bash
#!/bin/bash
#SBATCH -J astral
#SBATCH -o %x.o%j
#SBATCH -e %x.e%j
#SBATCH -p nocona
#SBATCH -N 1
#SBATCH -n 32

java -jar astral -i <unrooted gene tree file, .tre> -o <output species tree file, .tre>
```

### Action 5.3.1
*Use ASTRAL






