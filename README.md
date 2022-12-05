# Surival analysis - Multiple Myeloma data challenge

I developed a few models for predicting the risk of dying or relapsing of newly diagnosed multiple myeloma patients from baseline clinical and/or gene expression data. I performed a baseline Cox proportional hazards model known from the literature that uses clinical variables age and ISS stage (https://doi.org/10.1038/s41375-020-0742-z). In my second model, instead of the Cox proportional hazards I used random survival forests method and also used age and ISS as explanatory variables. My third model is inspired by the second place model from the multiple myeloma data challange that used a univariate approach to rank gene for feature selection in building expression based models (https://doi.org/10.1038/s41375-020-0742-z) - a four feature Cox proportional hazards model using variable age, ISS stage and expression of PHF19 and MMSE genes. In my fourth model, I used LASSO regularization for Cox model to select for genes that contribute to the prediction the most together with variables: age and ISS stages. In my fifth model, instead of using all genes for modelling, I selected genes that are reported to be associated with multiple myeolma based on a review publication in Nature on multiple myeloma (https://doi.org/10.1038/nrdp.2017.46). Lastly, I compared all the models using C-index and pick the best one that is the third model.

My steps:
-    Pre-processing of RNA-seq data (filtering the most variable genes, log-transformation and normalization to z-scores)
-    Unsupervised exploratory analysis to check for batch effects - clustering and PCA of gene expression
-    Baseline Cox model: age + ISS
-    Random survival forests model: age + ISS
-    Cox model: age + ISS + expression of PHF19 and MMSE genes
-    Cox model: age + ISS + selected gene expressions selected from the LASSO based cox model
-    Cox model: age + ISS + selected gene expressions from gene pathways known to be associated with multiple myeloma
-    Assess performance of all models and pick the best one
