<img src="docs/SAMBAR_Logo.png" width="200">
Logo generated using DALL-E 2

# SAMBAR-Net
<ins>S</ins>equence <ins>A</ins>nalysis of <ins>M</ins>urine <ins>B</ins>2 <ins>A</ins>ccumulated <ins>R</ins>NAs: A CNN model to predict expressed B2 SINE genes in 3T3 cells across the mm10 genome

*Sahil B. Shah, Priyanka Sanghrajka, Azra Lari, James Mao, Liana Lareau, and Britt Glaunsinger*

## Overview
This repository contains the code and data needed to replicate the analysis found in the manuscript "RNA polymerase III transcription-associated polyadenylation promotes the accumulation of noncoding retrotransposons during herpesviral infection," which can be found at ... The goal of this binary (0,1) model is to predict whether a B2 SINE gene is expressed in the mm10 genome and identify which nucleotide sequence features are predictive of an expressed B2 SINE locus. The input data was obtained from an RNA-seq dataset in the following manuscript: Genome-wide mapping of infection-induced SINE RNAs reveals a role in selective mRNA export, where expressed B2 SINEs were defined as having an RPKM >= 10. The current model was trained with ony the forward DNA sequences.

The jupyter notebook used to train and analyze the CNN model are found in the `src/` directory. The saved, fully-trained model can be found in `models/`. The TF-MoDISco figure outputs are located in the `tf_modisco/figures` directory. All data used for model training and data produced from TF-MoDISco are located on Zenodo as zip files and can be found at "...". The `B2SINE_model_data.zip` file can be extracted in the `data/` directorys, and the `tf_modisco_data.zip` file can be extracted in the `tf_modisco/data` directory.

### Requirements and Usage
Most packages that this code base relies on are part of standard scientific/numeric python distributions. The following package dependencies are required for model training and analysis:
```
#Model training
torch==2.3.1
cuda==12.4
#TF-MoDISco analysis
modisco==0.5.16.4.1
captum==0.7.0
``` 
The GPU used to train the model was NVIDIA GeForce RTX 3090 Ti. To fully train the model using the described GPU takes about 2-3 hours to complete. To retrain and reanalyze the model, run all cells in the jupyter notebooks found in `src/`. Note: The TF-MoDISco analysis notebook contains a variable `b2_family` that can take one of the following three strings: "B2\_Mm1a", "B2\_Mm1t", and "B2\_Mm2," which represent the three B2 SINE families, defined by RepeatMasker, that the model was trained on.

### Help
Please open a ticket on github or contact Sahil B. Shah at sahilbshah@berkeley.edu for questions.
