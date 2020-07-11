# Machine Learning to Predict Credit Risk
Resampling and ensemble learning using imbalanced-learn and Scikit-learn libraries to predict credit risk.

---

For this exercise several machine-learning models were used to predict credit risk based on free data from LendingClub.

The first approach was to resample the LendingClub data and build and evaluate logistic regression classifiers using the resampled data.

* Naive Random Oversampler and SMOTE algorithms were used as oversampling methods.
* The Cluster Centroids algorithm was used as the undersampling method.
* To apply a combined over and under sampling method the SMOTEEN algorithm was used.

The second approach was to train and compare two different ensemble classifiers to predict loan risk.

* Balanced Random Forest Classifier
* Easy Ensemble AdaBoost Classifier

---

### Resampling

##### RESULTS TABLE:
|   | Naive Random Oversampling  | SMOTE Oversampling  | Undersampling  | Combination (Over and Under) Sampling  |
|---|---|---|---|---|
| Balanced Accuracy Score  | 0.6512  | 0.6549  | 0.6549  | 0.5443  |
| Recall Score (avg/total)  | 0.56  | 0.69  | 0.42  | 0.57  |
| Geometric Mean Score (avg/total)  | 0.64  | 0.65  | 0.53  | 0.63  |

##### Which model had the best balanced accuracy score?
SMOTE Oversampling and Undersampling returned the same balanced accuracy score of 0.6549 tying for the best score.
>
> Naive Random Oversampling: 0.6512 <br />
> SMOTE Oversampling: 0.6549 <br />
> Undersampling: 0.6549 <br />
> Combination: 0.5443 <br />
##### Which model had the best recall score?
SMOTE Oversampling had the best average/total recall score of 0.69.
>
> Naive Random Oversampling: 0.56 <br />
> SMOTE Oversampling: 0.69 <br />
> Undersampling: 0.42 <br />
> Combination: 0.57 <br />
##### Which model had the best geometric mean score?
SMOTE Oversampling had the best average/total geometric mean score of 0.65.
>
> Naive Random Oversampling: 0.64 <br />
> SMOTE Oversampling: 0.65 <br />
> Undersampling: 0.53 <br />
> Combination: 0.63 <br />

---

### Ensemble Learning

##### RESULTS TABLE:
|   | Balanced Random Forest Classifier  | Easy Ensemble AdaBoost Classifier  |
|---|---|---|
| Balanced Accuracy Score  | 0.79  | 0.69  |
| Recall Score (avg/total)  | 0.87  | 1.00  |
| Geometric Mean Score (avg/total)  | 0.78  | 0.61  |

##### Which model had the best balanced accuracy score?
Random Forest had the best average/total geometric mean score of 0.79.
> Balanced Random Forest Classifier: 0.79 <br />
> Easy Ensemble AdaBoost Classifier: 0.69 <br />
##### Which model had the best recall score?
AdaBoost had the best average/total recall score of nearly 1.00.
> Balanced Random Forest Classifier: 0.87 <br />
> Easy Ensemble AdaBoost Classifier: 1.00 <br />
##### Which model had the best geometric mean score?
Random Forest had the best average/total geometric mean score of 0.78.
> Balanced Random Forest Classifier: 0.78 <br />
> Easy Ensemble AdaBoost Classifier: 0.61 <br />

##### What are the top three features?

##### Random Forest

The top three features for the Balanced Random Forest Classifier were total_rec_prncp, total_pymnt, and total_pymnt_inv as seen in this chart of results:

![Random Forest Features Importances](Resources/RandomForestTopFeatures.PNG)

##### AdaBoost

The top three features for Easy Ensemble AdaBoost Classifier were total_rec_int, last_pymnt_amnt, and issue_d_Jan_2019 as seen in this chart of results:

![AdaBoost Features Importances](Resources/AdaBoostTopFeatures.PNG)