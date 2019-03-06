Lending Club is a website which provides personal and business loans. They release information such as income, employment, loan status,
etc. on loan applications. In this project, all the approved loans from 2007 to the third quarter of 2018 which are either fully paid or 
charged off are investigated. The goal is to predict the probability of a personal loan to become charged off based on more than 1.25 
millions samples. This will help Lending Club have a better understanding of the risks of future applications. 

The dataset has 150 features. Features which are not available at the time a loan application is submitted, features with unique value for
each sample, and features with a single value across all samples are removed. Features with more than 50% missing values are removed only
if they are specific to primary applicant. Features specific to secondary applicant are removed if they have more than 50% null values
across joint applications. 

Some categorical features contain date or time; they are transformed to datetime format first, and then replaced with new features based
on the information extracted from them. Some categorical features have high cardinality problem; they are converted to numerical features
with the help of a method similar to the weight of evidence. The impact of remaining categorical features on the response variable is 
investigated by analyzing a pie plot and a bar plot; features with low impact are removed.

Highly correlated numerical features are identified with the help of heatmap. Only one feature from each group of highly correlated ones
is kept and the rest are removed. Also, some numerical features have quite large number of zeros; the impact of these features on the 
response variable is investigated by analyzing a count plot, and the features with low impact are removed. Outliers are capped and floored
by applying conservative thresholds. Missing values are addressed with an imputer.

Only 20% of the samples are charged-off. The imbalanced data problem is addressed by adjusting parameters of classifiers. Also, stratifed
folds are used in cross-validation processes. The stratified split is used to separate training and test sets too. The first used 
classifier is logistic regression. No improvement in recall score is observed after parameter tuning and also adding interaction terms.
The next classifier is XGBoost which shows higher accuracy and recall scores than the logistic regression. Parameter tuning slightly 
improves the recall score of the XGBoost classifier. Two different tricks of manipulating the features are also tested but no higher 
recall score is achieved. Next, the model is simplified by removing the features with low importance. At the end, recall and accuracy 
scores of the test set are computed. Both scores are quite close to the corresponding cross-validation scores of the training set.

Report: https://docs.google.com/document/d/1S99Rujjj_ekAYf4ji38Mi5q55JaPJedkUgKtO_ghLrU/edit?usp=sharing
Presentation: https://docs.google.com/presentation/d/1fE-CMOeFt8ID8lGjbXx7WgcoCMHSkhsF03v2rMzsqMI/edit?usp=sharing
