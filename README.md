# Motion Sensor Classification – Environment Prediction Challenge

In this project, the goal was to predict the **environmental condition** in which a machine is operating, using motion sensor data recorded over time.

This is a **multi-class classification problem** with **9 possible classes**, each representing a different operating environment.

## Competition Details

- **Start date:** March 11, 2025  
- **End date:** March 26, 2025  
- **Evaluation Metric:** Accuracy

The target variable is `condition`, which corresponds to one of 9 categories (A1, A2, B1, B2, ..., C3).  
These are encoded as integers from **0 to 8**, in alphabetical order:

- `A1` → 0  
- `A2` → 1  
- `B1` → 2  
- `B2` → 3  
- `B3` → 4  
- `C1` → 5  
- `C2` → 6  
- `C3` → 7  
- `D1` → 8  

## Dataset

The dataset consists of motion sensor time-series data. The files provided are:

- `X_train.csv`: Features for the training set  
- `y_train.csv`: Labels for the training set  
- `X_test.csv`: Features for the test set  
- `sample_submission.csv`: Sample output format

### Feature Description

Each row in `X_train.csv` and `X_test.csv` includes time-series sensor data with the following columns:

- `order_id`: row identifier  
- `id_seq`: time-series identifier (used to group rows into sequences)  
- `time`: time step (within a sequence)

#### Sensor data:
- **Angular velocity:** `Xa`, `Ya`, `Za`  
- **Velocity:** `Xv`, `Yv`, `Zv`  
- **Orientation (quaternions):** `Xo`, `Yo`, `Zo`, `Wo`  
- **Signal strength:** `signal_strength`

The `y_train.csv` file contains the corresponding labels:

- `id_seq`: matches the sequence ID from the training data  
- `group_id`: experimental run ID  
- `condition`: target variable (encoded as 0–8)

## Goal

Build a classification model that takes the time-series motion data as input and predicts the correct environment (`condition`) for each sequence in the test set.

## Evaluation

The competition uses **accuracy** as the evaluation metric. Your predictions must match the class encoding (0–8) used in the target variable.

