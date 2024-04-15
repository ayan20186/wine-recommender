# wine-recommender

## Task Definition
Our broad task is to "learn the language of wine." More concretely, our aim is to build models that take as input the description of a wine by a wine expert and output:

Grape type: red or white (binary classification)
Grape variety (multi-class classification)
Similar wines (recommendation)
## Data and Features
# Dataset
Our data source is a Kaggle Featured Dataset containing over 150,000 wine reviews. We preprocessed the data by:

Censoring grape variety names from the review text
Filtering the dataset to only include grape varieties with at least 1,000 reviews
Removing reviews of blends and rosés
This left us with a dataset of just under 100,000 reviews and 24 unique grape varieties, with a 2/3 to 1/3 split of red vs. white wines.

## Features
We used the following feature types:

# Word Features: Features for every word in the reviews, after removing stop words
# Character n-gram Features: Features for every n-gram (sequence of n characters) in the reviews, after removing stop words
# word2vec Features: 400-dimensional vector representations of the review text, learned using a skip-gram model
# Supervised Learning
We evaluated the following models on our dataset:

1. Decision Tree
2. Random Forest
3. Naive Bayes
4. Logistic Regression
Our best model for Task 1 (grape type classification) achieved 99% test accuracy, and our best model for Task 2 (grape variety classification) achieved 76% accuracy.

# Wine Recommendations
We also developed an unsupervised approach to making wine recommendations. Given an input wine description, we use the word2vec features to compute a vector representation of the description, and then find the most similar wine descriptions based on cosine similarity.

## Understanding Grape Varieties through Unsupervised Learning
To gain insight into the relationships between different grape varieties, we used our word2vec features to embed each wine review in a 400-dimensional space. We then projected these embeddings onto a 2D plane using PCA and averaged the vectors by grape variety. This allowed us to visualize the relative distances between grape varieties, which we could then interpret in terms of characteristics like fruit aromas and bitterness/sweetness.

## Conclusion
By "learning the language of wine," we have developed models that can accurately classify wine type and variety, as well as recommend similar wines, based on the textual descriptions provided by wine experts. This project showcases our ability to apply state-of-the-art machine learning techniques to a real-world problem in the domain of wine analysis.
