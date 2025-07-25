﻿## Facial Emotion Recognition with CNN

This project focuses on classifying facial emotions using Convolutional Neural Networks (CNNs). It utilizes a dataset of labeled facial images to train models capable of recognizing six basic emotions: **Angry**, **Disgust**, **Fear**, **Happy**, **Sad**, **Surprise**, and **Neutral**.

## Project Structure

- `Facial_Emotion_Image_Classification.ipynb` - Contains all steps for data preprocessing, model development, training, and evaluation
- `Dataset/` - Facial emotion image dataset with emotion labels. Upload this manually via Google Colab or your local environment

- Dataset Link : https://www.kaggle.com/datasets/chiragsoni/ferdata

## Models Built

### 1. Baseline CNN Model

- Simple architecture
- No regularization
- Serves as a reference point

### 2. CNN with Regularization

- Deeper architecture with more convolutional layers
- Includes Dropout and L2 Regularization
- Helps reduce overfitting

### 3. Transfer Learning Model

- Uses a pre-trained model ResNet50
- Fine-tuned on the facial emotion dataset
- Generally offers better performance with less training time

## Evaluation

Each model was evaluated using:

- Accuracy and loss curves
- Classification report (Precision, Recall, F1-Score)
- Confusion matrix

## Requirements

Install all necessary libraries with:

```bash
pip install tensorflow keras matplotlib seaborn scikit-learn opencv-python
```

## How to Run

1. Open `Facial_Emotion_Image_Classification.ipynb` in Google Colab or Jupyter Notebook
2. Upload the facial emotion dataset when prompted
3. Ensure the folder structure matches what the notebook expects
4. Run all cells sequentially to preprocess data, train models, and evaluate performance

## Results Summary

| Model                        | Train Accuracy | Test Accuracy | Training Time | Optimizer | Remarks                                               |
| ---------------------------- | -------------- | ------------- | ------------- | --------- | ----------------------------------------------------- |
| Baseline CNN                 | 50%            | 55%           | ~17.12 min    | Adam      | Struggled with complex features                       |
| Deeper CNN (Adam)            | 51%            | 54%           | ~8.98 min     | Adam      | Better than baseline, but slower & less accurate      |
| Deeper CNN (SGD)             | 56%            | 61%           | ~8.98 min     | SGD       | Better result with SGD then Adam                      |
| Transfer Learning (ResNet50) | 76%            | 65%           | ~71.58 min    | Adam      | Best accuracy, generalization, and faster convergence |

_Note: Exact accuracy depends on training settings and dataset split._

## Notes

- This project demonstrates how model depth, regularization, and transfer learning impact classification performance
- You can experiment by adding more layers, augmenting the dataset, or testing other pre-trained models
