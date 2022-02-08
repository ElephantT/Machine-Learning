# Diabetes risk assessment for insurance company (binary crossentropy - logloss)

### more info (ru) on [Kaggle](https://www.kaggle.com/c/competition-2-yandex-shad-spring-2021)

The purpose of this project is to learn how to build probabilistic models and optimize their parameters using the example of the problem of assessing
the risk of diabetes mellitus. We will look at the task of assessing the risk of illness from the perspective of an insurance company.

If a person stops being examined, and the insurance company does not find out if he has developed diabetes, then there will be no costs associated with his disease,
i.e. we can assume that such a person remained healthy. The same applies to people who are diagnosed with the disease for the first time after more than 5 years.

In order to calculate the expected cost of a client's treatment, the insurance company wants to get as a result of the model the probability that 
a person who does not suffer from a disease will develop it within 5 years. Therefore, binary cross entropy (aka logloss) between predicted probabilities 
and true class labels was chosen as a quality metric:

![image](https://user-images.githubusercontent.com/33278581/152930406-a63d8a47-d052-491f-addd-955f5d1872d8.png)

1. Data preprocessing and analysis
   - a lot of missing values problem
2. Baseline - constant prediction model (i took mean of probability distribution)
3. Big assumption on normal distribution of features and their conditional independence with respect to the target - Gaussian Naive Bayes. Log loss:
![image](https://user-images.githubusercontent.com/33278581/152932435-180ea076-6858-4dcf-98ef-94c35168072c.png)
4. Removing assumption on independence:
   - assuming that all classes share the same covariance matrix - LinearDiscriminantAnalysis
   - not assuimng that - QuadraticDiscriminantAnalysis
![image](https://user-images.githubusercontent.com/33278581/152933152-c7d33679-340e-4c78-8588-176a67fc1db2.png)
   - Why does we have syck results?:
   - The higher the dimension of the data set (the more predictors in a data set) the more parameters we have to estimate. This can lead to high variance and so we have to be careful when using QDA. In conclusion, LDA is less flexible than QDA because we have to estimate fewer parameters. This can be good when we have only a few observations in our training data set so we lower the variance. On the other hand, when the K classes have very different covariance matrices then LDA suffers from high bias and QDA might be a better choice. So, what is comes down to is the bias-variance trade-off. Therefore, it is crucial to test the underlying assumptions of LDA and QDA on the data set and then use both methods to decide which one is more appropriate. (https://thatdatatho.com/linear-vs-quadratic-discriminant-analysis/)

5. Logistic Regression - best result for now (log loss - 0.0612)
   - https://stats.stackexchange.com/questions/95247/logistic-regression-vs-lda-as-two-class-classifiers
   - For a two class classification problem, LDA predicts two normal density functions (one for each class) that creates a linear boundary where they intersect, whereas logistic regression only predicts the log-odd function between the two classes, which creates a boundary but does not assume density functions for each class.

![image](https://user-images.githubusercontent.com/33278581/152933913-568e8ad6-83f1-46ef-ad9e-4de057fc33f9.png)

6. Generalized Linear Models - no improving

7. Hazard function implementation (risk to get ill in time T if client was healthy before and healthy in moment T, non personalized metric)

8. Cox Proportional Hazard Model implementation (Hazard function + using features of each client)
   - sklearn template
   - check different weight init/regularizations/learning rates
   - optimizing likelihood function

![image](https://user-images.githubusercontent.com/33278581/152935069-70e7efc0-62ba-465d-b894-5b83622796fd.png)

![image](https://user-images.githubusercontent.com/33278581/152935262-d94c5a5d-94eb-444c-a57b-01d572a79f3c.png)

![image](https://user-images.githubusercontent.com/33278581/152935389-11bd36df-ddf8-4da2-a799-76b0c849bd65.png)

9. Stochastic Gradient Decent implementation - same analysis as for CPHM for point 8

![image](https://user-images.githubusercontent.com/33278581/152935625-bfbfb9dc-e517-4cbd-82fe-3690c0890707.png)

10. Implementation of Momentum-sgd + Adagrad-sgd + Adadelta-sgd

![gif](https://i.imgur.com/2dKCQHh.gif)

![gif](https://i.imgur.com/pD0hWu5.gif)

(https://imgur.com/a/Hqolp)

11. Calibration of classification models

![image](https://user-images.githubusercontent.com/33278581/152938623-9d8bfc00-2de0-4f29-bb67-ae2d5c604a22.png)

![image](https://user-images.githubusercontent.com/33278581/152938658-1e9b40bb-3800-4051-9e47-9f50dceeba88.png)




