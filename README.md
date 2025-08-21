## **Supplementary Methods: Multi-Biofluid Metabolomics Analysis for Alzheimer's Disease and Dementia with Lewy Bodies**

To elucidate metabolic alterations associated with Alzheimer's disease (AD) and , we developed and implemented an R-based computational pipeline to analyze targeted metabolomics data from both serum and urine using the Biocrates AbsoluteIDQ® p400 platform. This integrated pipeline was designed to identify disease-specific metabolic signatures, assess biofluid-specific differences, and support biomarker discovery across clinical phenotypes.

------------------------------------------------------------------------

### **1. Data Preprocessing and Quality Control**

All raw data from the Biocrates platform were processed using standardized nomenclature consistent with the AbsoluteIDQ® p400 assay. Metabolite names were harmonized across serum and urine matrices to ensure cross-biofluid comparability. Preprocessing steps included:

-   **Log₂ transformation** of metabolite concentrations to normalize distributions and stabilize variance.
-   **Normalization within biofluid** to control for batch effects and inherent differences in concentration ranges.
-   **Missing value filtering**, removing metabolites with \>30% missingness per group, followed by imputation or case-wise deletion as appropriate.
-   Metabolite intensities were subjected to **scaling and centering**, ensuring compatibility with multivariate methods.

This data preprocessing facilitated accurate downstream statistical modeling and minimized technical artifacts.

------------------------------------------------------------------------

### **2. Statistical Analysis**

#### **Univariate Analysis**

We performed an analysis of variance (ANOVA) for each metabolite across diagnostic groups (AD, DLB, and cognitively normal controls). Where significant effects were observed, **Tukey's HSD** post-hoc tests were applied to identify pairwise group differences.

To correct for multiple hypothesis testing, **Benjamini-Hochberg false discovery rate (FDR)** correction was employed. Effect sizes were quantified using **eta-squared (η²)**, providing insight into the magnitude of group-level differences beyond p-values.

#### **Multivariate Analysis**

We implemented:

-   **Principal Component Analysis (PCA)** to reduce dimensionality and visualize clustering based on metabolic profiles.
-   **Partial Least Squares Discriminant Analysis (PLS-DA)** for supervised classification of diagnostic groups using metabolomic features.

To ensure model robustness, **5-fold cross-validation** was employed, and variable importance in projection (VIP) scores were computed to identify key discriminative metabolites.

------------------------------------------------------------------------

### **3. Metabolite Classification and Chemical Categorization**

All detected metabolites were systematically classified into biologically relevant chemical classes, facilitating functional interpretation and pathway mapping. Classes included:

-   **Acylcarnitines**
-   **Amino acids**
-   **Biogenic amines**
-   **Phospholipids** (e.g., phosphatidylcholines, lysophosphatidylcholines, sphingomyelins)
-   **Lipids** (e.g., triglycerides, diglycerides, cholesteryl esters)

This classification was used to assess group-wise trends and to support metabolite set enrichment analysis.

------------------------------------------------------------------------

### **4. Visualizations and Figures**

The pipeline generates a suite of **visualizations** including:

-   **Demographic plots** showing sample characteristics (age, sex, APOE status)
-   **PCA and PLS-DA plots** highlighting group separation
-   **Volcano plots** displaying log₂ fold-change versus –log₁₀ p-values for all metabolites
-   **Heatmaps** of top-ranked discriminative metabolites, stratified by group
-   All visual outputs are provided in **PDF and PNG** formats suitable for inclusion in manuscripts or presentations.

------------------------------------------------------------------------

### **5. Biomarker Discovery Framework**

To support the identification of potential metabolic biomarkers for AD:

-   Univariate significance (FDR-adjusted p-values), **effect sizes**, and **VIP scores** from multivariate models were integrated.
-   Metabolites consistently ranked across univariate and multivariate methods were prioritized as candidate biomarkers.
-   **Cross-biofluid comparisons** were conducted to validate biomarker consistency and assess systemic vs. biofluid-specific metabolic signatures.

------------------------------------------------------------------------

### **6. Pathway and Metabolite Set Enrichment**

We conducted **metabolite class enrichment analysis** to identify pathways disproportionately represented among significantly altered metabolites. This included:

-   Comparison of enrichment patterns between serum and urine
-   Identification of metabolic pathways related to **energy metabolism**, **lipid regulation**, **amino acid turnover**, and **neurotransmitter synthesis**
-   Emphasis on pathways previously implicated in **neurodegeneration**, **oxidative stress**, and **mitochondrial dysfunction**

Pathway-level interpretation was supported by curated databases and literature-based annotations.

------------------------------------------------------------------------

### **7. Output Structure and Export**

All results are exported into a structured output directory (`metabolomics_results/`), including:

-   **CSV files** for all statistical results (p-values, effect sizes, VIP scores)
-   **Visual figures** in high-resolution formats
-   **Cross-validation metrics** for model performance
-   **Summary reports** detailing key findings per biofluid

------------------------------------------------------------------------

### **Clinical and Translational Relevance**

This pipeline enables comprehensive metabolic profiling of clinical cohorts and is particularly suited for early-stage biomarker discovery in neurodegenerative diseases. It supports:

-   Identification of **disease-specific metabolic fingerprints** (AD vs. DLB vs. CN)
-   Exploration of **biofluid-specific alterations** and inter-biofluid correlations
-   Construction of **multi-metabolite panels** for classification and diagnosis
-   Functional interpretation through **pathway-centric analysis**

By combining statistical modeling with interpretability and visualization, this pipeline provides a framework for metabolomics research in clinical neuroscience.
