# Spam Ham Classifier
 Three Classifiers are trained to detect whether a text (sms) is spam or legitimate:
The current repository includes a jupyter notebook project which contains three different models trained off of SMS Spam Collection v.1 from UCI.
The file is firstly read into a data frame separating the texts from their lables. 
Some data preprocessing and feature engineering are applied to the data.
The data is cleaned and preprocessed as follows:
    1. made the text lower case
    2. removed links
    3. removed punctuations
    4. removed words with numbers
    5. removed stop-words
    6. Stemming
Then a stratified 5-fold cross validation are performed on the data (a stratified k-fold is proper for a data that is imbalanced) to perform the train test split.
Proper pipelines for three major machine learning algorithms for such a task are prepared and the data are trained on these pipelines.
Amongst those, Random Forest Classifier (100 estimators) performs best in terms of mean accuracy and std, plus the classification reports for all the folds. Naive Bayes is second in that. SVM performs worst among them.
