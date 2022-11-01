# Paper anaylsis Reslo protein sequence generation

This repo server as the paper Reslo analysis for the data science presentation. 

![Reslo](/pictures/xxx.png)

The model can use the weights to generate the protien sequences with lower fitness. How to represent the protein sequences remains a question.

##Overview
### Relevant work
#### TAPE:Evaluating Protein Transfer Learning with TAPE (https://github.com/Yijia-Xiao/ProteinLM) (https://github.com/songlab-cal/tape/blob/6d345c2b2bbf52cd32cf179325c222afd92aec7e/tape/models/modeling_utils.py#L843)
Protein modeling is an increasingly popular area of machine learning research. Semi-supervised learning has emerged as an important paradigm in protein modeling due to the high cost of acquiring supervised protein labels, but the current literature is fragmented when it comes to datasets and standardized evaluation techniques. To facilitate progress in this field, we introduce the Tasks Assessing Protein Embeddings (TAPE), a set of five biologically relevant semi-supervised learning tasks spread across different domains of protein biology. We curate tasks into specific training, validation, and test splits to ensure that each task tests biologically relevant generalization that transfers to real-life scenarios. We benchmark a range of approaches to semi-supervised protein representation learning, which span recent work as well as canonical sequence learning techniques. We find that self-supervised pretraining is helpful for almost all models on all tasks, more than doubling performance in some cases. Despite this increase, in several cases features learned by self-supervised pretraining still lag behind features extracted by state-of-the-art non-neural techniques.

#### ProteinGAN: A generative adversarial network that generates functional protein sequences (https://github.com/Biomatter-Designs/ProteinGAN)
De novo protein design for catalysis of any desired chemical reaction is a long standing goal in protein engineering, due to the broad spectrum of technological, scientific and medical applications. Currently, mapping protein sequence to protein function is, however, neither computationionally nor experimentally tangible. Here we developed ProteinGAN, a specialised variant of the generative adversarial network that is able to 'learn' natural protein sequence diversity and enables the generation of functional protein sequences. ProteinGAN learns the evolutionary relationships of protein sequences directly from the complex multidimensional amino acid sequence space and creates new, highly diverse sequence variants with natural-like physical properties. Using malate dehydrogenase as a template enzyme, we show that 24% of the ProteinGAN-generated and experimentally tested sequences are soluble and display wild-type level catalytic activity in the tested conditions in vitro, even in highly mutated (>100 mutations) sequences. ProteinGAN therefore demonstrates the potential of artificial intelligence to rapidly generate highly diverse novel functional proteins within the allowed biological constraints of the sequence space.

#### ESM: Evolutionary Scale Modeling (https://github.com/facebookresearch/esm)
This is a large protein language model used in current SOTA task. However it does not contain the capability in protein sequence design

### Summary: 
Currently most of the protein language model are using Transformer based methods to capture both local and global information. However, there are not specific models for the DMS data. The model Relso 
