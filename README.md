# E-Commerce-Product-Text-Classification

## Overview
This is an NLP project for predicting the category of e-commerce items from the description of the products. There are four categoreis which are Household, Books, Electronics dan Clothing & Accessories. Various vectorization techniques and machine learning models are used. The vectorizer TF-IDF and bag of words are used and the machine learning models SVC and Random Forest are used resulting in a combined total of 4 models tested.

## Data
The data is 12.000 rows of text data which contains four cateogires of e-commerce products, each entry is a text description of the products and an associated label

## Approaches and Techniques

### Preprocessing
Preprocessing is done using the re and nltk libraries
* Cleaning
* Tokenization
* Stopword Removal
* Lemmatization
  
### EDA
The most common words in the dataset after being preprocessed is shown in a bar graph
![image](https://github.com/user-attachments/assets/b95cefcc-1814-4e23-834c-1d9eecc4e315)

### Vectorization
* TF-IDF
  
TF-IDF (Term Frequency-Inverse Document Frequency) is a method used to assess how important a word is in a document relative to the rest of the document. TF measures the frequency of a word in a document, while IDF measures how common or rare that word is across the corpus; the combination of the two gives higher weight to more informative words.

* Bag of Words
  
Bag of Words (BoW) is a text representation model that ignores the order of words and only considers the frequency of occurrence of words in a document. In this model, each document is represented as a vector of the number of occurrences of unique words in the corpus.

### Hyperparameter Tuning
The the models used are tuned using the sklearn library. A random search algorithm is used to find the best reasonable values for certain parameters.

Tuned parameters for random forest models
* n_estimators: [50, 100, 150], 
* max_features: ['sqrt', 'log2'], 
* criterion:['gini', 'entropy']

Tuned parameters for SVC models
* C: [0.1, 1, 10],  
* gamma: [1, 0.1, 0.01, 'scale'], 
* kernel: ['rbf', 'linear', 'sigmoid'] 


### Result
A table of the results of the trained models with tuned parameters

![image](https://github.com/user-attachments/assets/56bdb5da-d297-4e67-9f5d-c407d370452d)


### Conclusion

It can be seen that both algorithms if TF-IDF produces better performance than bag of words. This is because TF-IDF is more holistic when considering the value of a word, considering the entire corpus compared to bag of words which only uses word frequency without any additional context. The comparison of random forest and SVM is not too far if you take the best for both, which is 95%, where the difference in some metrics is very small so it can be said to be negligible.
