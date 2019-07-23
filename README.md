# Comprehensive Resource of Biomedical Relations with Deep Learning and Network Representations (CROssBAR) - Biomedical Networks

The aim of the CROssBAR project is to develop a large-scale open access system to annotate complex relations between drugs/compounds, target biomolecules, pathways and diseases, via biological data integration and artificial learning based relation prediction.

![CROssBAR-Overview](https://user-images.githubusercontent.com/13165170/61704408-ee10c000-ad43-11e9-829b-83df6d226664.png)

**Sub-projects under CROssBAR:**

**1) Construction of the CROssBAR database** by integrating biological data from various resources

**2) Large-scale prediction of unknown drug-target interactions** (as well as non-interactions), by developing and applying a deep learning based ML method

**3) Generation of the biomedical networks**, where nodes will represent compounds/drugs, genes/proteins, pathways and diseases, and the edges will represent the known and predicted pairwise relations

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

<img src="https://user-images.githubusercontent.com/8128032/61721044-86bd3500-ad70-11e9-9df0-50c7bc51a329.png" width="500">

**2. The determination of protein-protein interactions (PPIs):** 

- STRING application on CytoScape 

- PPIs with a confidence score >= 0.95

- 45 PPIs between 31 proteins

![image](https://user-images.githubusercontent.com/8128032/61718989-b702d480-ad6c-11e9-849b-0245642cca10.png)

**3. The selection of compounds interacting with HCC related genes:**

**a. Known interactions from DrugBank** 

- 63 interactions between 21 genes and 57 compounds 

- Edge color: Green   

- Node color: Red

![image](https://user-images.githubusercontent.com/8128032/61719015-ca15a480-ad6c-11e9-9c05-031d449f6d5c.png)

**b. Experimentally measured interactions from PubChem + ChEMBL (ExCAPE dataset)**

- Compounds with pXC50 >= 5.0 were labelled as active.

- For each compound, enrichment score was calculated based on ratios of active & inactive datapoint numbers of compounds in HCC genes and in total ExCAPE gene set.

- Only compounds with enrichment score > 1 were considered

- Top 5 compounds, which are not similar to each other, were selected based on enrichment scores 

- 26 interactions between 11 genes and 12 compounds

- Edge color: Blue   

- Node color: Orange (if not a drug) 

![image](https://user-images.githubusercontent.com/8128032/61719047-dbf74780-ad6c-11e9-86b0-a871eeac768c.png)

**c. Predicted interactions from DEEPScreen**

- Predicted interactions were retrieved from DEEPSreen predictions 

- For each compound, enrichment score was calculated based on ratios of active & inactive datapoint numbers of compounds in HCC genes and in total ExCAPE gene set.

- Only compounds with enrichment score > 1 were considered

- Top 5 compounds, which are not similar to each other, were selected based on enrichment scores 

- 25 interactions between 5 genes and 23 compounds 

- Edge color: Red   

- Node color: Orange (if not a drug) 

![image](https://user-images.githubusercontent.com/8128032/61719081-ec0f2700-ad6c-11e9-98e9-de9050fd71d5.png)

**4. The determination of HCC related pathways and their gene associations:** 

- Signaling pathways associated with HCC disease pathway (hsa05225) in KEGG

- STRING enrichment application on CytoScape 
  - FDR cutoff = 0.05
  - KEGG signaling pathways >= 5 enriched genes
     
<img src="https://user-images.githubusercontent.com/8128032/61722515-19f76a00-ad73-11e9-80f9-fab13384c512.png" width="600">

- 66 interactions between 22 genes and 10 pathways 

![image](https://user-images.githubusercontent.com/8128032/61719251-40b2a200-ad6d-11e9-982b-89bd90f87011.png)

**5. The determination of other diseases associated with HCC related genes:** 

- Associations between these genes and other diseases

- STRING enrichment application on CytoScape 
  - FDR cutoff = 0.05
  - KEGG diseases >= 10 enriched genes

<img src="https://user-images.githubusercontent.com/8128032/61721937-0dbedd00-ad72-11e9-8cba-61602a5c8049.png" width="600">

- 72 interactions between 27 genes and 5 diseases

![image](https://user-images.githubusercontent.com/8128032/61719376-735c9a80-ad6d-11e9-98b0-ec39f750218a.png)

**6. The determination of associations between pathways and diseases:** 

- Retrieved from KEGG pathways of the network diseases

- 26 interactions between 10 pathways and 5 diseases

<img src="https://user-images.githubusercontent.com/8128032/61731119-7793b280-ad83-11e9-9a78-0907f525c31b.png" width="650">

**7. The determination of associations between genes and HPO terms:**

- HPO terms were retrieved from Human Phenotype Ontology database (https://hpo.jax.org/app/)

- For each HPO term, enrichment score and p-value was calculated based on ratios of HPO terms in HCC genes and in total ExCAPE gene set

- Only HPO terms with enrichment score > 65 and p-value < 10^-5 were considered

- Top 10 HPO terms, which have not parent-child relationship with each other, were selected and associated with related genes

- 120 interactions between 22 genes and 10 HPO terms

<img src="https://user-images.githubusercontent.com/8128032/61719445-99823a80-ad6d-11e9-845a-9e7eba619146.png" width="600">



**- The prototype network below includes 178 nodes (i.e., genes, compounds, pathways, KEGG diseases, HPO terms) and 443 edges (i.e., interactions between nodes) in total.**

![image](https://user-images.githubusercontent.com/8128032/61729585-38179700-ad80-11e9-90d2-b09c5cbdf4eb.png)








## How to load the network on CytoScape:

To load the Hepatocellular Carcinoma Prototype Network on CytoScape;

- You can directly open the session file (Hepatocellular Carcinoma Network.cys) via CytoScape application  

  or (if it does not work),

- You can open a new session on CytoScape and import the network file (Hepatocellular Carcinoma Network.xgmml) as File -> Import -> Network -> File 

