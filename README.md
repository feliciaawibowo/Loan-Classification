# Loan-Classification

## Project Overview
The project aims to predict the likelihood of customers being granted a personal loan based on demographic, financial, and behavioral features. Two neural network models were developed and compared: a baseline model and a modified model with added dropout layers to improve generalization.

## Dataset
### Key Features
Continuous: Age, Experience, Income, CCAvg (Credit Card Average), Mortgage
Discrete: Family, Education, Securities Account, CD Account, Online, CreditCard
### Target
Personal Loan (binary classification: 0 - No, 1 - Yes)
### Preprocessing
Dropped irrelevant columns, adjusted **Income** to monthly, replaced invalid **CCAvg** values with zero where no credit card was used, scaled continuous features using RobustScaler, and one-hot encoded the **Education** feature

## Model Architecture
### Baseline Model
Hidden Layers: 
  Two fully connected layers with:
    Units: 2 * n_input
    Activation: ReLU
Output Layer:
  Units: 2 (binary classification, one-hot encoded target)
  Activation: Sigmoid
Loss Function: Binary Crossentropy
Optimizer: Adam
Metrics: Accuracy

### Modified Model
Hidden Layers:
  Two fully connected layers with:
    Units: 2 * n_input
    Activation: ReLU
    Dropout: 0.2 added after each hidden layer
Output Layer:
  Units: 2 (binary classification, one-hot encoded target)
  Activation: Sigmoid
Loss Function: Binary Crossentropy
Optimizer: Adam
Metrics: Accuracy

## Evaluation Metrics
Accuracy: Correct predictions over the total number of predictions.

Precision: Proportion of true positive predictions among all positive predictions.

Recall: Proportion of true positive predictions among actual positive cases.

F1-Score: Harmonic mean of precision and recall.

## Results
### Baseline Model:
  Accuracy: 98.00%
  Precision: 93.18%
  Recall: 85.42%
  F1-Score: 89.13%
### Modified Model:
  Accuracy: 98.20%
  Precision: 95.35%
  Recall: 85.42%
  F1-Score: 90.11%

## Conclusion
The modified model with dropout layers slightly outperformed the baseline model in accuracy, precision, and F1-score, while maintaining the same recall. The addition of dropout layers improved the network's generalization, reducing overfitting.
