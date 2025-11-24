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

# Discussion

## Diagnostic Potential of miRNAs in Lung Cancer (LC)

- Medium dysregulation (MD) miRNAs achieved a very high diagnostic accuracy (99.2%), comparable to high dysregulation (HD) miRNAs (99.7%).
- Non-significant dysregulation (ND) miRNAs also demonstrated notable diagnostic potential (92.1% accuracy). 

## Insights from K-Means Clustered miRNA Attributes

- 31 clusters were identified based on miRNA sequence attributes using k-means clustering and elbow method.
- 13, close to half, of the 31 clusters comprise both HD and MD miRNAs, highlighting shared and/or alike features i.e., attribute values.
- Clusters with indices 1, 7, and 23 include numerous discriminative MD miRNAs without any HD category representation, pointing to unique-to-MD features and likely novel biochemical mechanisms in LC.

## Dimensionality Reduction Related Observations

- PCA (linear) and t-SNE (nonlinear) techniques, both applied for a two-dimensional output, confirmed the need for a substantially higher dimensional presentation and analysis for feature separation.

# Conclusions

## Hypothesis vs Outcome

- <ins>Hypothesis:</ins> miRNAs with medium dysregulation (MD miRNAs) and high dysregulation (HD miRNAs) both achieve similar performances of Lung Cancer (LC) diagnosis using machine learning techniques.

- <ins>Outcome:</ins> Study results are consistent with and support the hypothesis i.e., MD miRNAs have diagnostic potential comparable to HD miRNAs in LC.

## Key Findings

**I. Rethinking the Utility of miRNA Expression Levels in Diagnostics** (broad applicability)

- Quantitative significance alone does not necessarily indicate biological significance - regulatory complexity matters when considering expression level changes.

- Including MD miRNAs expands biomarker diversity - enhancing the understanding of biochemical mechanisms, early diagnosis, subclassification, prognosis assessment of diseases, and enable refining precision medicine approaches.

**II. Common/Similar Sequence Attributes of HD and MD miRNAs in LC**

- Despite their distinct dysregulation levels, common or similar sequence attribute values observed within a mixed cluster of HD and MD miRNAs, suggest similar or related regulatory roles - indicating some already known pathways in LC are being promoted in yet overlooked ways.

**III. Sequence Attributes Unique to Some Key MD miRNAs in LC**

- Multiple, densely populated clusters comprising only key MD miRNAs, are identified – sequence attribute values associated with these clusters unique to the MD category, convey novel information about the biochemical mechanisms of LC.

- miRNAs associated with these clusters are likely to provide valuable new insight into LC diagnosis, prognosis, drug research and treatment planning.

![Illustration of practical diagnostic benefit of the proposed approach.](/DiagnosticBenefitofProposedApproach.png)

# Significance

## Further Research Questions

- Which sequence attribute values are shared/similar between MD and HD miRNAs, and which others are unique to either category?
- How do these attribute values influence miRNA function e.g., target mRNAs, regulatory behavior, and disease mechanisms?
- Which other miRNAs possess same/similar attribute values and may, therefore, be relevant biomarkers?
- Can attribute values help predict miRNAs’ impact more robustly?
- How to explain ND category’s observed performance?

## Future Directions

- Investigate shared/similar sequence attribute values within the 13 mixed i.e., both HD and MD miRNA containing, as well as the 3 only MD miRNA containing clusters to, respectively, uncover common functional patterns and gain novel insights into LC-specific biochemical mechanisms.
- Map key HD and MD miRNAs to their target mRNAs, and, consequently, to the indicated pathways of the corresponding proteins.
- Revisit and refine some best performing contemporary LC diagnostic models by incorporating both HD and MD miRNAs.
- Validate current findings in the sample cases of some other diseases.

## Applications and Impact

