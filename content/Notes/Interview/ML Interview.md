---
title: ML Interview
draft: true
tags:
date: 03-Sep-2025
---
# Introduction
## Machine Learning

**What** -> is a branch of Artificial Intelligence that focuses on developing models and algorithms that let computers learn from data without being explicitly programmed for every task. In simple words, ML teaches the systems to think and understand like humans by learning from the data.
<!--SR:!2025-09-07,4,270-->

**Types**
?
- Core types
	- **Supervised Learning**: Trains models on labeled data to predict or classify new, unseen data.
	- **Unsupervised Learning**: Finds patterns or groups in unlabeled data, like clustering or dimensionality reduction.
	- **Reinforcement Learning**: Learns through trial and error to maximize rewards, ideal for decision-making tasks.
- Additional Types
	- **Self-Supervised**: Self-supervised learning is often considered as a subset of unsupervised learning, but it has grown into its own field due to its success in training large-scale models. It generates its own labels from the data, without any manual labeling.
	- **Semi-Supervised**: This approach combines a small amount of labeled data with a large amount of unlabeled data. It’s useful when labeling data is expensive or time-consuming.
<!--SR:!2025-09-07,4,270-->
+++

How  Works
?
- Problem Statement:
	- project objectives
	- clarity in desired outcomes
	- the scope of the task
	- success criteria
- Data Collection
	- **Relevance:** Collect data should be relevant to the defined problem and include necessary features.
	- **Quality:** Ensure data quality by considering factors like accuracy and ethical use.
	- **Quantity:** Gather sufficient data volume to train a robust model.
	- **Diversity:** Include diverse datasets to capture a broad range of scenarios and patterns.
- Data Cleaning and Preprocessing
	- ***Data Cleaning:*** Address issues such as missing values, outliers and inconsistencies in the data.
	- ***Data Preprocessing:*** Standardize formats, scale values, and encode categorical variables for consistency.
	- ***Data Quality:** Ensure that the data is well-organized and prepared for meaningful analysis.
- Exploratory Data Analysis (EDA)
	- **Exploration:** Use statistical and visual tools to explore patterns in data.
	- ***Patterns and Trends:*** Identify underlying patterns, trends and potential challenges within the dataset.
	- ***Insights:*** Gain valuable insights for informed decisions making in later stages.
	- ***Decision Making:*** Use EDA for feature engineering and model selection.
