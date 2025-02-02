# Federalist Papers Data Processing

This project processes the full text of the **Federalist Papers** from [The Library of Congress](https://guides.loc.gov/federalist-papers/full-text). The data is collected, cleaned, and stored in a structured format for further analysis.

## Data Collection
The full text of the Federalist Papers was copied from the source and saved in a raw text file:
raw_data.txt

## Data Preprocessing
The preprocessing was performed using a Jupyter Notebook:
preprocessing.ipynb

### Steps:
1. **Extracted Articles**: The raw text was split into individual articles.
2. **Removed Authors**: Author names were removed from the article text.
3. **Formatted Data**: The cleaned data was structured and saved in CSV format.

The final dataset is stored in:
clean_data.csv

## Data Structure
The `clean_data.csv` file contains the following columns:
- **ArticleNo** – The article number.
- **Author** – The author of the article (disputed authors are marked as `"Unknown"`).
- **Article** – The full text of the article.

## Model Training
The essays were vectorized using the CountVectorizer then 
a Multinomial Naive Bayes Model was trained on the processed data.

### Model Workflow:
1. **Data Preparation** – Loaded `clean_data.csv` and preprocessed the text.
2. **Feature Extraction** – Converted text into numerical representations.
3. **Training** – A machine learning model was trained on the dataset.
4. **Prediction** - The model was feed the unknown author essays. And resulted in outputs with very high certainty. The outputs were stored in the  `output.csv` in the outputs folder along with probability of authorship.