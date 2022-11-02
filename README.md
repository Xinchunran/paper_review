# Paper review on ReLSO protein sequence generation and ESM2 summary

This repo server as the paper ReLSO analysis primarily and ESM analysis for the data science presentation. 
![ReLSO](./pics/relso.png)
![ESM2](./pics/esm_articles.png)

The model can use the weights to generate the protien sequences with lower fitness. How to represent the protein sequences remains a question.

## Overview

### Relevant work

#### TAPE:Evaluating Protein Transfer Learning with TAPE (https://github.com/Yijia-Xiao/ProteinLM) (https://github.com/songlab-cal/tape/blob/6d345c2b2bbf52cd32cf179325c222afd92aec7e/tape/models/modeling_utils.py#L843)
The first Semi-supervised learning use in protein function prediction and protein structure prediction. The semi-supervised method help lower down the cost of acquiring supervised protein labels. To facilitate progress in this field, Yun s Song et. al.[[1]](#1) introduce the Tasks Assessing Protein Embeddings (TAPE), a set of five biologically relevant semi-supervised learning tasks spread across different domains of protein biology, such as stability, secondary structure prediction, binding affinity prediction etc.

#### ProteinGAN: A generative adversarial network that generates functional protein sequences (https://github.com/Biomatter-Designs/ProteinGAN)
De novo protein design for catalysis of any desired chemical reaction is a long standing goal in protein engineering. ProteinGAN, a specialised variant of the generative adversarial network that is able to 'learn' natural protein sequence diversity and enables the generation of functional protein sequences. ProteinGAN learns the evolutionary relationships of protein sequences directly from the complex multidimensional amino acid sequence space and creates new, highly diverse sequence variants with natural-like physical properties. Using malate dehydrogenase as a template enzyme, they show that 24% of the ProteinGAN-generated and experimentally tested sequences are soluble and display wild-type level catalytic activity in the tested conditions in vitro, even in highly mutated (>100 mutations) sequences. ProteinGAN therefore demonstrates the potential of artificial intelligence to rapidly generate highly diverse novel functional proteins within the allowed biological constraints of the sequence space. However, it is really hard to convert while training. Therefore, it is hard to retrieve the high fitness protein sequences

#### ESM: Evolutionary Scale Modeling (https://github.com/facebookresearch/esm)
This is a large protein language model used in current protein related downstreams taski, which can be considered as GPT3 in biomolecules. However it does not contain the protein sequence design module or function prediction heads.
![ESM atlas](./pics/esm.png)


### Summary: 
Currently most of the protein language model are using Transformer based methods to capture both local and global information. And then using the sequence representation to conduct other protein structure/function related tasks. However, there are not specific models for the DMS data. The model ReLSO, a deep transformer-based autoencoder, combined both language model and latent space gradient-based methods to generate funtion-enhanced protein sequences.
![anit-ranibizumab design](./pics/anit-ranibizumab.png)

### ReLSO contributions
1. The model use transformer based encoder
2. The model construct sequence-function relationships 
3. The model re-normalize the convex latent space for better sequence optimization
4.  A gradient-ascent algorithm for generating new sequences from the latent space

#### ReLSO architecture
![ReLSO](./pics/model_architecture.png)

#### Training details

ReLSO were training on three different datasets TAPE, Gifford, GB1, repsectively. The sequence optimization is using gradient ascent.
1. Protein sequences are using one-hot embedding to convert into input
2. The latent space is regularized with KNN (k-nearest-neighbor)

#### Pseudocode:

** Input**: 𝒛 ∈ 𝑉*<sub>𝒛</sub>; protein sequence of amino acids; 𝒙 ∈ 𝑉*<sub>𝒙</sub>, amino acids token IDs.
** Output**: a ∈ R, where a indicte the desired values
** Hyperparameters**: 



### ESM contributions:

*The model is trained on the entire protein sequences database.


