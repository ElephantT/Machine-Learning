### Win prediction of DOTA 2 games - binary classification problem (ROC-AUC metric)

# additional info (ru) about project on [Kaggle](https://www.kaggle.com/c/competition-1-yandex-shad-spring-2021) 

What have been done in current project and its results:
1. Data preprocessing and analysis:
   ![image](https://user-images.githubusercontent.com/33278581/152741483-9b0bea7b-061a-46ae-94a2-49d0406fe5a7.png)
   - missing values:
   -- Conducted reaserch on how to deal with them in different cases
   - outliers detection:
   -- Used box-plots for each feature and used my understanding of the problem, what is possible and what is not
   - data scaling (conducted research on scaling impact for different models) -> for many models we need normalized data for different reasons:
   -- Linear Regression - problems: non-scaled data affecting gradients (exploding, vanishing) + derivatives on sigmoid functions
   -- SVM - problems: non-scaled data affecting distance measurments
   -- SVM with 'rbf' kernel - problems: features with bigger variation doesn't let model to train on features with less variation
   -- MLP - problems: non-scaled data affecting gradients (exploding, vanishing) + derivatives on activation function + local optimums
   -- NN - normilized data speeds up training process (gradients are not saturated on the start of the trainig + better internal optimization)
   - feature engineering:
   -- Different combinations of features + non-linear math functions for numerical features
   - feature selection:
   -- L1 regularization for Logistic Regression model for feature importance
2. Hyperparameters tuning (GridSearch, cross-validation):
![image](https://user-images.githubusercontent.com/33278581/152741749-1c5b9cd6-2491-4f38-896f-224a4be9e709.png)

3. Learning curves and analysis:
![image](https://user-images.githubusercontent.com/33278581/152741847-6a9660b3-21d2-4fea-8190-de164bdcfed2.png)


3. GridSearch, KFold, cross-validation, mean values and confidence intervals
4. data scaling, and why it is needed
5. Learning curves
6. One-hot-encoding for categorical data
7. Implementation of new classification model (by sklearn template) for blending different models
8. box-plots to compare probability distributions of each models


hyperparameter tuning (grid search, ; cross-validation/train-val-test splits; conducting correct experiments; how to compare different models
