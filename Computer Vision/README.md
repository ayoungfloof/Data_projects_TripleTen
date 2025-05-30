## Predicting Age from Facial Images for Good Seed Supermarket
**Description:**
This project supports Good Seed, a supermarket chain, in improving compliance with alcohol sales laws by using computer vision to estimate a customer’s age at self-checkout. The stores are equipped with cameras that activate when a customer attempts to purchase alcohol. A reliable age prediction model can help ensure underage individuals are not mistakenly sold restricted products.

**Objective:**
Develop and evaluate a deep learning model capable of predicting a person's age from a photo. The model will be trained on a dataset of labeled facial images and assessed using the Mean Absolute Error (MAE) metric, with a target performance of MAE ≤ 8.

**Data Sources:**
- Facial image dataset located in the /datasets/faces/ directory:
    - final_files/: Contains ~7,600 individual face images.
    - labels.csv: A CSV file linking each image filename with the person's actual age.
- Each record includes:
    - file_name: Filename of the image.
    - real_age: True age of the person in the photo.

**Approach:**
- Data Preparation:
    - Load the image data using ImageDataGenerator to handle large image volumes efficiently.
    - Normalize and batch images for training and validation sets.
- Model Development:
    - Use a pre-trained ResNet50 architecture as the feature extractor.
    - Add a global pooling layer and a dense output layer with ReLU activation.
    - Use Adam optimizer and MSE loss for training.
- Model Training:
    - Due to platform constraints, model training is performed externally using a GPU.
    - Provided training logs from 20 epochs will be analyzed for final evaluation.
- Evaluation:
    - Examine training/validation loss and MAE over time.
    - Determine whether the model meets the performance threshold for deployment.
    
**Tools**
- import pandas as pd  
- import numpy as np  
- import tensorflow as tf  
- from tensorflow.keras.preprocessing.image import ImageDataGenerator  
- from tensorflow.keras.applications.resnet import ResNet50  
- from tensorflow.keras.models import Sequential  
- from tensorflow.keras.layers import GlobalAveragePooling2D, Dense  
- from tensorflow.keras.optimizers import Adam  
- import matplotlib.pyplot as plt  
- import seaborn as sns
- import os
- import matplotlib.image as mpimg
- from PIL import Image
- import inspect

**Deliverables:**
- A trained convolutional neural network for age prediction.
- Model evaluation results, including MAE and validation performance.
- Final recommendations regarding the feasibility of using the model at checkout kiosks.

This project will demonstrate how deep learning can enhance retail compliance and operational efficiency through age verification from facial images.

## Overall Conclusion
This project focused on building a computer vision model to assist the Good Seed supermarket chain in verifying customers’ ages during alcohol purchases. By leveraging facial photographs and age labels, we aimed to develop an accurate regression model capable of estimating a person’s age directly from an image.

- Model Design and Training:
    - The model used a pre-trained ResNet50 as a feature extractor with a custom head for age prediction.
    - The final architecture included:
        - GlobalAveragePooling2D for flattening feature maps,a single Dense output neuron with ReLU activation to ensure non-negative age predictions.
    - Training was conducted over 20 epochs using the Adam optimizer and Mean Squared Error (MSE) as the loss function.
- Model Performance:
    - The model achieved a final validation Mean Absolute Error (MAE) of 7.65 years, which satisfies the project requirement of MAE < 8.
    - The best validation MAE (6.64) occurred at epoch 17, suggesting optimal generalization around that point.
    - Training MAE consistently decreased across epochs, indicating proper learning.
    - Slight overfitting was observed after epoch 17, as validation MAE began to increase while training MAE continued to decrease.
- Data Quality and Preprocessing:
    - No missing or duplicate entries were found in the dataset.
    - Images had consistent dimensions (114x114) and RGB color channels.
    - All images were rescaled and standardized using ImageDataGenerator to improve model performance and prevent overfitting.
- Business Value:
    - This solution can help automate underage alcohol purchase detection by flagging customers estimated to be below legal age thresholds (e.g., 21).
    - While the model’s error margin is approximately ±7.65 years, it performs reliably enough to support human verification (e.g., flag reviews or trigger ID checks), especially near age boundaries.

**Recommendations:**

- Model Improvements:
    - Use additional training data or apply data augmentation techniques (e.g., rotation, zoom) to improve generalization.
    - Experiment with dropout layers or fine-tune more layers of ResNet50 to reduce overfitting.
    - Consider using alternative CNN architectures such as EfficientNet or MobileNet for faster inference on retail hardware.
- Post-processing Rules:
    - Implement logic thresholds (e.g., flag if predicted age < 25) to minimize the risk of underage sales.
    - Combine model predictions with existing ID scanning processes for double verification.
- Deployment Considerations:
    - Test the model in real-world store lighting and angles to validate robustness.
    - Ensure that ethical and privacy concerns around facial analysis are addressed in production use.

**Final Verdict:**
The model shows strong promise in helping the supermarket chain improve compliance with alcohol laws. It meets the project’s performance criteria and lays the groundwork for a hybrid human-AI review system at checkout counters. With further tuning and testing, it could become a valuable tool in the chain’s responsible retail strategy.
