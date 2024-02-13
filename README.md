# Synthetic Data Hackathon: Accelerate AI Solution by Team [PixelPioneers]

This repository contains our winning solution for the Synthetic Data Hackathon: Accelerate AI, where we achieved the highest ROC AUC score on the test set. Our approach utilized LightGBM in conjunction with Optuna for hyperparameter optimization, focusing on predicting activities in a household based on sensor data.

## Challenge Overview

The hackathon challenge was to predict household activities from gas, temperature, and infrared sensor data within an elderly person's home. The dataset included readings from various rooms, with the task to predict activity levels based on sensor inputs.

### Dataset Description

The dataset featured columns for timestamp, temperature, humidity, several gas sensor readings (CO2, MOX1-4, COValue), and binary indicators for movement detection in different rooms (Living room, Bedroom, Bathroom, Kitchen, Hallway).

### Files

- `data_synth_train.csv`: Training dataset with sensor readings and activity indicators.
- `data_synth_test.csv`: Test dataset with sensor readings, where predictions were made.
- `data_submission_example.csv`: Example submission format with predicted activity probabilities.

## Our Solution

### Approach

Our solution was built on LightGBM, leveraging its efficiency and effectiveness for handling tabular data. We utilized Optuna for extensive hyperparameter tuning to maximize the ROC AUC score, ensuring our model's predictions were both accurate and reliable. 

### Features

We engineered features from the sensor data to capture temporal patterns and room-specific activity trends. This included extracting cyclic features from the timestamps, adding elapsed minutes, hours and etc. Moreover, to somehow include corellations, we were appending the results predicted for the previous room as the feature for the next room, which improved the score. Also, we added lagged features of infrared sensors which also played crucial role in team success.

### Hyperparameter Tuning

Optuna was used to systematically search the hyperparameter space, finding the optimal configuration for our LightGBM model. This process significantly contributed to our model's performance.

## Results

We secured the top position with a ROC AUC score of 0.694 on the test set, demonstrating the effectiveness of our approach in predicting household activities from sensor data.


## Improvements and Future Work

Given more time, we would explore additional feature engineering techniques, experiment with ensemble models, and further refine our hyperparameter tuning process. Additionally, exploring the impact of different sensor combinations and their spatial relationships could yield insights for improving model accuracy.


## Acknowledgements

We thank Aindo SpA and the hackathon organizers for the opportunity to participate in this challenging and insightful event.
