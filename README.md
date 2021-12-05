# Stroke-Detection
<b>Stroke Prediction Dataset</b><br>
Dataset include information about 5110 patients, each row represents patient information with label whether he got stroke or not. Based on dataset we try to train a model to get best predictor of patient having a risk of stroke.

Source:https://www.kaggle.com/fedesoriano/stroke-prediction-dataset<br>
Author:https://www.kaggle.com/fedesoriano

<b>Dataset Description</b><br><br>
Patients: 5110<br>
Non-Stroke:4861<br>
Stroke:249<br>
Stroke ratio:5.12%<bR>

  <b>Notebook Summary:</b><br>

Dataset is splitted to train set and holdout set, model is trained on train set, holdout set is used only for evaluation.

Dataset is very imbalanced, there are only 5.12% of stroke patients, in order to improve model training, training dataset is upsampled. Categorical features are encoded to numbers, numeric values are normalized to the same scale in order to improve model training.

  Notebooks are trigered in following order:<br>
    <i>1. Data_Exploration<br>
      2. Data_Preprocessing<br>
      3. Model_Evaluation</i>
  
 <b>Model and Metrics</b><br><br>
Model: <b>CatBoostClassifier</b><br>
Selected metric: <b>Recall</b><br><br>

<b>Train set:</b><br>
Accuracy: <b>78.74%</b><br>
Positive cases recall: <b>93%</b><br>
Positive cases precission: <b>73%</b><br>
Negative cases recall:<b>66%</b><br>
Negative cases precission:<b>90%</b><br><br>
<b>Classification Report</b>

              precision    recall  f1-score   support

           0       0.90      0.66      0.76       777
           1       0.73      0.93      0.82       777

    accuracy                           0.79      1554
  
<b>Holdout set:</b><br>
Accuracy: <b>67.5808%</b><br>
Positive cases recall: <b>0.84</b><br>
Positive cases precission: <b>0.12</b><br>
Negative cases recall:<b>0.67</b><br>
Negative cases precission:<b>0.99</b><br><br>
<b>Classification report</b><br>

              precision    recall  f1-score   support

           0       0.99      0.67      0.80       971
           1       0.12      0.84      0.20        50

    accuracy                           0.68      1021

  
Accuracy on holdout set is relatively low at 67.5808%, our main metrics recall however is up to 84%, which means that 84% of real positive cases were caught by model, which is much better metrics for evaluation for this imbalanced dataset. Our model must catch as many real positive cases as possible regardless accuracy is penalized.
  
