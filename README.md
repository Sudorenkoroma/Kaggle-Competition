# Kaggle Competition - ML Model for Sales Prediction

## Overview
This project is a Kaggle competition entry that involves building a machine learning model to predict item outlet sales. The solution uses a deep neural network implemented with TensorFlow/Keras, along with preprocessing techniques, to improve the accuracy of predictions on the provided dataset.

## Project Structure
- **Notebook**: The notebook `otebookac1062f1d6.ipynb` contains the entire workflow of the project, including data loading, preprocessing, model building, training, and evaluation.
- **Data**: The dataset used for this competition includes `train.csv`, `test.csv`, and `sample_submission.csv`, loaded directly from the Kaggle competition.

## Key Steps

1. **Data Preprocessing**:
    - **Missing values**: Replaced missing values in numerical columns with 0.
    - **Categorical Features**: Converted categorical variables (like `Item_Fat_Content`, `Item_Type`, `Outlet_Identifier`, etc.) into dummy variables.
    - **Feature Engineering**: Added new feature `Age_of_Outlet` to represent the age of each outlet.
    - **Scaling**: Numerical features were scaled using `StandardScaler`.

2. **Model Architecture**:
    - The neural network consists of multiple dense layers with ReLU activation.
    - Dropout layers are used for regularization to avoid overfitting.
    - A custom learning rate scheduler (`CustomLearningRateScheduler`) adjusts the learning rate during training based on validation loss.
    - Early stopping is implemented to halt training if the validation loss does not improve after several epochs.

3. **Training**:
    - The model is compiled using the `Adam` optimizer and `mean_squared_logarithmic_error` as the loss function.
    - The training process uses early stopping and a custom learning rate scheduler to ensure optimal performance.
    - The model is trained for up to 150 epochs, with a batch size of 64.

4. **Evaluation**:
    - Validation data is used to evaluate the model’s performance by calculating the `Mean Squared Logarithmic Error (MSLE)`.
    - The model predictions are saved to a submission file for Kaggle competition entry.

## Dependencies
The following Python libraries are used:
- `pandas`
- `numpy`
- `sklearn`
- `tensorflow`
- `keras`
