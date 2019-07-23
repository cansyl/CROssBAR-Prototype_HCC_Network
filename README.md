# Comprehensive Resource of Biomedical Relations with Deep Learning and Network Representations (CROssBAR) - Biomedical Networks

The aim of the CROssBAR project is to develop a large-scale open access system to annotate complex relations between drugs/compounds, target biomolecules, pathways and diseases, via biological data integration and artificial learning based relation prediction.

![CROssBAR-Overview](https://user-images.githubusercontent.com/13165170/61704408-ee10c000-ad43-11e9-829b-83df6d226664.png)

**Sub-projects under CROssBAR:**

**1) Construction of the CROssBAR database** by integrating biological data from various resources

**2) Large-scale prediction of unknown drug-target interactions** (as well as non-interactions), by developing and applying a deep learning based ML method

**3) Generation of multi-partite biomedical networks**, where nodes will represent compounds/drugs, genes/proteins, pathways and diseases, and the edges will represent the known and predicted pairwise relations

**4) Biological evaluation (experimental validation)** of the selected results on PI3K/AKT/mTOR pathway, in terms of liver cancer mechanisms

**5) Construction of an open access web-service**, where it will be possible to browse with an entity of interest to observe the related network with its components

Repository for item # 2: https://github.com/cansyl/DEEPScreen

## Prototype: Hepatocellular Carcinoma Network

We constructed a prototype network using CROssBAR integrated data resources and by setting multiple enrichment based filters to include only the most relevant biomedical entities. Later, this workflow will be automatized to generate similar networks and visualize them on the fly using CytoScape browser plug-in, through the CROssBAR web-service.

Below network will be displayed to the web-service user following a web-service search with the term: “hepatocellular carcinoma”

**Workflow for the construction of the network:**

The prototype network model was created in 7 main steps:

**1. The selection of HCC related genes:**

- KEGG (H00048): 20 genes

- OMIM (Phenotype MIM 114550): 9 genes

- OpenTargets (EFO_0000182): 18 genes (with score > 0.2 «genetic associations» )

- TCGA_HCC: 34 genes (expert knowledge)

- 61 HCC related genes in total


## How to load the network on CytoScape:

