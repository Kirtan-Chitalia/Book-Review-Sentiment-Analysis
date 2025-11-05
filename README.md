# Book Review Sentiment Analysis

This project performs sentiment analysis on a dataset of book reviews. The goal is to classify reviews as either positive or negative based on the text of the review and its summary.

## Dataset

The dataset used in this project is `all_kindle_review.csv`. It contains various information about Kindle book reviews, including the review text, rating, and a summary.

## Methodology

1. **Data Loading and Exploration**: The data is loaded into a pandas DataFrame, and initial exploration is performed to understand its structure and identify missing values.
2. **Data Cleaning and Preprocessing**:
    - Irrelevant columns are dropped.
    - Missing values in the 'summary' column are removed.
    - A new 'tags' column is created by combining the 'reviewText' and 'summary' columns.
    - The 'rating' column is binarized, with ratings 1 and 2 classified as negative (0) and ratings 3, 4, and 5 classified as positive (1).
    - Text cleaning is performed on the 'tags' column to remove HTML tags, URLs, non-alphabetic characters, and stop words.
    - Lemmatization is applied to the cleaned text.
3. **Data Vectorization**: The cleaned text data is vectorized using both CountVectorizer and TfidfVectorizer to convert the text into numerical representations.
4. **Model Training**: Logistic Regression models are trained on both the CountVectorizer and TfidfVectorizer data.
5. **Model Evaluation**: The performance of the models is evaluated using confusion matrices, classification reports, and accuracy scores.
6. **Sentiment Prediction**: A function is created to predict the sentiment of new text inputs using the trained Logistic Regression model.

## Code

The project is implemented in a Jupyter Notebook, with the following key steps:

- Loading and initial exploration of the data.
- Data cleaning and preprocessing using libraries like `BeautifulSoup` and `nltk`.
- Text vectorization using `sklearn.feature_extraction.text`.
- Training and evaluation of Logistic Regression models using `sklearn.linear_model` and `sklearn.metrics`.
- Implementing a function for sentiment prediction.

## Results

The trained Logistic Regression models achieved accuracies of approximately 83% on the test dataset, indicating a reasonable ability to classify book review sentiment.

## How to Run the Code

1. Ensure you have the necessary libraries installed (`pandas`, `numpy`, `nltk`, `scikit-learn`, `beautifulsoup4`).
2. Download the `all_kindle_review.csv` dataset and place it in the specified path or update the path in the notebook.
3. Run the cells in the Jupyter Notebook sequentially.

## Future Work

- Experiment with other sentiment analysis models (e.g., Naive Bayes, Support Vector Machines, deep learning models).
- Perform hyperparameter tuning to optimize model performance.
- Explore more advanced text preprocessing techniques.
- Analyze the most important features (words) for sentiment classification.