- Feature Engineering and Selection
	- ***Feature Engineering:*** Create new features or transform existing ones to capture better patterns and relationships.
	- ***Feature Selection:*** Identify subset of features that most significantly impact the model's performance.
	- ***Domain Expertise:*** Use domain knowledge to engineer features that contribute meaningfully for prediction[.](https://www.geeksforgeeks.org/physics/power/)
	- ***Optimization:** Balance set of features for accuracy while minimizing computational complexity.
- Model Selection
	- ***Complexity:*** Consider the complexity of the problem and the nature of the data when choosing a model.
	- ***Decision Factors:*** Evaluate factors like performance, interpretability and scalability when selecting a model.
	- ***Experimentation:*** Experiment with different models to find the best fit for the problem.
- Model Training
	- **Iterative Process:*** Train the model iteratively, adjusting parameters to minimize errors and enhance accuracy.
	- ***Optimization:*** Fine-tune model to optimize its predictive capabilities.
	- ***Validation:*** Rigorously train model to ensure accuracy to new unseen data.
- Model Evaluation and Tuning
	- ***Evaluation Metrics:*** Use metrics like accuracy, precision, recall and F1 score to evaluate model performance.
	- ***Strengths and Weaknesses:*** Identify the strengths and weaknesses of the model through rigorous testing.
	- ***Iterative Improvement:*** Initiate model tuning to adjust hyperparameters and enhance predictive accuracy.
	- ***Model Robustness:*** Iterative tuning to achieve desired levels of model robustness and reliability.
- Model Deployment
	- Integrate with existing systems
	- Enable decision-making using predictions
	- Ensure deployment scalability and security
	- Provide APIs or pipelines for production use
- Model Monitoring & Maintenance
	- Track model performance over time
	- Detect data drift or concept drift
	- Update and retrain the model when accuracy drops
	- Maintain logs and alerts for real-time issues
<!--SR:!2025-09-04,1,230-->
+++

Use Cases
?
- **Image Recognition**: Used in facial recognition, self-driving cars and medical imaging.
- **NLP**: chatbots, translation, sentiment analysis
- **Recommendation Systems**: Netflix, Amazon, Spotify.
- **Predictive Maintenance**: Detects machine issues before they happen.
<!--SR:!2025-09-07,4,270-->
+++

# ML Pipeline
## Data Preprocessing
### Data Cleaning

what -> is a step in machine learning (ML) which involves identifying and removing any missing, duplicate or irrelevant data. The goal of data cleaning is to ensure that the data is accurate, consistent and free of errors as raw data is often noisy, incomplete and inconsistent which can negatively impact the accuracy of model. Clean datasets also helps in [EDA](https://www.geeksforgeeks.org/data-analysis/what-is-exploratory-data-analysis/) which enhances the interpretability of data so that the right actions can be taken based on insights.

Benefits
?
- Error free data
- Data quality
- Accuracy & Efficiency
- Complete Data
- Maintains Data Consistency
+++

How works
?
- **Remove Unwanted Observations:** Eliminate duplicates, irrelevant entries or redundant data that add noise.
- **Fix Structural Errors:** Standardize data formats and variable types for consistency.
- ***Manage Outliers:*** Detect and handle extreme values that can skew results, either by removal or transformation.
- ***Handle Missing Data:*** Address gaps using imputation, deletion or advanced techniques to maintain accuracy and integrity.
+++

Tools
?
- ***OpenRefine:*** A free, open-source tool for cleaning, transforming and enriching messy data with an easy-to-use interface and powerful features like clustering and faceting.
- ***Trifacta Wrangler:*** An AI-powered, user-friendly platform that helps automate data cleaning and transformation workflows for faster, more accurate preparation.
- ***TIBCO Clarity:*** A data profiling and cleansing tool that ensures high-quality, standardized and consistent datasets across diverse sources.
- ***Cloudingo:*** A cloud-based solution focused on deduplication and data cleansing, especially useful for maintaining accurate CRM data.
- ***IBM InfoSphere QualityStage:*** An enterprise-grade tool designed for large-scale, complex data quality management including profiling, matching and cleansing.
+++

Advantages
?
- ****Improved model performance:**** Removal of errors, inconsistencies and irrelevant data helps the model to better learn from the data.
- ****Increased accuracy:**** Helps ensure that the data is accurate, consistent and free of errors.
- ****Better representation of the data:**** Data cleaning allows the data to be transformed into a format that better represents the underlying relationships and patterns in the data.
- ****Improved data quality:**** Improve the quality of the data, making it more reliable and accurate.
- ****Improved data security:**** Helps to identify and remove sensitive or confidential information that could compromise data security.
+++

Disadvantages
?
- ***Time-consuming:*** It is very time consuming task specially for large and complex datasets.
- ***Error-prone:*** It can result in loss of important information.
- ***Cost and resource-intensive:*** It is resource-intensive process that requires significant time, effort and expertise. It can also require the use of specialized software tools.
- ***Overfitting:*** Data cleaning can contribute to overfitting by removing too much data.
+++

### Data Preprocessing

what -> is the first step in any data analysis or machine learning pipeline. It involves cleaning, transforming and organizing raw data into a structured format to ensure accuracy, consistency and readiness for modelling. This step improves data quality and directly impacts the performance of analytical or predictive models.

Advantages
?
- **Improves Data Quality:** Cleans and organizes raw data for better analysis.
- ***Enhances Model Accuracy:*** Removes noise and irrelevant data, leading to more precise predictions.
- ***Reduces Overfitting:*** Handles outliers and redundant features, improving model generalization.
- ***Speeds Up Training:*** Efficiently scaled data reduces computation time.
- ***Ensures Algorithm Compatibility:*** Converts data into formats suitable for machine learning models.
+++

### Feature Scaling
### Feature Extraction
### Feature Engineering
### Feature Selection Techniques
## Exploratory Data Analysis
## Model Evaluation
# Supervised Learning
# Unsupervised Learning
# Reinforcement Learning
# Semi Supervised Learning
# Forecasting Models
# Deployment of ML Models