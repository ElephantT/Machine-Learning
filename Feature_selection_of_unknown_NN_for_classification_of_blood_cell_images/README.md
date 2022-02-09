# Feature selection of unknown Neural Network for classification of blood cell images - top 7 (125 teams) [Kaggle](https://www.kaggle.com/c/competition-3-yandex-shad-spring-2021) result

### metric - AUC-ROC

Attention of current project was on feature selection, cause we have already 512 features
in vector as object, and we need to select only important using different strategies.

1. Univariate feature selection - connection between features and targets using univariate statistical tests:

![image](https://user-images.githubusercontent.com/33278581/153242044-0a8a2ab9-029a-4594-9f9a-830d8dca2499.png)

2. L1 for logistic regression as feature selection using it's coefficients:

![image](https://user-images.githubusercontent.com/33278581/153242295-166670d9-a5ea-4e5d-855c-feaa4793d0a3.png)

3. PCA - this technique showed #1 result on kaggle
4. KNN for feature selection

![image](https://user-images.githubusercontent.com/33278581/153242950-5baf41d9-3da2-4fa4-b2bf-4f7f09b940b9.png)
![image](https://user-images.githubusercontent.com/33278581/153242999-57ab5b5e-17f9-47ff-ad59-3432f4e4af2c.png)

5. Decision trees for feature selection

![image](https://user-images.githubusercontent.com/33278581/153243142-d264e861-85c8-4904-b436-941443620ca1.png)

6. Random forest for feature selection

![image](https://user-images.githubusercontent.com/33278581/153243261-e1a0070b-0573-4acd-b496-2243a75d57db.png)

7. SHAP values - strong technique (https://towardsdatascience.com/a-novel-approach-to-feature-importance-shapley-additive-explanations-d18af30fc21b) + kaggle article

![image](https://user-images.githubusercontent.com/33278581/153243507-3c7f913f-f691-40a4-b50e-14960bfa38aa.png)
![image](https://user-images.githubusercontent.com/33278581/153243655-fbb9ba3f-90bd-4b8d-9434-dc0199ec586e.png)

8. Comparing of different models on different subsets of features
9. Ansambles, stacking

![image](https://user-images.githubusercontent.com/33278581/153243890-c0ab6531-7ee7-4310-9cc4-56a0e93c4a4a.png)

10. Complex final model for kaggle - stacking of 8 different internally models with data transformation for each of them and probabilities calibration where it is needed

