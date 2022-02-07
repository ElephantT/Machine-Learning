# Win prediction of DOTA 2 games - binary classification problem (AUC-ROC metric)

#### additional info (ru) about project on [Kaggle](https://www.kaggle.com/c/competition-1-yandex-shad-spring-2021) 

What have been done in current project and its results:
1. Data preprocessing and analysis:
   ![image](https://user-images.githubusercontent.com/33278581/152741483-9b0bea7b-061a-46ae-94a2-49d0406fe5a7.png)
   - missing values:
     - Conducted reaserch on how to deal with them in different cases
   - outliers detection:
     - Used box-plots for each feature and used my understanding of the problem, what is possible and what is not
   - data scaling (conducted research on scaling impact for different models) -> for many models we need normalized data for different reasons:
     - Linear Regression - problems: non-scaled data affecting gradients (exploding, vanishing) + derivatives on sigmoid functions
     - SVM - problems: non-scaled data affecting distance measurments
     - SVM with 'rbf' kernel - problems: features with bigger variation doesn't let model to train on features with less variation
     - MLP - problems: non-scaled data affecting gradients (exploding, vanishing) + derivatives on activation function + local optimums
     - NN - normilized data speeds up training process (gradients are not saturated on the start of the trainig + better internal optimization)
   - feature engineering:
     - Different combinations of features + non-linear math functions for numerical features
   - feature selection:
     - L1 regularization for Logistic Regression model for feature importance
2. Hyperparameters tuning (GridSearch, cross-validation):
3. Learning curves and analysis:
![image](https://user-images.githubusercontent.com/33278581/152741847-6a9660b3-21d2-4fea-8190-de164bdcfed2.png)
4. Final model: implemented with sklearn template blend model of different classifiers
5. For model comparing I used box-plots, to see and check probability distributions of each model
