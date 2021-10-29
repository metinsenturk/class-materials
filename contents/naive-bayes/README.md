# Naive-Bayes Algorithm

## Introduction

Naive-bayes methods are a set of supervised algorithms that are based on Bayes' Theorem with the naive assumption. Naive assumption refers to the conditional independence between every pair of features and the class variable. For example, any object have a weight, color, dimension, etc. All of these features are tought to equally contribute to the probability of being the object. This equal contribution is the naive assumption of the algorithm.

Bayes theorem states that the conditional probability of an event A given the occurence of event B, is equal to the product of the likelihood of B and probability of A.


$$
P(A|B) = \dfrac{P(B|A)P(A)}{P(B)}
$$


Above probabilities also known as:

- P(A) - how likely A happens (prior knowledge - the probability of event before the evidence is seen)
- P(B) - how likely B happens (evidence)
- P(A|B) - posterior probability. probability of the hypothesis is true given the evidence
- P(B|A) - how likely B happens when A already happened (likelihood)



So, naive-bayes is a conditional probability model: It assigns instance probabilities of each possible outcomes given the n features. In the real world, you have more than one features. Therefore, above bayes rule can be written for all features as below:

$$
P(y \mid x_1, \dots, x_n) = \frac{P(y) P(x_1, \dots, x_n \mid y)}
                                 {P(x_1, \dots, x_n)}
$$

In simple terms, we can evaluate this as:

$$
P(Outcome | Evidence) (Posterior) = \frac{P(Prior) P(Likelihood of Evidence)}
                                 {P(Evidence)}
$$

There are different types of classifiers under naive bayes:

- **Gaussian**: Assumes features follow a normal distribution
- **Bernoulli**: For binary feature vectors. For example, if a word occurs in a sentence or not.
- **Multinomial**: For discrete counts. Instead of if the word occurs, we are interest in how many times it occured.



Applications of naive bayes algorithms are vast. Below areas are a few:

- **Real time prediction:** Due to being a fast in training and prediction, it could be used in real time predicitons.
- **Mutli-class prediction:** Target variables with more than 2 labels perform well.
- **Text classification (document classification, spam filtering, sentiment analysis):** Since it is a better multi-class classifier, they have a tendency to have higher success rates.
- **Recommendation systems:** Naive bayes classifiers could also be used in recommendation systems.

### Assumptions

- Each feature is independent of other
- Makes equal contribution to the target variable

### Advantages

- Performs well in multi-class prediction, easy and fast predictions for training and test datasets.
- Often very easy to interpret results
- Provides a straitforward probabilistic prediction
- It can be a good classifier for an initial baseline classifier.
- Can be used for both continuous and discrete data.
  
### Disadvantages

- If there is a category in test data that is not seen in training set, naive bayes algorithms will assign a 0 probability to the record. This is known a [Zero Frequency](https://datascience.stackexchange.com/a/15536/61094).
- Naive bayes algorithms makes an assumption for all predictors to be independent of each other. This assumption is almost impossible in the real world even tough it works.
- Naive bayes is a good classifier, but a bad estimator, so probability outputs should be interpretted carefully.

## References

- [Scikit learn's naive bayes model's introduction](https://scikit-learn.org/stable/modules/naive_bayes.html)
- [Understand the conditional probability with real world examples](https://towardsdatascience.com/bayes-theorem-101-example-solution-ff54147d6c7f)
- [Understand bayes theorem](https://www.cuemath.com/data/bayes-theorem/)
- https://www.machinelearningplus.com/predictive-modeling/how-naive-bayes-algorithm-works-with-example-and-full-code/