# DSI Capstone - Kaggle Leaf Classification

Author: William Buck

---

## Problem Statement
Species identification presents many issues since it is a subjective grouping based on observations of the scientist doing the classification of the organism. Identifying the biodiversity of an ecosystem is vital to understanding how to care for the environment, which is increasingly important for humans as we explore environmental issues related to our impact. You can read more about the ["species problem" here](https://en.wikipedia.org/wiki/Species_problem).

While physical appearance is only one attribute of species identification, it is something that can be improved upon by using computers since human error can be minimized. A more accurate image classification model could have a big impact on the many companies and organizations that rely on the environment.

The following analysis on the Kaggle Leaf Classisfication datasets will demonstrate the predictive power of Machine Learning models, as well as a Convolutional Nueral Net, on the provided leaf images to identify the species of tree that the leaf originated from.


## Data Description

**[Link to Leaf Classification datasets on Kaggle](https://www.kaggle.com/c/leaf-classification/data)**

The dataset consists of 1,584 images of leaf specimens (16 samples each of 99 species) which have been converted to binary black leaves against white backgrounds. Three sets of features are also provided per image: a shape contiguous descriptor, an interior texture histogram, and a ﬁne-scale margin histogram. For each feature, a 64-attribute vector is given per leaf sample.

**File descriptions**
<br>train.csv - the training set
<br>test.csv - the test set
<br>sample_submission.csv - a sample submission file in the correct format
<br>images - the image files (each image is named with its corresponding id)

**Data fields**
<br>id - an anonymous id unique to an image
<br>margin_1, margin_2, margin_3, ..., margin_64 - each of the 64 attribute vectors for the margin feature
<br>shape_1, shape_2, shape_3, ..., shape_64 - each of the 64 attribute vectors for the shape feature
<br>texture_1, texture_2, texture_3, ..., texture_64 - each of the 64 attribute vectors for the texture feature

## Metrics
In this report, a combination of Log Loss and accuracy scores will be displayed. Since the classes are balanced and each class represents ~1% of the data, the accuracy measure will be an acceptable measure of model preformace and is quickly interpretible in terms of knowing how many correct predictions were made, but Log Loss will ultimately be the loss function I'm trying to minimize since it penalizes the score for false predictions, or less than certain predictions. See the function below.

$$
\textit{logloss} = -\frac1N\sum_{i=1}^{N}\sum_{j=1}^{M}{{y}_{i,j}\log({p}_{i,j})}
$$

N = the number of samples or instances
<br>M = the number of possible labels 
<br>${y}_{i,j}$ = a binary indicator of whether or not label *j* is the correct classification for instance *i*
<br>${p}_{i,j}$ = the model probability of assigning label *j* to instance *i*

>Log-loss is a “soft” measurement of accuracy that incorporates the idea of probabilistic confidence. It is intimately tied to information theory: log-loss is the cross entropy between the distribution of the true labels and the predictions. Intuitively speaking, entropy measures the unpredictability of something. Cross entropy incorporate the entropy of the true distribution, plus the extra unpredictability when one assumes a different distribution than the true distribution. So log-loss is an information-theoretic measure to gauge the “extra noise” that comes from using a predictor as opposed to the true labels. By minimizing the cross entropy, one maximizes the accuracy of the classifier.
><br>-- From: https://www.quora.com/What-is-an-intuitive-explanation-for-the-log-loss-function
