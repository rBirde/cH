# Spam Ham Classifier
Five distinct Classifiers are trained to detect whether a text (sms) is spam or legitimate.
## SMS Spam Collection Data Set
The SMS Spam Collection is a public set of SMS labeled messages that have been collected for mobile phone spam research. The dataset includes 5574 messages that are labeled as either "Ham" or "Spam". The classifiers are trained on this set of data to identify whether each message in a list of string objects is ham (legitimate) or spam. 
## Training the Spam Classifiers
The current repository includes a jupyter notebook project which contains five different models trained off of SMS Spam Collection v.1 from UCI.
The file is firstly read into a data frame separating the texts from their lables. 
Some data preprocessing and feature engineering are applied to the data.
On assessing the data, the main realization that is done, is that the classes present in the dataset ("ham" and "spam") are imbalanced. That means, the number of "ham" messages in the dataset are significantly higher than the number of spam messages. So, other than the accuracy of the models, one needs to keep an eye on the recall value for actual spam messages in the classification report as one need to have the least False Negatives for a class that have lower number of data in the dataset which in this case is "spam" messages. The other realization, is that the length of the spam messages turn to be longer than legitimate messages, and one could expect that. 

The data is cleaned and preprocessed as follows:

<ol>
  <li>made the text lower case</li>
  <li>removed links</li>
  <li>removed punctuations</li>
  <li>removed words with numbers</li>
  <li>removed stop-words</li>
  <li>Stemming</li>
</ol>

Then a stratified 5-fold cross validation are performed on the data (a stratified k-fold is proper for a data that is imbalanced) to perform the train test split.

A brief literature review of such a dataset, confirms that the most successful algorithms amongst Machine Learning Classifiers for such a task might be the following 
### Multinomial Naive Bayes
### Random Forest
### Support Vector Machine
### XGBoost

Proper pipelines for the machine learning algorithms for such a task are prepared and the data are trained on these pipelines.

Amongst the Machine Learning algorithms, XGBoost Random Forest Classifiers (100 estimators) perform best in terms of mean accuracy and std, plus the classification reports for all the folds (especially recall for "spam" class). Naive Bayes is third in that. SVM performs worst among them.


