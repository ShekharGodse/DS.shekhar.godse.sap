
•	To protect the user's identity and the security of their confidential information, the dataset provider has applied Principal Component Analysis transformation on the original numerical features and compressed it into 28 principals components.
•	Only two features have not been transformed i.e. 1) Time and 2) Amount
•	The feature class will be target column with user labels as:
	0 : non-fradulent
	1 : fraudulent
•	The barplot reveals a significant imbalance between classes (0-Non Fradulent) and (1-Fraudulent).
•	Majority of features are in PCA form , with the exceptions being Time and Amount ,a more in-depth examination of these two features is required.
•	The feature we are most interested in is the "Amount". Here us the summary of the feature.
•	We will initiate the visualization of transaction counts across hours, starting with the entire dataset. Subsequently, we will partition the dataset into fraudulent and non-fradulent transactions to gain a more detailed perspective.
•	Now we will check the number of occurances of each class label and we will plot the information using matplotlib.
•	We can observe that the genuine transactions are over 99%.
•	We will apply scaling techniques on the "Amount" feature to transform the range of values.
•	We will drop the original "Amount" column and add a new column with the scaled values. We will also drop the "Time" columns as it is irrelevant.
•	Now, we will split the credit card data with a split of 70-30 using train_test_split().
•	train_test_split() function in scikit-learn is a useful utility for splitting a dataset into training and testing sets.
•	Parameters
•	X: Feature matrix
•	Y: Target variable
•	test_size: Proportion of the dataset to include in the test split. Here we have set the test_size as 0.3 means 30% of the data we take as testing data set.
•	random_state: we have set the seed for random number generation, to ensure the reproducibility



## Applying Machine Learning Algorithm to Credit Card Dataset
•	We will explore various machine learning algorithms to determine the most effective model for our binary classification problem.
•	The task involves predicting one of the two class labels. We plan to access the performance of different algorithms, such as Random Forest and Decision Tree identify the most suitable solution for our specific problem
•	Our approach involves constructing Random Forest and Decision Tree classifiers to identify the most effective model.


## Decision Tree Algorithm
•	The Decision Tree Algorithm is a supervised machine learning technique employed for both classification and regression tasks. Its objective is to create a training model capables of predicting the value of a target class variable.
•	This is achieved by learning straighforward if-then-else decision rules derived from the patterns present in the training data.


## Decision Tree Algorithm
•	The Decision Tree Algorithm is a supervised machine learning technique employed for both classification and regression tasks. Its objective is to create a training model capables of predicting the value of a target class variable.
•	This is achieved by learning straighforward if-then-else decision rules derived from the patterns present in the training data.


## Random Forest Algorithm
•	Random Forest is supervised Machine Learning algorithm. It creates a "forest" out of an ensemble of "decision trees", which are normally trained using the "bagging" technique.
•	The bagging method's basic principal is that combining different learning models improved the outcome.To get a more precise and reliable forecast, random forest creates several decision trees and merges them.
•	Here we are creating a RandomForestClassifier with 100trees in the forest.
•	The large number of trees will generally lead to better performance, but it may also increase the training time.
•	Now we will check the score of the Decision Tree model
•	The Random Forest classifier has slightly an edge over the Decision Tree Classifier.

## Evaluation Metrics
•	We will create a function to print the metrics:
1.	Accuracy_score
2.	Precision_score
3.	Confusion_matrix
4.	Recall_score
5.	F-1 score
We understand from the confusion matrix:
•	Non-Fraudulent transactions:
1.	Correctly predicted as non-fraudulent(True Negative) 85260 transactions.
2.	Incorrectly predicted as fraudulent(False Positive) 47 transactions.
•	Fraudulent Transactions:
1.	Incorrectly predicted as non-fraudulent(False Negative) : 23 transactions
2.	Correctly predicted as fraudulent(True Positive) : 113 transactions
In-short summary:
•	The model correctly identified 113 fraudulent transactions.
•	It incorrectly identified 23 transactions as non-fraudulent.
•	It correctly identified 85260 non-fraudulent transactions.
•	It incorrectly identified 47 non-fraudulent transactions as fraudulent.
We understand from the confusion matrix:
•	Non-Fraudulent transactions:
1.	Correctly predicted as non-fraudulent(True Negative) 85302 transactions.
2.	Incorrectly predicted as fraudulent(False Positive) 5 transactions.
•	Fraudulent Transactions:
1.	Incorrectly predicted as non-fraudulent(False Negative) : 27 transactions
2.	Correctly predicted as fraudulent(True Positive) : 109 transactions
In-short summary:
•	The model correctly identified 109 fraudulent transactions.
•	It incorrectly identified 27 transactions as non-fraudulent.
•	It correctly identified 85302 non-fraudulent transactions.
•	It incorrectly identified only 5 non-fraudulent transactions as fraudulent.
Class-Imbalance
•	The Random Forest model works better than Decision Trees. In the presenece of a class-Imbalance issue, where genuine transactions account for over 99% of the dataset and credit card fraud transactions constitute only 0.17%.
•	Training the model without addressing the imbalance can lead to biased predictions.
•	Despite the apparent accuracy, such a model may not effectively capture the nuances of the minority class (fraud transactions) and may not generalize well to real-world situations.
•	The class imbalance problem can be solved by various techniques. Oversampling is one of them.
•	Given that the Random Forest Algorithm outperformed the Decision Tree Algorithm, we will now apply the Random Forest algorithm to our resampled data.
We understand from the confusion matrix:
•	Non-Fraudulent transactions:
Correctly predicted as non-fraudulent(True Negative) 85131 transactions.
Incorrectly predicted as fraudulent(False Positive) 17 transactions.
•	Fraudulent Transactions:
Incorrectly predicted as non-fraudulent(False Negative) : 0 transactions
Correctly predicted as fraudulent(True Positive) : 85440 transactions
We understand from the confusion Matrix is:
•	The model correctly identified 85440 fraudulent transactions.
•	It incorrectly identified 0 transactions as non-fraudulent.
•	It correctly identified 85131 non-fraudulent transactions.
•	It incorrectly identified only 17 non-fraudulent transactions as fraudulent.
We can see that our model performed much better than the previous Random Forest classifier without oversampling.
We have applied the techniques to address the class imbalance issues and achieved an accuracy of more than 99%.
•	We will import the pickle to dump the dataframe and the model for the model deployement as the future scope.


## Results
The best results are achieved by over-sampling the under-represented class using SMOTE (synthetic minority oversampling technique).
With this approach, the model is able to detect 100% of all fraudulent transactions in the unseen test set. This fully satisfies the primary objective to detect the vast majority of abnormal transactions. Please note that the technique and model used are simple to implement simple, easy to use and can be updated in real-time.

In addition, the number of false positive remains acceptable. This means a lot less verification work (on legitimate transactions) for the fraud departement compare dto some other approaches which failed on this aspect. Key results are shown below:
