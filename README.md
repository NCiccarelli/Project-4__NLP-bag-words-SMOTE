# Project-4: NLP (Natural Language Processing) & Bag-of-words model

**Summary: In this Jupyter notebook we perform Sentiment Analysis for the Amazon Software dataset using the Bag-of-Words model and using SMOTE (Synthetic Minority Over-sampling Technique).**

The Amazon Softare dataset is obtained from this website: https://nijianmo.github.io/amazon/index.html 

We use two sources of data: 

(1) Two zip files -i.e., "Software_df1.json.gz" and "Software_df2.json.gz"- contain the main dataset. These two zip files contain the reviews of the clients and contain the rating for each product;

(2) Another zip file -i.e., "meta_Software.json.gz"- contains the "title" of the product (i.e., the name of the product). It also contains the brand of the product and the main category of the product. 

The three datasets are merged together using the product ID which is included in all datasets. 

Description of the main variables in the main dataset: 

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
- In Section 4 we perform Sentiment Analysis. In Section 4 we use Grid search (i.e., GridSearchCV) in order to select the best model -i.e., the model with the highest predictive power. We also use a pipeline within GridSearchCV. 
- In Section 5 we use grid search together with SMOTE (Synthetic Minority Over-sampling Technique); in this section we use the unbalanced dataset, and we correct the unbalancedness of the dataset through the use of SMOTE. 
- In Section 6 we draw a few conclusions about the effect of SMOTE on the "precision" and the "recall" of the estimator. 
