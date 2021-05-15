# Predicting Who Lives and Dies on the Titanic

- [Predicting Who Lives and Dies on the Titanic](#predicting-who-lives-and-dies-on-the-titanic)
	- [Data Set](#data-set)
	- [Data Pre-Processing](#data-pre-processing)
	- [Model](#model)
	- [Results](#results)

On April 15, 1912, during her maiden voyage, the widely considered “unsinkable” RMS Titanic sank after colliding with an iceberg. Unfortunately, there weren’t enough lifeboats for everyone onboard, resulting in the death of 1502 out of 2224 passengers and crew.

While there was some element of luck involved in surviving, it seems some groups of people were more likely to survive than others.

In this project, I built a dense binary classification neural network to predict whether each passenger on the Titanic lived or died, based on some given info about each passenger.

## Data Set

The data set for this project is from Kaggle's Titanic Machine Learning Competition. 

https://www.kaggle.com/c/titanic/data

All of the passengers of the Titanic are split up into two data sets:
- A training set which indicates whether the passenger survives 
- A test set containing different passengers with no label for survival

For each passenger, we are given the following data about them:
- Ticket class (1st, 2nd, or 3rd)
- Sex (male or female)
- Age (in years)
- Number of siblings or spouses aboard the Titanic
- Number of parents or children aboard the Titanic
- Ticket ID number
- Cost of the ticket (in dollars)
- Cabin number
- Port of embarkation (Cherbourg, Queenstown, or Southampton)

## Data Pre-Processing

Some of the data given in the data set is immediately usable, but many other categories require some pre-processing. Pre-processing includes handling missing values, and converting text data. 

For further details on how I handled the data pre-processing, please take a look at the notebook file. 

## Model

There are many possible approaches to solve a simple binary classification problem such as this. Some examples include 
- Logistic Regression
- K Nearest Neighbors
- Stochastic Gradient Descent
- Random Forest Classifier
- Gradient Boosted Trees
- Deep Neural Network

Since I have been practicing deep neural networks with TensorFlow, I decided to build a simple densely connected binary classification neural network. 

Here is a summary of the model as given by `model.summary()`.

```
Model: "sequential"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
dense (Dense)                (None, 64)                704       
_________________________________________________________________
dense_1 (Dense)              (None, 64)                4160      
_________________________________________________________________
dense_2 (Dense)              (None, 1)                 65        
=================================================================
Total params: 4,929
Trainable params: 4,929
Non-trainable params: 0
_________________________________________________________________
```

## Results

The goal of this project was to beat the baseline of 76.5%, which is the accuracy if one predicts that all females live and all males die. 

After trying different configurations of hyper parameters, I arrived at a final accuracy of 77.8%. This does manage to beat out the baseline, although not by much. 