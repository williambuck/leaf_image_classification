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

## Files in this repository:
1. **Kaggle_Leaf_Classification-Technical_Presentation.ipynb** - Includes the full analysis of the dataset
1. **bestbenchmarkmodel.h5** - CNN that was used as a benchmark
1. **bestmodel.h5** - CNN that provided the best validation score
1. **model.png** - Architecture of final CNN model
1. **data** - Numerical attribute data, training and test sets (see Data Description above)
1. **images** - Includes all of the black and white leaf images

## Results:
The final CNN model resulted in a Log Loss score of 0.07351101370107743 with 99.6% accuracy when predicting the species of tree from which the leaf originated.
