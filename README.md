📌 IntersectMatch: Optimizing Candidate Selection with Joint Semantic and Predictive Filtering

Welcome to the repository for our research project IntersectMatch, a dual-filter AI-driven system that streamlines and improves the recruitment process by combining semantic similarity and predictive classification techniques.

📖 Overview

Modern recruitment has evolved into a high-volume, digitally driven process. Traditional manual screening methods are slow, biased, inconsistent, and often lead to suboptimal candidate selections. Meanwhile, organizations demand fast, fair, and scalable solutions to identify the best candidates from a vast pool of applicants.

To address this, our research project explores the fusion of semantic embedding-based filtering with machine learning-based predictive modeling, aiming to create a hybrid model that is both effective and interpretable in real-world hiring scenarios.

🔍 Problem Statement

Recruitment inefficiencies stem from:

Human bias and subjectivity in resume evaluation

Inconsistent scoring mechanisms

Difficulty scaling manual reviews

While machine learning has gained traction in hiring workflows, current models still lack fairness, transparency, and domain adaptability.

🧠 Research Gaps

Despite advances in NLP and ML:

Most solutions rely on either semantic or predictive methods, not both.

There's limited focus on model explainability in candidate ranking systems.

Contextual embeddings (like BERT) are underutilized in actual screening pipelines.

Few studies have evaluated the interplay of multiple models in improving candidate-job alignment.

🛠️ Methodology
![image](https://github.com/user-attachments/assets/d42f604c-2242-4d0f-b72e-1a4a455348a2)

Our approach integrates:

Predictive Modeling: Using classifiers (e.g., Naive Bayes, Logistic Regression, etc..) on combined embeddings for classifying candidate fit levels (Good Fit, Potential Fit, No Fit). 

Semantic Filtering: Using pretrained embedding models (Sentence-BERT, GloVe, Word2Vec) to generate dense vector representations of resumes and job descriptions. Cosine similarity is then computed between these vectors to assess their semantic alignment.



📊 Dual Pipeline

Step 1: Preprocess textual data (lowercasing, stopword removal, lemmatization).

Step 2: Generate Embeddings for resumes and job descriptions (Experimented with both Semantic and Static Embeddings).

Step 3: Resume Screening (highlights dual approach): 

Stage 1: Training a ML model on historical resume and job description labeled data where each job-resume pair is labeled as good fit, no fit, or potential fit for predictive analysis.
Stage 2: Computing cosine similarities between resumes and job descriptions and selecting resumes above a pre-determined threshold.

Step 4: Resume Selection:

To ensure the selection of the best resume-job fit, the intersection of the results from both stages is taken. This step shows the novelty of our proposed framework combined with the dual approach.

Step 5: Evaluate performance using precision, recall, F1-score, and confusion matrices.

📈 Experiments & Results

We conducted extensive experiments using the cnamuangtoun/resume-job-description-fit dataset (This dataset has not been used in the literature, we are the first ones to experiment with it).

✅ Semantic Embedding Results on ML models' Performance:

GloVe outperformed Sentence-BERT in maintaining contextual relevance on XGBoost amongst other trained models (76%)

✅ Static Embedding Results on ML models' Performance:

XGBoost showed strong performance with static embedding  (Word2Vec - 75% Accuracy) - Best Performing model

XGBoost was the best performing model in both the cases. 

📊 Visuals:

Confusion matrices and classification reports were used to interpret model decisions. 

💡 Key Findings

Static Embedding performs better than Semantic Embedding, in most cases.

Model not suitable for real world deployment given its low accuracy score, however, the overall framework is solid and deployable.

The best performing ML model with the dataset used for this study is XGBoost, with an accuracy score of 76%.


🚀 Future Work

Develop public datasets with resume–job pairs and detailed fit labels.

Test model on varied corpora to assess generalization.

Apply transfer learning for unlabeled or industry-specific data.

Evaluate model fairness across demographics and language.

Deploy in real systems to measure recruiter usability and trust.

Use multi-dimensional fit criteria beyond binary labels.

Interactive UI (optional future integration)

👨‍💼 Authors

Madeeha Balouch Abdul Razzaque Balouch - g00105837@aus.edu

Ragad Ahmed - g00085960@aus.edu

Sarah Elfattal - g00088762@aus.edu

📨 Contact

For collaborations or questions, please reach out via GitHub Issues or email any of the authors.
