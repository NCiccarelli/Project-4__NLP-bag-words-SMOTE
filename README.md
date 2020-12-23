# Project-4__NLP-bag-words-SMOTE

**Summary: In this Jupyter notebook Sentiment Analysis for the Amazon Software dataset using Bag-of-Words and using SMOTE (Synthetic Minority Over-sampling Technique).**

The Amazon Softare dataset is taken from this link: https://nijianmo.github.io/amazon/index.html 

We use BOW (Bag-of-Words) to perform Sentiment Analysis. 

We use two sources of data: 

(1) one zip file -i.e., "Software.json.gz"- contain the main dataset, and it contains the reviews of the clients;

(2) another zip file -i.e., "meta_Software.json.gz"- contains the "title" of the product (i.e., the name of the product), and it contains the brand of the product and the main category of the product. 

The two datasets are merged together using the product ID which is included in both datasets. 

Description of the main variables in the main dataset (i.e., "Software.json.gz"): 

- reviewerID - ID of the reviewer, e.g. A2SUAM1J3GNN3B
- asin - ID of the product, e.g. 0000013714
- reviewerName - name of the reviewer
- summary - summary of the review
- reviewText - text of the review
- overall - rating of the product
- unixReviewTime - time of the review (unix time)
- reviewTime - time of the review (raw)

Description of the main variables in the metadata dataset (i.e., "meta_Software.json.gz"): 

- asin - ID of the product, e.g. 0000013714
- title - name of the product
- brand - brand name
- main_cat - main category of the product (e.g., "Software"; "All Electronics")

These sections are included in this Jupyter notebook: 
- In Section 1 we prepare the two datasets and we merge them using the product ID.  
- In Section 2 we create the binary rating variable. The binary rating variable is used as the target of the BOW (bag-of-words) model in the following sections. 
- In Section 3 we apply pre-processing to the clients' reviews. We delete stopwords and numbers, and we use lower-case letters for all reviews; we remove punctuation, and we apply lemmatization. 
- In Section 4 we perform Sentiment Analysis. In Section 4 we use Grid search (i.e., GridSearchCV) in order to select the best (most predictive) model. We also use a pipeline within GridSearchCV. 
- In Section 5 we use grid search together with SMOTE (Synthetic Minority Over-sampling Technique); in this section we use the unbalanced dataset, and we correct unbalancedness through the use of SMOTE. 
- In Section 6 we draw a few conclusions about the effect of SMOTE on the "precision" and the "recall" of the estimator. 
