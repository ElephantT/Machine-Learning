# Diabetes risk assessment for insurance company (binary crossentropy - logloss)

### more info (ru) on [Kaggle](https://www.kaggle.com/c/competition-2-yandex-shad-spring-2021)

The purpose of this project is to learn how to build probabilistic models and optimize their parameters using the example of the problem of assessing
the risk of diabetes mellitus. We will look at the task of assessing the risk of illness from the perspective of an insurance company.

If a person stops being examined, and the insurance company does not find out if he has developed diabetes, then there will be no costs associated with his disease,
i.e. we can assume that such a person remained healthy. The same applies to people who are diagnosed with the disease for the first time after more than 5 years.

In order to calculate the expected cost of a client's treatment, the insurance company wants to get as a result of the model the probability that 
a person who does not suffer from a disease will develop it within 5 years. Therefore, binary cross entropy (aka logloss) between predicted probabilities 
and true class labels was chosen as a quality metric:

<p align="center">
  <img src="https://user-images.githubusercontent.com/33278581/152930406-a63d8a47-d052-491f-addd-955f5d1872d8.png">
</p>
