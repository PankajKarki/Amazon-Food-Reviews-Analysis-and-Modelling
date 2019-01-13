# Amazon-Food-Reviews-Analysis-and-Modelling Using Various Machine Learning Models


#### Performed Exploratory Data Analysis, Data Cleaning, Data Visualization and Text Featurization(BOW, tfidf, Word2Vec). Build several ML models like KNN, Naive Bayes, Logistic Regression, SVM, Random Forest, GBDT etc.

### Objective:
Given a text review, determine the sentiment of the review whether its positive or negative.

Data Source: https://www.kaggle.com/snap/amazon-fine-food-reviews

#### About Dataset

The Amazon Fine Food Reviews dataset consists of reviews of fine foods from Amazon.<br>

Number of reviews: 568,454<br>
Number of users: 256,059<br>
Number of products: 74,258<br>
Timespan: Oct 1999 - Oct 2012<br>
Number of Attributes/Columns in data: 10 

Attribute Information:

1. Id
2. ProductId - unique identifier for the product
3. UserId - unqiue identifier for the user
4. ProfileName
5. HelpfulnessNumerator - number of users who found the review helpful
6. HelpfulnessDenominator - number of users who indicated whether they found the review helpful or not
7. Score - rating between 1 and 5
8. Time - timestamp for the review
9. Summary - brief summary of the review
10. Text - text of the review
<hr>

### 1 Amazon Food Reviews EDA, NLP, Text Preprocessing and Visualization using TSNE
1. Defined Problem Statement  
2. Performed Exploratory Data Analysis(EDA) on Amazon Fine Food Reviews Dataset plotted Word Clouds, Distplots, Histograms, etc.
3. Performed Data Cleaning & Data Preprocessing by removing unneccesary and duplicates rows and for text reviews removed html tags, punctuations, Stopwords and Stemmed the words using Porter Stemmer 
4. Documented the concepts clearly
5. Plotted TSNE plots for Different Featurization of Data viz. BOW(uni-gram), tfidf, Avg-Word2Vec and tf-idf-Word2Vec
<hr>

### 2 KNN
1. Applied K-Nearest Neighbour on Different Featurization of Data viz. BOW(uni-gram), tfidf, Avg-Word2Vec and tf-idf-Word2Vec 
2. Used both brute & kd-tree implementation of KNN 
3. Evaluated the test data on various performance metrics like accuracy also plotted Confusion matrix 
using seaborne

###### Performance Table
<img src="https://i.ibb.co/BBLy0KF/KNN.png" />

###### Conclusions:
1.  KNN is a very slow Algorithm takes very long time to train.
2.  Best Accuracy  is achieved by Avg Word2Vec Featurization which is of 79.789%.
3.  Both kd-tree and brute algorithms of KNN gives comparatively similar results.
4.  Overall KNN was not that good for this dataset.
<hr>


### 3 Naive Bayes
1. Applied Naive Bayes using Bernoulli NB and Multinomial NB on Different Featurization of Data viz. BOW(uni-gram), tfidf. 
2. Evaluated the test data on various performance metrics like accuracy, f1-score, precision, recall,etc. also plotted Confusion matrix using seaborne
3. Printed Top 25 Important Features for both Negative and Positive Reviews

###### Performance Table
<img src="https://i.ibb.co/ypkGnDF/NV.png" />

###### Conclusions:
1. Naive Bayes is much faster algorithm than KNN
2. The performance of bernoulli naive bayes is way much more better than multinomial naive bayes.
3. Best F1 score is acheived by BOW featurization which is 0.930
<hr>

### 4 Logistic Regression
1. Applied Logistic Regression on Different Featurization of Data viz. BOW(uni-gram), tfidf, Avg-Word2Vec and tf-idf-Word2Vec 
2. Used both Grid Search & Randomized Search Cross Validation
3. Evaluated the test data on various performance metrics like accuracy, f1-score, precision, recall,etc. also plotted Confusion matrix using seaborne
4. Showed How Sparsity increases as we increase lambda or decrease C when L1 Regularizer is used for each featurization<br>
5. Did pertubation test to check whether the features are multi-collinear or not

###### Performance Table
<img src="https://i.ibb.co/CQp51B7/REG.png" />

###### Conclusions:
1. Sparsity increases as we decrease C (increase lambda) when we use L1 Regularizer for regularization.
2. TF_IDF Featurization performs best with F1_score of 0.946 and Accuracy of 90.957.
3. Features are multi-collinear with different featurization.
4. Logistic Regression is faster algorithm.
<hr>

### 5 SVM
1. Applied SVM with rbf(radial basis function) kernel on Different Featurization of Data viz. BOW(uni-gram), tfidf, Avg-Word2Vec and tf-idf-Word2Vec 
2. Used both Grid Search & Randomized Search Cross Validation 
3. Evaluated the test data on various performance metrics like accuracy, f1-score, precision, recall,etc. also plotted Confusion matrix using seaborne
4. Evaluated SGDClassifier on the best resulting featurization

###### Performance Table
<img src="https://i.ibb.co/LShNsLt/SL.png" />
<img src="https://i.ibb.co/LShNsLt/SRBF.png" />

###### Conclusions:
1. BOW Featurization with linear kernel with random search gave the best results with F1-score of 0.943.
2. Avg-w2v Featurization with RBF Kernel (C=10, gamma=0.1) gave the best results with F1-score of 0.928
3. SVM with RBF kernel the separating plane exists in another space.
4. Using SGDClasiifier takes very less time to train.
<hr>

### 6 Decision Trees
1. Applied Decision Trees on Different Featurization of Data viz. BOW(uni-gram), tfidf, Avg-Word2Vec and tf-idf-Word2Vec 
2. Used both Grid Search with random 30 points for getting the best max_depth 
3. Evaluated the test data on various performance metrics like accuracy, f1-score, precision, recall,etc. also plotted Confusion matrix using seaborne
4. Plotted feature importance recieved from the decision tree classifier

###### Performance Table
<img src="https://i.ibb.co/cD6CcMf/DEc.png" />

###### Conclusions:
1. TFIDF Featurization(max_depth=17) gave the best results with accuracy of 85.328% and F1-score of 0.917.
2. Decision Trees on BOW and tfidf would have taken forever if had taken all the dimensions as it had huge dimension and hence tried with max 17 as max_depth
<hr>

### 6 Ensembles(RF&GBDT)
1. Applied Random Forest on Different Featurization of Data viz. BOW(uni-gram), tfidf, Avg-Word2Vec and tf-idf-Word2Vec 
2. Used both Grid Search with random 30 points for getting the best max_depth, learning rate and n_estimators. 
3. Evaluated the test data on various performance metrics like accuracy, f1-score, precision, recall,etc. also plotted Confusion matrix using seaborne
4. Plotted world cloud of feature importance recieved from the RF and GBDT classifier

###### Performance Table
<img src="https://i.ibb.co/9qTzZWs/Untitled.png" />
<img src="https://i.ibb.co/544v0j1/ensemblw.png" />

###### Conclusions:
1. AVG_W2VEC Featurization in Random Forest (BASE-LEARNERS=300) with random search gave the best results with F1-score of 0.924.
2. BOW Featurization in GBDT (BASE-LEARNERS=700, DEPTH=5, LEARNING-RATE=0.1) gave the best results with F1-score of 0.934.
<hr>

