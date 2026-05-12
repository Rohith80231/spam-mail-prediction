# spam-mail-prediction
# SMS Spam Detection using Logistic Regression

## Project Overview
This project implements a simple yet effective SMS spam detection system using a Logistic Regression model. The goal is to classify incoming SMS messages as either 'ham' (legitimate) or 'spam' based on their content.

## Dataset
The dataset used for this project is `mail_data.csv`, which contains two columns:
- `Category`: Indicates whether the message is 'ham' or 'spam'.
- `Message`: The actual content of the SMS message.

## Model
**Logistic Regression** is used as the classification model. It's a linear model used for binary classification tasks, making it suitable for distinguishing between spam and ham messages.

## Preprocessing and Feature Extraction
1.  **Handling Missing Values**: Null values in the dataset are replaced with empty strings.
2.  **Label Encoding**: The 'Category' column is converted into numerical representation:
    - 'spam' messages are encoded as `0`.
    - 'ham' messages are encoded as `1`.
3.  **Splitting Data**: The dataset is split into training and testing sets to evaluate the model's performance.
4.  **TF-IDF Vectorization**: Text messages are converted into numerical feature vectors using `TfidfVectorizer`. This technique reflects the importance of a word in a document relative to a corpus.

## Dependencies
The following Python libraries are required:
- `numpy`
- `pandas`
- `scikit-learn` (specifically `train_test_split`, `TfidfVectorizer`, `LogisticRegression`, `accuracy_score`)

## Setup and Installation
To run this notebook, ensure you have the necessary libraries installed:

```bash
pip install numpy pandas scikit-learn
How to Run the Code
Load the Dataset: Ensure mail_data.csv is in the same directory as your notebook or provide the correct path.
Execute Cells Sequentially: Run each code cell in the provided notebook in order.
Training: The Logistic Regression model is trained on the preprocessed and vectorized training data.
Evaluation: The model's accuracy is evaluated on both training and testing datasets.
Prediction: You can test the model with new input messages to see its prediction (0 for spam, 1 for ham).
Code Structure
Model Dependencies: Imports necessary libraries.
Data Preprocessing: Loads data, handles missing values, and performs label encoding.
Splitting Data: Divides data into training and testing sets.
Feature Extraction: Converts text messages into numerical features using TF-IDF.
Model Training and Evaluation: Initializes, trains, and evaluates the Logistic Regression model.
Prediction System: Demonstrates how to use the trained model to predict new messages.
Results
The model achieves a high accuracy:

Accuracy on training data: ~96.8%
Accuracy on testing data: ~97.0%
This indicates that the model is performing well in distinguishing between spam and ham messages.

Example Usage (from the notebook)
To predict if a new email is spam or ham:

input_mail = ["WINNER!! As a valued network customer you have been selected to receivea £900 prize reward! To claim call 09061701461. Claim code KL341. Valid 12 hours only."]

input_data_features = feature_extraction.transform(input_mail)
prediction = model.predict(input_data_features)

print(prediction)
# Output: [0] (indicating spam)
