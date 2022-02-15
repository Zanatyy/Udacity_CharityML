# Udacity_CharityML
### Question 1 - Naive Predictor Performace
* If we chose a model that always predicted an individual made more than $50,000, what would  that model's accuracy and F-score be on this dataset? You must use the code cell below and assign your results to `'accuracy'` and `'fscore'` to be used later.

** Please note ** that the the purpose of generating a naive predictor is simply to show what a base model without any intelligence would look like. In the real world, ideally your base model would be either the results of a previous model or could be based on a research paper upon which you are looking to improve. When there is no benchmark model set, getting a result better than random choice is a place you could start from.

** HINT: ** 

* When we have a model that always predicts '1' (i.e. the individual makes more than 50k) then our model will have no True Negatives(TN) or False Negatives(FN) as we are not making any negative('0' value) predictions. Therefore our Accuracy in this case becomes the same as our Precision(True Positives/(True Positives + False Positives)) as every prediction that we have made with value '1' that should have '0' becomes a False Positive; therefore our denominator in this case is the total number of records we have in total. 
* Our Recall score(True Positives/(True Positives + False Negatives)) in this setting becomes 1 as we have no False Negatives.

### Question 2 - Model Application
List three of the supervised learning models above that are appropriate for this problem that you will test on the census data. For each model chosen

- Describe one real-world application in industry where the model can be applied. 
- What are the strengths of the model; when does it perform well?
- What are the weaknesses of the model; when does it perform poorly?
- What makes this model a good candidate for the problem, given what you know about the data?

** HINT: **

Structure your answer in the same format as above^, with 4 parts for each of the three models you pick. Please include references with your answer.
**Decision Tree Classifier:**
- Real-world application: Can be used in manufacturing to evaluate decisions.
- Strengths: Performs classification without the need of data preparation since it can work *in theory* with categorical data and missing values.
- Weakness: Prone to overfitting.
- Candidacy: It has the ability to deal with both categorical and continous data. Also widely used in classification problems.

**Ensemble method (AdaBoost):**
- Real-world application: Customer Churn prediction. Also in features extraction in face detection.
- Strengths: Very good at boosting performance of weak learners (decision trees) on two class (binary) classification problems.
- Weakness: Noise and Outliers are problematic. You need to be careful with missclassifications in the data (Needs a quality dataset).
- Candidacy: We need to classify inputs into two classes (binary classification). Decision trees been used on this problem it had an acceptable performance but suffered overfitting. Generalizes better than RandomForests.

**Support Vector Machine:**
- Real-world application: used in bioinformatics with detecting genes, patients with genetic problems.
- Strengths: Works effictively with high dimensional data. Works well in the case of lack of data exploring.
- Weakness: Difficulty of choosing a suitable kernel. Very long training time.
- Candidacy: Any classification problems can be solved by SVM with the right kernel as it's known for its performance. Can work if we have high dimensional data.

### Question 3 - Choosing the Best Model

* Based on the evaluation you performed earlier, in one to two paragraphs, explain to *CharityML* which of the three models you believe to be most appropriate for the task of identifying individuals that make more than \$50,000. 

** HINT: ** 
Look at the graph at the bottom left from the cell above(the visualization created by `vs.evaluate(results, accuracy, fscore)`) and check the F score for the testing set when 100% of the training set is used. Which model has the highest score? Your answer should include discussion of the:
* metrics - F score on the testing when 100% of the training data is used, 
* prediction/training time
* the algorithm's suitability for the data.

**Answer:**
- AdaBoost is the most accurate with the highest f score with a relatively low training/predicting time.

### Question 4 - Describing the Model in Layman's Terms

* In one to two paragraphs, explain to *CharityML*, in layman's terms, how the final model chosen is supposed to work. Be sure that you are describing the major qualities of the model, such as how the model is trained and how the model makes a prediction. Avoid using advanced mathematical jargon, such as describing equations.

**Answer:**
Adaboost classifier begins with fitting a classifier to the 

