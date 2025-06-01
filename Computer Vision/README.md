## Predicting Age from Facial Images for Good Seed Supermarket

**Overview**
To strengthen compliance with alcohol sales regulations, Good Seed — a nationwide supermarket chain — aims to implement a computer vision system that estimates customer age during self-checkout. This project develops a convolutional neural network to predict a person’s age from facial images using deep learning techniques. A model with an MAE (Mean Absolute Error) of ≤ 8 years is considered suitable for deployment to assist human verification systems.

**Project Objective**
- Build a CNN regression model to estimate age from facial images
- Use a pre-trained ResNet50 architecture with a custom output head
- Process ~7,600 labeled images and evaluate performance using MAE
- Ensure model meets accuracy threshold (MAE ≤ 8) to support compliance workflows

**Data Sources:**
- Facial image dataset located in the /datasets/faces/ directory:
    - final_files/: Contains ~7,600 individual face images.
    - labels.csv: A CSV file linking each image filename with the person's actual age.
- Each record includes:
    - file_name: Filename of the image.
    - real_age: True age of the person in the photo.
    
**Tools & Technology**
- Language: Python
- Libraries: TensorFlow, Keras, pandas, NumPy, matplotlib, seaborn, PIL
- Modeling: ResNet50 (pre-trained), Sequential API, GlobalAveragePooling2D
- Training: Adam optimizer, MSE loss
- Evaluation: MAE (Mean Absolute Error)
- Preprocessing: ImageDataGenerator for normalization and batching

**Methodology**
1. Data Preparation
- No missing or duplicate data detected
- Image resolution: 114x114 RGB, standardized across the dataset
- Used ImageDataGenerator to normalize images and batch data for training/validation
2. Model Architecture
- Leveraged a pre-trained ResNet50 as a fixed feature extractor
- Added:
    - GlobalAveragePooling2D layer
    - Single Dense output neuron with ReLU activation (for non-negative age prediction)
- Loss function: Mean Squared Error (MSE)
- Optimizer: Adam
3. Model Training
- Trained on GPU externally for 20 epochs
- Training and validation loss/MAE monitored for each epoch
- Early signs of overfitting observed after epoch 17
4. Model Evaluation
- Metric | Value:
    - Final Validation MAE	7.65 years
    - Best MAE (Epoch 17)	6.64 years
    - Performance Target	MAE ≤ 8

**Visuals**

![image](https://github.com/user-attachments/assets/3ff22d58-2658-4552-a2c9-e0275709e917)

![image](https://github.com/user-attachments/assets/109ebfc7-868a-4749-980b-0eefcef05aae)

![image](https://github.com/user-attachments/assets/35f1e6e7-b624-4420-8fd0-b087348f99e4)

**Conclusion**
This project successfully trained a CNN model to estimate customer age from facial images with high accuracy. The final MAE of 7.65 years meets the project’s threshold, making the model viable for retail screening support.
- Key highlights:
    - Training behavior was stable across 20 epochs
    - Peak validation performance occurred at epoch 17 (MAE = 6.64)
    - Slight overfitting noted in final epochs, suggesting early stopping or regularization could improve generalization

**Opportunities for Future Improvement**
- Model Enhancements:
    - Add data augmentation (e.g., zoom, rotation) to improve generalization
    - Test alternative CNN backbones (e.g., EfficientNet, MobileNet) for real-time performance
    - Fine-tune more layers of ResNet50 or apply dropout layers to reduce overfitting
- Business Integration:
    - Use a post-processing threshold (e.g., flag if predicted age < 25) to minimize legal risk
    - Combine this model with existing ID scan systems for double verification
    - Test in varied lighting and camera conditions to ensure robustness

**Final Recommendation**
The trained ResNet-based model meets performance goals and offers real-world value for supporting underage sales prevention. With further tuning and deployment testing, it could serve as a hybrid AI-human review tool to assist staff at self-checkout stations, improving both regulatory compliance and customer trust.
