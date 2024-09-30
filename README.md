# Text Classification using Logistic Regression

This repository contains a text classification model that automatically classifies whether a text is pro-Trump or not, utilizing machine learning algorithms (specifically logistic regression) along with natural language processing (NLP) techniques to analyze the content of the text.

## Overview

The model is trained on two datasets containing comments and posts from two popular platforms:
- **Parler** (a social media platform associated with pro-Trump supporters)
- **Reddit** (specifically, posts from the subreddit `/r/politics`)

The data was collected between **December 1, 2020**, and **January 11, 2021**, a timeframe chosen due to the events surrounding the **Capitol riot** on January 6, 2021, when Trump supporters attacked the U.S. Capitol.

## Preprocessing

To improve the quality of the text data and reduce noise, several preprocessing steps were applied:

- **Removing user handles** (e.g., `@username`)
- **Removing specific keywords**: After analyzing the most influential features for the model, certain keywords that strongly influenced the model's decision-making were removed.
- **Eliminating stop words** (common words like "the," "and," etc.)
- **Removing unwanted characters** (e.g., special characters, punctuation)
- **Cleaning URLs** and irrelevant links
- **Minimum text length filtering**: A threshold was set for the minimum text length of each post or comment. Through experimentation, it was determined that excluding shorter phrases (less than 20 words) led to better model performance, increasing accuracy from **0.78** to **0.81**.

## Model and Evaluation

The logistic regression model was trained and evaluated across **four different datasets** to test its ability to distinguish between pro-Trump (Parler) and non-pro-Trump (Reddit) content, as well as to identify toxic and offensive speech. The model's performance was evaluated using confusion matrices and classification reports.

### Datasets Used for Evaluation

1. **Banned Subreddits (The_Donald, greatawakening):**
   - The model was tested on datasets consisting of 10,000 comments each from subreddits associated with alt-right ideologies (e.g., **The_Donald**, **greatawakening**) and a politically neutral subreddit (`/r/politics`).
   - The goal was to evaluate how accurately the model could classify comments from these subreddits and identify misclassifications where it incorrectly labels a Reddit post as pro-Trump (i.e., "Parler"). This comparison helped assess the model’s robustness across different sources.

2. **CrowdFlower Twitter Dataset (Hate Speech and Offensive Posts):**
   - This dataset contains labeled tweets that were identified as hate speech or offensive language.
   - The model was evaluated for its ability to differentiate between politically correct content (represented by Reddit data) and hate speech/offensive content (represented by Parler).

3. **Waseem 2015 Twitter Dataset (Racist Posts):**
   - The dataset focuses on tweets labeled as racist.
   - The model’s performance was assessed similarly to determine how well it could identify racist content compared to non-racist, politically correct text.

4. **Kaggle Wikipedia Toxic Comments Dataset:**
   - This dataset includes comments from Wikipedia, some of which are labeled as toxic.
   - The model was tested for its ability to distinguish between toxic comments and politically correct comments.

### Evaluation Methodology

For datasets 2, 3, and 4 (CrowdFlower, Waseem, Kaggle):
- A **confusion matrix** and **classification report** were used to measure the model’s accuracy, precision, recall, and F1 score.
- The model’s primary task was to distinguish between politically correct texts (Reddit data) and toxic/offensive content (Parler data).



## Conclusion

This project demonstrates the use of a logistic regression model for text classification, focusing on political sentiment analysis (pro-Trump or not) while evaluating its ability to identify hate speech, racist posts, and toxic comments. By leveraging natural language processing techniques and applying thorough preprocessing, the model delivers strong performance across multiple datasets.

Feel free to explore the code and modify it to suit your needs!
