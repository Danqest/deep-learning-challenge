# deep-learning-challenge

## Overview of the Analysis

- The purpose of this analysis is to use deep learning to predict what kind of applicants for funding from the non-profit foundation, Alphabet Soup, will succeed in their ventures. Predictive features in the dataset include various categorical metadata items while success is determined by a simply binary classification. The dataset is contains approximately 34,000 records and the split between successful and unsuccessful ventures is about evenly split.

## Results

- Basic Preprocessing:

  - As mentioned above, predictive labels are a simply binary classification (0 and 1). Data is preprocessed with the dropping of feature vectors that have no predictive capability (EIN and Name) along with the consolidation of certain categorical features (Application Type and Classification) to bring the total number of categories per feature vector down to a more reasonable number.
  - After processing the data, each category in every feature vector is turned in to a one-hot encoded variable to simplfy the nerual network learning process, ultimately resulting in 43 feature vectors for predictive capabilities after being split and scaled.
  - The standard neural network is a sequential model containing two hidden layers with RELU activation functions and one output layer with a sigmoid activation function. Binary Crossentropy Loss is used along with accuracy as the metric of choice.

  ![model 0 parameters](https://github.com/danqest/deep-learning-challenge/blob/main/images/model0.png?raw=true)

  - After being run for 100 epochs, the standard model results in a validation accuracy of 0.7285, though our desired threshold is 0.7500.

- Model Optimization Trial 1:

  - In the first trial of optimization, the data is once again preprocessed with the dropping of the above mentioned columns. Instead of consolidating categories, however, all categories for Application Type and Classification are used, which results in 116 predictive features after one-hot encoding.
  - The network architecture for this model is essentially the same other than input dimensions being scaled up to 116 for all of the new features.

![optimized model 0 parameters](https://github.com/danqest/deep-learning-challenge/blob/main/images/model1.png?raw=true)

- After being run for 100 epochs, the first optimization trial results in validation accuracy of 0.7321 which is an improvement over the original model, though somewhat marginal and still below the 0.7500 desired threshold.

- Model Optimization Trial 2:

  - In the second trial of optimization, the data is once again preprocessed with the dropping of the above mentioned columns. Only Classification features are consolidated as in the original model (all Application Types are used), which results in 51 predictive features.
  - The network architecture for this model is essentially the same other than input dimensions being scaled up to 52 for the features.

![optimized model 1 parameters](https://github.com/danqest/deep-learning-challenge/blob/main/images/model2.png?raw=true)

- After being run for 100 epochs, the first optimization trial results in validation accuracy of 0.7298 which is an improvement over the original model, though very marginal and still below the 0.7500 desired threshold.

- Model Optimization Trial 3:
- In the third trial of optimization, the data is once again preprocessed with the dropping of the above mentioned columns. Only Application Type features are consolidated as in the original model (all Classifications used), which results in 108 predictive features.
- The network architecture for this model is essentially the same other than input dimensions being scaled up to 108 for the features.

![optimized model 2 parameters](https://github.com/danqest/deep-learning-challenge/blob/main/images/model3.png?raw=true)

- After being run for 100 epochs, the first optimization trial results in validation accuracy of 0.7324 which is an improvement over the original model and essentiall the same as the first optimization trial, though still somewhat marginal and still below the 0.7500 desired threshold.

## Summary

- All optimized models performed better than the original model, though no model was able to reach or exceed the desired 0.7500 threshold in validation accuracy. Based on the variety of way the data was preprocessed, it can be determined that more granular predictive features, as was the case in using more granular Applicant Type and Classification features as opposed to consolidating them, results in a model with greater predictive capabilities; it would be recommended that more features be incorporated into the model, either through feature engineering or more comprehensive data collection.
