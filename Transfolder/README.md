# Transfolder: Protein Structural Generative Model
## Motivation
Molecular Dynamic (MD) simulation has been employed to explore the molecular dynamics stored in the dynamic trajectories. MD simulations are computationally expensive and there have been a number of existing studies to bypass the high computational demand such as GPU-accelerated MD simulations, QM/MM hybrid calculations, deep-learning approaches.
Protein folding is a process by which a polypeptide chain folds to become a biologically active protein in its native 3-dimensional structure. Due to the high computational demand explained above, how to understand the protein folding mechanism has not been fully explained. There are a number of reported factors that play significant roles in protein folding.
- Protein folding is mediated by entropic effect.
- Numerous local minima along the energy landscape that allow proteins to fold more actively.

In order to understand the protein folding mechanism, it is inevitable to develop a powerful tool to aid researchers investigate the dynamic effects involved in the protein folding process. To address this, we developed a **prototype** protein structural generative model by integrating Transformers model for reserach and Vanderbilt University DS-5899 Project purposes: Transfolder.

## Model Architecture
<src img="https://user-images.githubusercontent.com/33948358/206032007-055c46f6-f22f-41b6-89ce-5fe32c3d1cd5.png" width=50%>

## Transfolder output

## How can we analyze?
The evaluation of the generative model can be extremely challenging. The model consistency can be evaluated using the loss function; however, the specific metric or criteria to evaluate the output of Transfolder is unknown. The analysis shown below are simple strategies that have no scientific significance but to demonstrate the glimpse of analysis to the peers in Vanderbilt University DS-5899.
<img width="1267" alt="Screenshot 2022-12-06 at 3 39 46 PM" src="https://user-images.githubusercontent.com/33948358/206033138-f4c70024-6dca-47d3-b346-95f75c7c3224.png">
We generated a protein structural trajectory (1ps time gap) of a protein consisted of 378 amino acids. We measured root-mean-square deviation (RMSD) of each structure and compared against two proteins, consisted of 129 and 1058 amino acids. Based on the lengths of proteins, it is physically intuitive that 1058 amino acids will have larger RMSD variation. We investigated two quantitative factors: entropy associated with RMSD distribution, the mean and the standard deviation of each distribution.
<img width="1220" alt="Screenshot 2022-12-06 at 3 39 58 PM" src="https://user-images.githubusercontent.com/33948358/206034511-598e6e6f-baf4-47dc-94dd-29ed9057c9b9.png">
<img width="1238" alt="Screenshot 2022-12-06 at 3 40 21 PM" src="https://user-images.githubusercontent.com/33948358/206034522-f64118fa-0680-4d9f-b071-7a46af11f49b.png">
<img width="1244" alt="Screenshot 2022-12-06 at 3 40 11 PM" src="https://user-images.githubusercontent.com/33948358/206034533-2ff21aa6-133b-4c30-8507-8fce217ca7d9.png">
