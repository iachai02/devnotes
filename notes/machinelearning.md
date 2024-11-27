# Machine Learning Notes

## Types of Machine Learning

- `Supervised learning`: uses labeled inputs (meaning the input has a corresponding output label) to train models and learn outputs
  - pictures of a cat, dog, and lizard but to a computer, they are just pixels
  - these pictures have labels (cat, dog, lizard)
- `Unsupervised learning`: uses unlabeled data to learn about patterns in data
  - feed the computer all different types of pictures and be able to possibly cluster pictures if they have something in common (finding structure in unlabeled data)
- `Reinforcement learning`: agent learning in interactive environment based on rewards and penalties
  - giving rewards to our computer

## Supervised Learning

- `Feature vector`: a bunch of inputs not including the output
- `Target for feature vector`: output
- `X`: features matrix
- `y`: labels/targets vector
- A bunch of inputs get sent to a model and then comes out with an output (prediction)
- Features
  - `Qualitative`: categorical data (finite number of categories or groups)
    - i.e. gender, location/nationalities
    - nominal data (no inherent order)
    - use one-hot encoding (if it matches one category, make it a 1, if not make it a 0)
    - ordinal data (inherent order)
      - baby, toddler, teen, young adult, adult, etc.
  - `Quantitative`: numerical valued data (could be discrete or continuous)
    - i.e. length of something, temperature, how many eggs

### Supervised Learning Tasks

- `Classification`: predict discrete classes
  - i.e. is this a hotdog, pizza, icecream?
    - multiclass classification
  - i.e. is this a hotdog or not a hotdog?
    - binary classification
- `Regression`: predict continuous values
  - i.e. price of etherium tomorrow, what is going to be the temperature, what is the price of this house?

### Supervised Learning Dataset

- Training dataset, Validation dataset, Testing dataset
- validation set used as a reality check during/after training to ensure model can handle unseen data
- lower loss is better
- we take whatever model had the lowest loss and use our test set on that model to check how generalizable the final chose model is

## Common Imports

- import numpy as np
- import pandas as pd
- import matplotlib.pyplot as plt

## Common commands

- `pd.read_csv("file_name")`: imports a data file
  - `pd.read_csv("file_name", names=cols)`: adds labels to the dataset where `cols` is a list of the names of columns
