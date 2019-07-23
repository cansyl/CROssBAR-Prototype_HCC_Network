# Comprehensive Resource of Biomedical Relations with Deep Learning and Network Representations (CROssBAR) - Biomedical Networks

The aim of the CROssBAR project is to develop a large-scale open access system to annotate complex relations between drugs/compounds, target biomolecules, pathways and diseases, via biological data integration and artificial learning based relation prediction.

Sub-project under CROssBAR:

**1) Construction of the CROssBAR database** by integrating biological data from various resources;
**2) Large-scale prediction of unknown drug-target interactions** (as well as non-interactions), by developing and applying a deep learning based ML method;
**3) Generation of multi-partite biomedical networks**, where nodes will represent compounds/drugs, genes/proteins, pathways and diseases, and the edges will represent the known and predicted pairwise relations;
**4) Biological evaluation (experimental validation)** of the selected results on PI3K/AKT/mTOR pathway, in terms of liver cancer mechanisms;
**5) Construction of an open access web-service**, where it will be possible to browse with an entity of interest to observe the related network with its components.

Repository for item # 2: https://github.com/cansyl/DEEPScreen

## Prototype: Hepatocellular Carcinoma Network

We constructed a prototype network using CROssBAR integrated data resources and by setting multiple enrichment based filters to include only the most relevant biomedical entities. Later, this workflow will be automatized to generate similar networks and visualize them on the fly using CytoScape browser plug-in, through the CROssBAR web-service.

Below network will be displayed to the web-service user following the search with the term: “hepatocellular carcinoma”

**Workflow for the construction of the network:**

