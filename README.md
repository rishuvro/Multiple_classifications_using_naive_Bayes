# Multiple_classifications_using_naive_Bayes
## Introduction

Multiple classifications using Naive Bayes is a machine learning technique for classifying instances into one of several categories. It assumes that features are independent of each other given the class label. The algorithm calculates probabilities for each class and assigns the instance to the class with the highest probability. Naive Bayes classifiers are simple, efficient, and commonly used for tasks like spam detection or document classification. However, they assume independence between features, which may only sometimes hold true.

**Definition:** Multiple classifications using Naive Bayes is a machine learning algorithm that can be used for classifying data into multiple classes.

- Naive Bayes is a probabilistic algorithm for multi-class classification problems.
- Naive Bayes assumes that features are independent of each other. Despite this oversimplification, it performs well in practice.
- Naive Bayes calculates the probability of each class given input features using Bayes' theorem.
- For multiple classifications, Naive Bayes can use a one-vs-all or one-vs-one approach to choose the final predicted class.
- Naive Bayes is commonly used for text classification problems.

## Example
##mail classification
Suppose we have a dataset of emails, where each email is classified as either "spam", "ham" (not spam), or "promo" (promotional email). We want to classify a new email based on its text content.

**Training data:**

| Total emails | Spam | Ham | Promo |
|--------------|------|-----|-------|
| 10           | 4    | 4   | 2     |

**Example of new email:**
"Congratulations! You have won a free vacation. Click here to claim your prize."

To classify this email using Naive Bayes, we first need to preprocess the data by tokenizing the text and removing stop words.
Tokenized email:

Congratulations
won
free
vacation
Click
claim
prize

Now, we calculate the prior probabilities of each class:

- P(spam) = 4/10 = 0.4
- P(ham) = 4/10 = 0.4
- P(promo) = 2/10 = 0.2

Now, we calculate the conditional probabilities of each word given each class:

- P("Congratulations" | spam) = 1/16 = 0.0625
- P("Congratulations" | ham) = 1/12 = 0.0833
- P("Congratulations" | promo) = 0/5 = 0
- P("won" | spam) = 1/16 = 0.0625
- P("won" | ham) = 1/12 = 0.0833
- P("won" | promo) = 0/5 = 0
- P("free" | spam) = 1/16 = 0.0625
- P("free" | ham) = 0/12 = 0
- P("free" | promo) = 1/5 = 0.2
- P("vacation" | spam) = 1/16 = 0.0625
- P("vacation" | ham) = 0/12 = 0
- P("vacation" | promo) = 1/5 = 0.2
- P("Click" | spam) = 1/16 = 0.0625
- P("Click" | ham) = 0/12 = 0
- P("Click" | promo) = 1/5 = 0.2
- P("claim" | spam) = 1/16 = 0.0625
- P("claim" | ham) = 0/12 = 0
- P("claim" | promo) = 1/5 = 0.2
- P("prize" | spam) = 1/16 = 0.0625
- P("prize" | ham) = 0/12 = 0
- P("prize" | promo) = 1/5 = 0.2

Using the probabilities calculated previously, the posterior probabilities of the email belonging to each class are:

- P(spam | email) = P("Congratulations" | spam) * P("won" | spam) * P("free" | spam) * P("vacation" | spam) * P("Click" | spam) * P("claim" | spam) * P("prize" | spam) * P(spam) = 0.0625 * 0.0625 * 0.0625 * 0.0625 * 0.0625 * 0.0625 * 0.0625 * 0.4 = 0.0000008
- P(ham | email) = P("Congratulations" | ham) * P("won" | ham) * P("free" | ham) * P("vacation" | ham) * P("Click" | ham) * P("claim" | ham) * P("prize" | ham) * P(ham) = 0.0833 * 0.0833 * 0 * 0 * 0 * 0 * 0 * 0.4 = 0
- P(promo | email) = P("Congratulations" | promo) * P("won" | promo) * P("free" | promo) * P("vacation" | promo) * P("Click" | promo) * P("claim" | promo) * P("prize" | promo) * P(promo) = 0 * 0 * 0.2 * 0.2 * 0.2 * 0.2 * 0.2 * 0.2 = 0

