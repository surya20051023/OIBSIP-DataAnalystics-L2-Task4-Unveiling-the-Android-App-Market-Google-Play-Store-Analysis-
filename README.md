# OIBSIP-DataAnalystics-L2-Task4-Unveiling-the-Android-App-Market-Google-Play-Store-Analysis-
# Unveiling the Android App Market — Google Play Store Analysis

## Project Overview

This project performs an exploratory data analysis of the Google Play Store ecosystem to understand app market trends, category competition, user ratings, pricing strategies, installation patterns, and customer sentiment.

Using Python and its data analysis libraries, the project cleans and processes app information and user reviews, creates visualizations, and extracts meaningful insights. VADER sentiment analysis is applied to classify user reviews into positive, negative, and neutral categories. An interactive Plotly visualization allows users to explore app performance.

## Objectives

- Clean and preprocess the Google Play Store Apps and User Reviews datasets.
- Identify the most common and saturated app categories.
- Analyze app ratings and average ratings by category.
- Explore relationships between app size and installation counts.
- Compare free and paid apps and examine pricing trends.
- Estimate a rough paid-app value proxy by category.
- Perform sentiment analysis on user reviews using VADER.
- Compare sentiment patterns across app categories.
- Create at least one interactive visualization using Plotly.
- Summarize three data-driven insights from the analysis.

## Technologies Used

- **Python** — Programming language
- **Pandas** — Data cleaning and manipulation
- **NumPy** — Numerical operations
- **Matplotlib** — Data visualization
- **Seaborn** — Statistical visualizations
- **Plotly** — Interactive charts
- **NLTK VADER** — Sentiment analysis
- **Jupyter Notebook** — Development environment

## Dataset

The project uses the Google Play Store dataset available on Kaggle.

**Dataset link:** https://www.kaggle.com/datasets/lava18/google-play-store-apps

The dataset contains two files:

1. `googleplaystore.csv` — App details such as category, rating, reviews, size, installs, type, and price.
2. `googleplaystore_user_reviews.csv` — User review text and associated sentiment information.

## Project Structure

```text
Google-Play-Store-Analysis/
│
├── googleplaystore.csv
├── googleplaystore_user_reviews.csv
├── google_play_store_analysis.ipynb
├── requirements.txt
│
└── outputs/
    ├── cleaned_apps.csv
    ├── reviews_with_vader_sentiment.csv
    ├── category_app_counts.csv
    ├── category_ratings.csv
    ├── category_sentiment.csv
    ├── estimated_paid_app_value_by_category.csv
    └── interactive_app_ratings.html
```

## Installation

Install Python and Jupyter Notebook, then install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn plotly nltk
```

Alternatively, create a `requirements.txt` file containing:

```text
pandas
numpy
matplotlib
seaborn
plotly
nltk
```

Install the dependencies with:

```bash
pip install -r requirements.txt
```

## How to Run the Project

1. Download the dataset from Kaggle.
2. Extract the files into the project directory.
3. Open a terminal or command prompt in the project directory.
4. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `google_play_store_analysis.ipynb`.
6. Run the notebook cells in order, starting with library imports and dataset loading.
7. Review the generated charts, sentiment summaries, and output files.

The notebook downloads the VADER sentiment lexicon when required.

## Project Workflow

### 1. Data Loading and Inspection

Load the app metadata and user review datasets separately. Inspect their shapes, columns, data types, missing values, and duplicate records.

### 2. Data Cleaning

- Remove duplicate records.
- Handle missing and invalid values.
- Convert ratings, review counts, installations, and prices to numeric types.
- Remove commas, plus signs, and currency symbols where appropriate.
- Convert app sizes into a common MB unit.
- Retain missing ratings where the app can still contribute to other analyses.

### 3. Category Analysis

Create a bar chart showing the number of apps in each category. Identify categories with the largest number of listings. App count is treated as an indicator of market saturation, not a direct measurement of competition or profitability.

### 4. Ratings Analysis

Explore the distribution of app ratings and calculate average ratings by category. Consider the number of rated apps when comparing categories to avoid drawing conclusions from small samples.

### 5. App Size and Installation Analysis

Use scatter plots and correlation measures to explore the relationship between app size and installation counts. Logarithmic scales help display data with widely varying values.

### 6. Pricing Analysis

Compare free and paid apps and visualize paid-app prices. Estimate a rough gross-value proxy by multiplying the listed price by the approximate installation count.

**Important limitation:** This estimate is not actual revenue. Installation counts may be approximate, and installs do not necessarily represent purchases. The calculation does not account for refunds, taxes, regional pricing, subscriptions, in-app purchases, or platform revenue sharing.

### 7. Sentiment Analysis

Use VADER to analyze review text and assign each review one of three labels:

- **Positive:** Compound score greater than or equal to 0.05
- **Negative:** Compound score less than or equal to -0.05
- **Neutral:** Compound score between -0.05 and 0.05

Visualize overall sentiment distribution and compare positive and negative sentiment rates across categories. VADER results are estimates and may not correctly interpret sarcasm, specialized app terminology, or all translated reviews.

### 8. Interactive Visualization

Create an interactive Plotly scatter plot comparing app ratings and review counts. Categories are distinguished by color, installation counts influence marker size, and hovering over a point displays app details.

The interactive chart is saved as an HTML file in the `outputs/` directory.

### 9. Key Insights and Conclusion

Use the generated results to report three evidence-based findings:

1. **Category distribution:** Identify categories with the highest app counts and discuss what this may indicate about market saturation.
2. **Ratings and installations:** Report observed rating patterns and the relationship between app size and installations.
3. **User sentiment:** Identify categories with relatively high positive or negative review rates, considering review counts and category-matching coverage.

Use the actual results produced by the notebook rather than assuming these findings in advance.

## Expected Outcomes

- Cleaned app and review datasets.
- Visualizations of category counts, ratings, app size, installations, and pricing.
- A comparison of free and paid applications.
- VADER-based review sentiment labels and category sentiment summaries.
- An interactive Plotly chart saved as an HTML file.
- Three data-driven insights about the Google Play Store ecosystem.

## Applications

- Understanding app market trends.
- Identifying heavily represented app categories.
- Exploring user satisfaction through ratings and reviews.
- Supporting app development and market research.
- Comparing pricing strategies and approximate installation-based value.

## Conclusion

This project demonstrates how data analysis, visualization, and sentiment analysis can be combined to study the Google Play Store ecosystem. It provides insights into app distribution, ratings, pricing, installation patterns, and user feedback. The findings can support market research and app-development decisions, while recognizing that historical dataset coverage, missing values, approximate installation counts, and sentiment-model limitations affect interpretation.

## References

- Google Play Store dataset: https://www.kaggle.com/datasets/lava18/google-play-store-apps
- NLTK VADER documentation: https://www.nltk.org/api/nltk.sentiment.vader.html
- NLTK sentiment analysis guide: https://www.nltk.org/howto/sentiment.html
- Pandas documentation: https://pandas.pydata.org/docs/
- Seaborn documentation: https://seaborn.pydata.org/
- Plotly Python documentation: https://plotly.com/python/
