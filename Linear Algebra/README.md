## Evaluating Machine Learning for Insurance Benefits Prediction

**Overiew**

This project investigates how machine learning models can support the Sure Tomorrow Insurance Company in optimizing customer profiling, predicting benefit eligibility, and securing sensitive data. The key focus areas include customer similarity modeling, benefit classification, benefit count prediction, and secure data obfuscation through linear algebra techniques.

**Project Objective**
- Use k-Nearest Neighbors (kNN) to identify similar customers for targeted marketing
- Build a classification model to predict insurance benefit eligibility
- Develop a Linear Regression model to estimate the number of benefits received
- Apply a linear obfuscation transformation to anonymize data without degrading model performance

**Data Source**
The dataset includes anonymized customer records containing:
- Feature |	Description:
    - Demographics:	Age, gender, income, and dependents
    - Behavior Metrics:	Claims history, benefit counts
    - Target Variables:	Benefit eligibility (binary) and count
 
**Tools & Technologies**
- Language: Python
- Libraries: pandas, NumPy, scikit-learn, matplotlib
- Models: kNN Classifier, Custom Linear Regression, Dummy Classifier
- Metrics: F1 Score, Confusion Matrix, RMSE, R²
- Security Technique: Matrix-based linear data obfuscation

**Methodology**
1. Data Preparation
- Checked for missing values, inconsistencies, and scale imbalance
- Standardized features to improve model fairness and performance
- Split data into training and test sets for modeling and validation
2. kNN Classification (Customer Similarity)
- Compared Manhattan vs. Euclidean distance metrics
- Found that scaling significantly improved accuracy
- Best performance (F1 Score = 0.95) achieved with k=1 and scaled features
3. Classification Model (Eligibility)
- Compared kNN and Dummy classifiers
- Evaluated with F1 score and confusion matrices
- Model showed strong predictive power, significantly outperforming baseline
4. Linear Regression (Benefit Count Prediction)
- Built a custom Linear Regression model
- Achieved RMSE = 0.34 and R² = 0.66, indicating moderate predictive strength
- Performance consistent before and after data transformation
5. Data Obfuscation
- Applied a secure, invertible matrix transformation to input features
- Verified that this transformation did not affect model accuracy, preserving:
- RMSE = 0.34
- R² = 0.66

**Visuals**


**Conclusion**
- kNN Performance is highly sensitive to feature scaling. Without scaling, dominant features distort distance metrics.
- Linear Regression proved stable and robust, even after obfuscation using a matrix transformation.
- The highest classification performance (F1 = 0.95) was achieved with scaled kNN and k=1.
- Linear transformations effectively anonymized data without degrading model performance, confirming this as a viable security method for real-world use.

**Opportunities for Improvement**
- Experiment with more complex classifiers (e.g., Random Forest, Gradient Boosting)
- Add categorical encoding or feature interactions for regression tasks
- Use PCA or other dimensionality reduction to visualize obfuscation effects
- Explore differential privacy techniques for deeper data security assurance

**Final Takeaway**

This project demonstrates how machine learning can support secure, data-driven decision-making in insurance. Scaling plays a crucial role in distance-based models like kNN, while linear regression remains resilient under linear transformations — making it ideal for environments where privacy and accuracy must coexist.
