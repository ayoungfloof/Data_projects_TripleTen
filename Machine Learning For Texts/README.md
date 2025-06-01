## Sentiment Classifying Movie Reviews for the Film Junky Union

**Overview**
With the growing volume of online reviews, the Film Junky Union — a community of classic film enthusiasts — aims to automate the detection of negative movie reviews using machine learning and natural language processing (NLP). This project builds a binary sentiment classifier using IMDB data, helping surface constructive feedback and streamline content moderation.

**Project Objective**
- Preprocess IMDB reviews using traditional NLP techniques and modern embeddings
- Train and evaluate multiple classification models
- Achieve an F1 score of at least 0.85 on the test set
- Compare traditional NLP pipelines with transformer-based approaches like BERT (optional)
- Test model behavior on custom-written reviews

**Data Sources**
- Dataset: /datasets/imdb_reviews.tsv
- Column |	Description:
    - review	Raw text of each IMDB movie review
    - pos	Sentiment label (1 = positive, 0 = negative)
    - ds_part	Dataset split indicator (train, test)

**Tools & Technologies**
- Data Handling: pandas, numpy
- Text Preprocessing: NLTK, spaCy, regex, scikit-learn
- Vectorization: TF-IDF, CountVectorizer, optional BERT embeddings
- Modeling: Logistic Regression, LightGBM, Dummy Classifier
- Evaluation: F1 score, confusion matrix
- Visualization: matplotlib, seaborn
- Progress Monitoring: tqdm
    
**Methodology**
1. Data Exploration & Preprocessing
- Loaded and explored sentiment label distribution
- Cleaned review text with regex, lowercasing, and punctuation removal
- Applied two preprocessing pipelines:
    - Manual stopwords removal + TF-IDF
    - spaCy lemmatization + TF-IDF
2. Model Development & Evaluation
- Trained the following models:
    - Model	Preprocessing	F1 Score (Test)
    - Model 0	Dummy (baseline)	0.00
    - Model 1	TF-IDF + stopword removal	~0.87
    - Model 2	spaCy Lemmatization + TF-IDF	~0.86
    - Model 3	LightGBM + Lemmatized TF-IDF	~0.85
- Used cross-validation and grid search for tuning
- Evaluated on both test data and custom reviews written by the user

**Visuals**

![image](https://github.com/user-attachments/assets/9db3ac07-a088-485e-acd2-c3e54b68e930)

![image](https://github.com/user-attachments/assets/3d662f03-3770-4479-bc7b-03035e91fd5f)

![image](https://github.com/user-attachments/assets/79c29591-4c90-429e-b2f9-83ec3cd9d699)

![image](https://github.com/user-attachments/assets/beac905b-90e9-4a3a-822b-f49e1692c49d)

![image](https://github.com/user-attachments/assets/655fcc2d-06cc-4ee0-b16e-cc33151a6534)

![image](https://github.com/user-attachments/assets/491a9132-9576-42e2-ac1c-96644c5a272a)

![image](https://github.com/user-attachments/assets/9d9b70d9-f936-4e29-8606-190c22dbfd6d)

![image](https://github.com/user-attachments/assets/d80dcb6c-8c4e-46be-a769-31fa26eabe12)

![image](https://github.com/user-attachments/assets/194adde2-1b17-4a6f-971b-95004cc39e03)

![image](https://github.com/user-attachments/assets/07f745d4-aea7-4ab5-87bd-58925cdcdaab)

**Key Findings**
- Text preprocessing is critical — stopword removal and lemmatization both improved model accuracy
- Model 1 (Logistic Regression + TF-IDF) performed best overall and is lightweight, making it ideal for deployment
- Model 2 showed strong confidence across real and synthetic test cases
- Model 3 (LightGBM) underperformed slightly, possibly due to lack of parameter tuning or overfitting on sparse vectors

**Opportunities for Improvement**
- Apply grid search or Optuna to tune LightGBM or ensemble models
- Train on larger review corpora or incorporate more neutral/ambiguous reviews
- Use word embeddings like Word2Vec, FastText, or full BERT fine-tuning for more contextual accuracy
- Deploy a live demo with Streamlit or build an API with Flask for content moderation support

**Final Takeaway**

This project successfully delivered a high-performing sentiment classifier that meets the performance goal of F1 ≥ 0.85. With lightweight preprocessing and standard ML models, it demonstrates how NLP can efficiently support community moderation at scale. The Film Junky Union now has a working foundation for intelligent review filtering — scalable, interpretable, and ready for deployment.