Therefore, based on the highest posterior probability, the email is classified as "spam".


## vechicle identify

Example:

Given a new vehicle with the following features: Horsepower = 180,
Weight = 2800 lbs, Max Speed = 135 mph, what is the most likely class
for this vehicle using multiple classifications with Naive Bayes?

| **Instance** | **Horsepower** | **Weight (lbs)** | **Max Speed (mph)** | **Class**  |
|--------------|----------------|------------------|---------------------|------------|
| 1            | 200            | 3000             | 140                 | Car        |
| 2            | 150            | 2500             | 130                 | Car        |
| 3            | 100            | 1000             | 90                  | Motorcycle |
| 4            | 80             | 800              | 85                  | Motorcycle |
| 5            | 300            | 5000             | 120                 | Truck      |
| 6            | 250            | 4500             | 110                 | Truck      |
| 7            | 180            | 2800             | 135                 | Car        |

We want to classify a new vehicle with the following features:

Horsepower = 180, Weight = 2800 lbs, Max Speed = 135 mph.

Let's begin:

using the formula P(X) = Number of X instances / Total number of
instances.

| **Vehicle** | **Number of Instances** | **Total Instances** | **Probability**             |
|-------------|-------------------------|---------------------|-----------------------------|
| Car         | 3                       | 7                   | P(Car) = 3 / 7 = 3/7        |
| Motorcycle  | 2                       | 7                   | P(Motorcycle) = 2 / 7 = 2/7 |
| Truck       | 2                       | 7                   | P(Truck) = 2 / 7 = 2/7      |

the probabilities of each feature:

For Horsepower:

| **Vehicle** | **Number of Instances** | **Total Instances** | **P(Horsepower = 180 \| Vehicle)** |
|-------------|-------------------------|---------------------|------------------------------------|
| Car         | 3                       | 7                   | 1/3                                |
| Motorcycle  | 2                       | 7                   | 0                                  |
| Truck       | 2                       | 7                   | 0                                  |

For weight,

| **Vehicle** | **Number of Instances** | **Total Instances** | **P(Weight = 2800 \| Vehicle)** |
|-------------|-------------------------|---------------------|---------------------------------|
| Car         | 3                       | 7                   | 2/3                             |
| Motorcycle  | 2                       | 7                   | 0                               |
| Truck       | 2                       | 7                   | 0                               |

For Max Speed:

| **Vehicle** | **Number of Instances** | **Total Instances** | **P(Max Speed = 135 \| Vehicle)** |
|-------------|-------------------------|---------------------|-----------------------------------|
| Car         | 3                       | 7                   | 1/3                               |
| Motorcycle  | 2                       | 7                   | 0                                 |
| Truck       | 2                       | 7                   | 0                                 |

\- Calculate each class:

| **Class**  | **P(Class)** | **P(180 \| Class)** | **P(2800 \| Class)** | **P(135 \| Class)** | **Posterior Probability** |
|------------|--------------|---------------------|----------------------|---------------------|---------------------------|
| Car        | 3/7          | 1/3                 | 2/3                  | 1/3                 | 2/63                      |
| Motorcycle | 2/7          | 0                   | 0                    | 0                   | 0                         |
| Truck      | 2/7          | 0                   | 0                    | 0                   | 0                         |

\- final probabilities :

| **Vehicle** | **Probability**           |
|-------------|---------------------------|
| Car         | (2/63) / (2/63 + 0 + 0)=1 |
| Motorcycle  | 0 / (2/63 + 0 + 0)=0      |
| Truck       | 0 / (2/63 + 0 + 0)=0      |

Based on the calculations, the posterior probability for the Car class
is 1, while the posterior probabilities for the Motorcycle and Truck
classes are both 0. Therefore, the most likely class for the new vehicle
with the given features is "Car."
