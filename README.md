# miRNAs_in_Lung_Cancer
A machine learning based study of the quantitative and biological significances of miRNA expression level changes in lung cancer. (75th Annual Regeneron International Science and Engineering Fair fourth place winner in COMPUTATIONAL BIOLOGY AND BIOINFORMATICS category 'CBIO033 — Small Changes, Big Impact: miRNAs in Lung Cancer Detection'.)

# Introduction
MicroRNAs (miRNAs) are small, non-coding RNAs that modulate gene expression by down-regulating (via mRNA degradation and translational repression) or up-regulating (via direct mRNA activation or repression attenuation) their target genes. As miRNA dysregulation often occurs early in disease progression and circulating miRNAs are detectable in body fluids, they represent valuable non-invasive biomarkers for early diagnosis, prognosis, treatment monitoring, and drug discovery [3].

For example, a recent study [1] identified 10 specific miRNAs linked to lung cancer (LC) and used them to build an early diagnostic classifier. miRNAs with highly dysregulated expression levels, have so far constituted the focus of disease-specific biomarkers research. Dysregulation is usually measured by statistically significant (p < 0.05) fold change (FC) values calculated between positive (disease) and negative (no disease) samples, with conventional high dysregulation threshold set as |log2(FC)| ≥ 1.0 – without a robust justification.

Multiple studies [7, 15, 10, 12] have shown that miRNA expression levels weakly correlate with their regulatory activity [7], due to complex and nonlinear interactions [12] influenced by a multitude of factors [15, 10]. These findings suggest miRNAs with mid-range dysregulation levels may yet carry clinically valuable information. 

This study aims 
- to question the merit of considering only the strongly dysregulated miRNAs by comparing the diagnostic utility of high versus medium dysregulated miRNAs in the context of lung cancer, and 
- to advocate for a broader, more inclusive approach in miRNA-based disease diagnostics.
