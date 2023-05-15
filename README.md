# Surival analysis - Multiple Myeloma data challenge

I developed several models to predict the risk of mortality or relapse in newly diagnosed multiple myeloma patients, using baseline clinical and/or gene expression data. Firstly, I implemented a well-known model from the literature that utilizes a baseline Cox proportional hazards model and clinical variables such as age and ISS stage (https://doi.org/10.1038/s41375-020-0742-z). In my second model, instead of the Cox proportional hazards model, I utilized the random survival forests method and included age and ISS as explanatory variables. For my third model, I took inspiration from the second-place model in the multiple myeloma data challenge, which used a univariate approach to rank genes for feature selection in building expression-based models (https://doi.org/10.1038/s41375-020-0742-z). This model used a four-feature Cox proportional hazards model, incorporating variables such as age, ISS stage, and the expression of PHF19 and MMSE genes. In my fourth model, I employed LASSO regularization for the Cox model to select genes that contribute the most to the prediction, alongside variables such as age and ISS stages. In my fifth model, I chose to include only genes that have been reported to be associated with multiple myeloma (https://doi.org/10.1038/nrdp.2017.46). Finally, I compared all the models using the C-index and selected the best-performing model.

These were the steps I took:
- Pre-processed the RNA-seq data (filtered the most variable genes, log-transformed, and normalized to z-scores).
- Conducted unsupervised exploratory analysis to check for batch effects, using clustering and PCA of gene expression.
- Implemented a baseline Cox model incorporating age and ISS variables.
- Utilized a random survival forests model incorporating age and ISS variables.
- Implemented a Cox model incorporating age, ISS, and the expression of PHF19 and MMSE genes.
- Implemented a Cox model incorporating age, ISS, and gene expressions selected from the LASSO-based Cox model.
- Implemented a Cox model incorporating age, ISS, and selected gene expressions from gene pathways known to be associated with multiple myeloma.
- Assessed the performance of the models using the C-index and selected the best-performing model.