- Conventionally neglected MD miRNAs shown to provide valuable clinical information for LC diagnosis. In view of miRNA action mechanisms being common and/or similar across diseases, similar results can be expected for other diseases. 
- The diversity and novel information provided by MD miRNAs enable
  - a more complete view of diseases’ biochemical mechanisms,
  - improved accuracy of diagnostic tools, prognosis and treatment response assessment,
  - enhanced precision medicine and personalized treatment strategies,
  - more successful therapeutic interventions.

# References

[1] Asakura, K., Kadota, T., Matsuzaki, J. et al. (2020). A miRNA-based diagnostic model predicts resectable lung cancer in humans with high accuracy. Communications Biology, 3(1), 1–9. https://doi.org/10.1038/s42003-020-0863-y

[2] Coding and Non-Coding RNA | Bio-Rad. (n.d.). Bio-Rad. https://www.bio-rad.com/en-us/applications-technologies/coding-non-coding-rna?ID=Q1070M70KWE7

[3] Cortez, M. A., Bueso-Ramos, C., Ferdin, J. et al. (2011). MicroRNAs in body fluids—the mix of hormones and biomarkers. Nature Reviews Clinical Oncology, 8(8), 467–477. https://doi.org/10.1038/nrclinonc.2011.76

[4] GEO Accession viewer. (2024). Nih.gov. https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE137140

[5] Ho, P. T. B., Clark, I. M., & Le, L. T. T. (2022). MicroRNA-Based Diagnosis and Therapy. International Journal of Molecular Sciences, 23(13), 7167. https://doi.org/10.3390/ijms23137167

[6] Hoerter, J. E., & Ellis, S. R. (2019, August 13). Biochemistry, Protein Synthesis. Nih.gov; StatPearls Publishing. https://www.ncbi.nlm.nih.gov/books/NBK545161/

[7] Liang, Z., Zhou, H., Zheng, H., & Wu, J. (2011). Expression levels of microRNAs are not associated with their regulatory activities. Biology Direct, 6(1), 43–43. https://doi.org/10.1186/1745-6150-6-43

[8] miRCarta - miRBase overview. (2018). Uni-Saarland.de. https://mircarta.cs.uni-saarland.de

[9] Nature Education. (2014). Protein Structure | Learn Science at Scitable. Nature.com. https://www.nature.com/scitable/topicpage/protein-structure-14122136/

[10] O’Brien, J., Hayder, H., Zayed, Y., & Peng, C. (2018). Overview of MicroRNA Biogenesis, Mechanisms of Actions, and Circulation. Frontiers in Endocrinology, 9(402).  https://doi.org/10.3389/fendo.2018.00402

[11] Scitable. (2009). Ribosomes, Transcription, Translation | Learn Science at Scitable. Nature.com. https://www.nature.com/scitable/topicpage/ribosomes-transcription-and-translation-14120660/

[12] Tian, S., Zhao, Z., Ren, B., & Wang, D. (2024). Non-Linear Relationship between MiRNA Regulatory Activity and Binding Site Counts on Target mRNAs. Data, 9(10), 111–111. https://doi.org/10.3390/data9100111

[13] Venneri, M., & Passantino, A. (2023). MiRNA: what clinicians need to know. European Journal of Internal Medicine, 113, 6–9. https://doi.org/10.1016/j.ejim.2023.05.024

[14] Zhang, W., Dahlberg, J. E., & Tam, W. (2007). MicroRNAs in Tumorigenesis. The American Journal of Pathology, 171(3), 728–738. https://doi.org/10.2353/ajpath.2007.070070

[15] Mukherji, S., Ebert, M. S., Zheng, G. X. Y. et al. (2011). MicroRNAs can generate thresholds in target gene expression. Nature Genetics, 43(9), 854–859. https://doi.org/10.1038/ng.905

[16] Yavropoulou, M. P., & Yovos, J. G. (2018). The “dark matter” of DNA and the regulation of bone metabolism: The role of non-coding RNAs. Journal of Musculoskeletal & Neuronal Interactions, 18(1), 18–31. https://www.researchgate.net/publication/323582989_The_dark_matter_of_DNA_and_the_regulation_of_bone_metabolism_The_role_of_non-coding_RNAs
