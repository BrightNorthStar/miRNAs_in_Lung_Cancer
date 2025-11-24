# miRNAs_in_Lung_Cancer
A machine learning based study of the quantitative and biological significances of miRNA expression level changes in lung cancer. 

75th Annual Regeneron International Science and Engineering Fair fourth place winner in COMPUTATIONAL BIOLOGY AND BIOINFORMATICS category 'CBIO033 — Small Changes, Big Impact: miRNAs in Lung Cancer Detection'.

# Introduction
MicroRNAs (miRNAs) are small, non-coding RNAs that modulate gene expression by down-regulating (via mRNA degradation and translational repression) or up-regulating (via direct mRNA activation or repression attenuation) their target genes. As miRNA dysregulation often occurs early in disease progression and circulating miRNAs are detectable in body fluids, they represent valuable non-invasive biomarkers for early diagnosis, prognosis, treatment monitoring, and drug discovery [3].

For example, a recent study [1] identified 10 specific miRNAs linked to lung cancer (LC) and used them to build an early diagnostic classifier. miRNAs with highly dysregulated expression levels, have so far constituted the focus of disease-specific biomarkers research. Dysregulation is usually measured by statistically significant (p < 0.05) fold change (FC) values calculated between positive (disease) and negative (no disease) samples, with conventional high dysregulation threshold set as |log2(FC)| ≥ 1.0 – without a robust justification.

Multiple studies [7, 15, 10, 12] have shown that miRNA expression levels weakly correlate with their regulatory activity [7], due to complex and nonlinear interactions [12] influenced by a multitude of factors [15, 10]. These findings suggest miRNAs with mid-range dysregulation levels may yet carry clinically valuable information. 

This study aims 
- to question the merit of considering only the strongly dysregulated miRNAs by comparing the diagnostic utility of high versus medium dysregulated miRNAs in the context of lung cancer, and 
- to advocate for a broader, more inclusive approach in miRNA-based disease diagnostics.

# Background Research

![miRNA action illustration.](/BackgroundResearch.png)

## Protein Synthesis and Gene Expression Regulation by miRNAs

### Overview of Protein Synthesis
- Proteins are essential cellular workhorses, serving as structural, motor, and catalytic elements in cells of living organisms [9].
- Protein synthesis is also vital in medicine, influencing disease understanding and drug development [6].
- Protein synthesis is a form of gene expression. 
- Despite their common DNA, different cell types express genes selectively using distinct catalysts [11].

### Key Steps of Protein Synthesis
1. **Transcription:** DNA is transcribed into mRNA by enzymes [11].
   - Messenger RNA (mRNA): Carries genetic information i.e., coding sequences, necessary for protein synthesis [11].
   - The transcriptome represents the RNA molecules transcribed in a cell at a specific time [11].
2. **Translation:** Ribosomes read mRNA sequences and assemble amino acids into proteins [11].
   - Ribosomal RNA (rRNA): Forms ribosome cores and catalyzes the assembly of protein molecules [11].
   - Transfer RNA (tRNA): Delivers amino acids to ribosomes for use in protein synthesis [11].
   - MicroRNA (miRNA): Regulates gene expression via mRNA silencing [13, 10, 5, 14].
   - Non-coding RNAs (ncRNA) such as rRNA, tRNA and miRNA are not translated into proteins [2].

### miRNAs: Key Regulators of Gene Expression
- miRNAs are small (18-25 nucleotides) non-coding RNAs that regulate gene expression [13, 10, 5, 14].
- The human genome contains ~2,500 miRNAs, impacting ~60% of the transcriptome [13].
- miRNAs bind to their target mRNAs, leading to post-transcription mRNA degradation or translation inhibition [16, 13, 10].
- Under certain conditions, miRNAs can also activate translation or regulate transcription [10].

### Dynamic Nature of miRNA-mRNA Interactions
- miRNA-mRNA interactions depend on multiple factors including [15, 10]:
  - Subcellular location of miRNAs
  - miRNA and target mRNA abundance
  - Number of target mRNA sites
  - Affinity of miRNA-mRNA binding
- miRNAs can also circulate in extracellular fluids, facilitating cell-to-cell communication [10].

### miRNAs as Biomarkers (for Disease and Cancer Research)
- Dysregulated miRNA expression alters gene activity, contributing to diseases, including cancer [5].
- miRNAs exhibit high stability in body fluids, making them promising biomarkers for disease diagnosis and prognosis [5].
- miRNA-based therapies are being explored for cancer treatment, with potential for clinical applications [5].
- Ongoing research aims to classify cancers based on miRNA expression profiles, improving precision medicine approaches [14].

# Materials and Procedure

## miRNA Microarray Data [4]
This dataset comprises full miRNA expression profiles for 1,566 lung cancer (LC) patients and 2,178 patients without LC. The large sample size across both positive (LC(+)) and negative (LC(-)) classes enabled statistically robust partitioning of miRNAs into three categories based on dysregulation level: high (HD, |log2(FC)| ≥ 1.0), medium (MD, 0.15 ≤ |log2(FC)| < 1.0), and non-significant (ND, 0 < |log2(FC)| < 0.15 ).

![miRNA Microarray Data format - illustrative table.](/miRNAMicroarrayDataFormat.png)

## miRNA Sequence Data [8]
This dataset provides sequence-specific information for miRNAs, including attributes such as sequence length, molecular weight, mononucleotide counts and frequencies, and dinucleotide counts and frequencies. Following the selection of the most discriminative miRNAs from the HD and MD categories, this dataset was used in the second phase of the study to comparatively analyze sequence attributes across HD and MD miRNAs through attribute-based clustering.

![miRNA Sequence Data format - illustrative table.](/miRNASequenceDataFormat.png)

## Google Colab Environment
Google Colab, a cloud-based Jupyter Notebook platform with free access to computing resources (including GPUs and TPUs), was used to implement the diagnostic classifiers and the miRNA feature clustering algorithm. (The developed Jupyter Notebook (in Python) is available upon request.)

## Procedure

![Two block diagrams illustrating the two steps of the procedure developed and implemented.](/Procedure.png)

# Results

## Diagnostic Classifier KPIs

![Diagnostic classifier KPIs, bar plot and table.](/KPIs.png)

## Dimensionality Reduction

![Dimensionality reduction, two scatter plots.](/DimensionalityReduction.png)

## Mean Sequence Attributes in Observed miRNA Clusters

![Mean sequence attributes in observed miRNA clusters, 3 heatmaps.](/MeanSequenceAttributesperCluster.png)

## miRNA Distributions Across Clusters

![miRNA distributions across clusters, 1 heatmap.](/miRNADistributionsAcrossClusters.png)

# TBC
