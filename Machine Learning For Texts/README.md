# Classifying Movie Reviews for the Film Junky Union
**Description:**
The Film Junky Union, a bold new community for classic movie lovers, is building a system to automatically flag negative movie reviews from users. With the explosive growth in online reviews, manual moderation has become impractical. By leveraging natural language processing (NLP) and machine learning, this project aims to train a classifier that distinguishes between positive and negative IMDB movie reviews with high accuracy. The ultimate goal is to streamline content moderation and surface the most constructive feedback to the community.

**Objective:**
- Load and analyze a dataset of IMDB reviews labeled as positive or negative.
- Preprocess the review texts for machine learning readiness using tokenization, lemmatization, and vectorization techniques.
- Train and compare at least three classification models (e.g., Logistic Regression, Random Forest, Gradient Boosting).
- Evaluate model performance using the F1 score, targeting a minimum threshold of 0.85.
- Explore the use of BERT embeddings for a small sample to compare traditional NLP approaches with transformer-based representations.
- Test the models with original user-composed reviews and analyze classification consistency.

**Data Sources:**
- The dataset is stored in /datasets/imdb_reviews.tsv and contains:
    - review: the raw text of each movie review
    - pos: the binary target variable (1 = positive review, 0 = negative review)
    - ds_part: the dataset split indicator (train or test)
    
**Approach:**
- Data Preparation:
    - Load and explore the dataset.
    - Analyze the class balance and distribution of sentiment labels.
    - Preprocess the text using traditional NLP steps (cleaning, tokenization, lemmatization).
    - Optionally test transformer-based vectorization (BERT) on a subset.

- Model Development:
    - Build and train baseline models using vectorized features (e.g., Bag-of-Words, TF-IDF).
    - Implement and compare classifiers such as Logistic Regression, Random Forest, and Gradient Boosting.
    - Evaluate models using cross-validation and F1 scoring.

- Performance Evaluation:
    - Use the F1 score to assess model effectiveness in detecting negative reviews.
    - Compare predictions on test data and a set of custom-written reviews.
    - Analyze any differences in prediction behavior and suggest reasons.
    
**Tools & Libraries:**
- Data Processing: pandas, numpy, re
- Text Preprocessing: NLTK, spaCy, sklearn.feature_extraction.text
- Model Training: scikit-learn, optionally transformers (for BERT)
- Visualization: matplotlib, seaborn
- Progress Monitoring: tqdm

**Deliverables:**
- A trained and evaluated machine learning model that reliably classifies movie reviews by sentiment.
- A comparative performance analysis of traditional models vs. modern embeddings (optional BERT).
- Insights into classification behavior on custom reviews.
- Recommendations for improving classification further (e.g., hyperparameter tuning, ensembling, or use of larger embeddings).

By the end of this project, the Film Junky Union will have a sentiment classification pipeline that balances predictive performance with computational efficiency, helping them maintain a high-quality, feedback-friendly movie review community.

**Conclusion**

- Project Summary:
    - The goal was to build a binary classifier that can accurately detect negative movie reviews from IMDB. A variety of models were tested, and the target was to achieve an F1 score of at least 0.85.

- Models Trained:
    - Model	Description	Preprocessing	F1 (Test)
    - Model 1	Logistic Regression	TF-IDF + Manual stopwords ~0.87
    - Model 2	Logistic Regression	spaCy Lemmatization + TF-IDF ~0.86
    - Model 3	LightGBM Classifier	spaCy Lemmatization + TF-IDF ~0.85
    - Model 0	Dummy (Baseline) None 0.00

- Key Insights:
    - Text preprocessing (e.g., stopwords removal, lemmatization) plays a critical role in model performance.
    - Model 1 offered strong performance without heavy computation — a great candidate for deployment.
    - Model 2 handled review context well and was the most confident across custom-written reviews.
    - Model 3 (LGBM) was slightly more conservative and might benefit from hyperparameter tuning or feature engineering.

- Recommendations:
    - Deploy Model 2 if you want the most confident classifier.
    - Use Model 1 if you prefer simplicity and speed without sacrificing much in performance.
    - Avoid overly complex models unless there's a need for handling edge cases or non-linear relationships.
