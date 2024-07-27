# 🐦 Sentiment and NLP Analysis Project

## 📋 Project Overview

This project aims to analyze the sentiment of tweets, leveraging natural language processing (NLP) techniques to clean and process tweet data. 
The objective is to derive insights from the tweets by analyzing their polarity and subjectivity, and visualize the results. This will help in understanding public opinion and trends based on Twitter data. 🌍💬

## 📊 Dataset Description

The dataset used in this project contains the following information about tweets:

- **Tweets**: Original text of the tweet.
- **Retweets**: Number of retweets of the current tweet.
- **Likes**: Number of likes of the current tweet.
- **Date**: Date of creation of the tweet.
- **Cleaned_tweets**: Text of the tweet after removing 'RT', hashtags, hyperlinks, mentions, emojis, leading, and trailing whitespaces.

## 🛠️ Activities Performed

### 1. Data Cleaning and Text Preprocessing 🧹
1. **Data Cleaning**:
    - Removed rows with empty strings in the 'Cleaned_tweets' column after cleanup.
    - Removed duplicates to ensure data quality.
    
2. **Text Cleaning**:
    - Removed 'RT', hashtags, hyperlinks, mentions, emojis, and leading/trailing whitespaces.

### 2. Sentiment Analysis 💬🔍
A very accurate definition of polarity and subjectivity in sentiment analysis is provided by Christian Meyer:

- **Polarity**: Refers to the strength of an opinion. It can be positive or negative. For example, "I don’t think I’ll buy this item because my previous experience with a similar item wasn’t so good." has a negative polarity.

- **Subjectivity**: Refers to the degree to which a person is personally involved in an object. For example, "I’m very happy with my new smartphone because it has the highest performance available on the market." is subjective because it reflects personal experience and feelings.

### 3. Visualizing the Results 📊
- **Visualizations**: Created visualizations to represent the analysis results clearly.

### 4. Performance NLP Analysis 🧠📈
- **Analysis of Common Words, People, and Organizations**:
    - Created a new dataframe with the tweets column for further analysis.
    - Applied stemming and removed stop words.
    
4.1 **Stemming and Removing Stop Words**:
    - Reduced words to their root form using stemming techniques.

4.2 **Creating Visualizations**:
    - **Top Words Most Used**: Visualized the most frequently used words in tweets.
    - **Word Cloud**: Created a word cloud to visualize common words.
    - **Top Persons Mentioned**: Identified top-mentioned individuals using Spacy (NLP).
    - **Top Companies Mentioned**: Identified top-mentioned companies using Spacy (NLP).

## 🚀 Steps to Run the Project

### 1. Install Required Libraries
```bash
pip install pandas numpy matplotlib seaborn spacy tensorflow
```

### 2. Load and Clean the Dataset


### 3. Perform Sentiment Analysis
```python
from textblob import TextBlob

# Define functions to calculate polarity and subjectivity
def get_polarity(text):
    return TextBlob(text).sentiment.polarity

def get_subjectivity(text):
    return TextBlob(text).sentiment.subjectivity

# Apply functions to dataset
data['Polarity'] = data['Cleaned_tweets'].apply(get_polarity)
data['Subjectivity'] = data['Cleaned_tweets'].apply(get_subjectivity)
```

### 4. Visualize the Results
```python
import matplotlib.pyplot as plt

# Plotting polarity and subjectivity

```

### 5. Perform NLP Analysis
```python
import spacy
nlp = spacy.load('en_core_web_sm')

# Function to extract entities
def extract_entities(text):
    doc = nlp(text)
    return [(ent.text, ent.label_) for ent in doc.ents]

data['Entities'] = data['Cleaned_tweets'].apply(extract_entities)
```

## 💡 Use Cases

Here are some potential use cases for this sentiment analysis project:

- **Brand Monitoring**: Understand public sentiment towards a brand or product.
- **Market Research**: Gauge customer opinions and trends to make informed business decisions.
- **Customer Feedback Analysis**: Analyze feedback to improve products and services.
- **Event Monitoring**: Track sentiment around events or campaigns to measure impact.

## 📈 Communicating Benefits to Managers

### Benefits:

1. **Enhanced Decision Making**: Data-driven insights help make better strategic decisions.
2. **Customer Insights**: Understand customer sentiment to tailor marketing strategies and improve products.
3. **Competitive Advantage**: Stay ahead by monitoring public sentiment and responding proactively.

### Communication Tips:

- **Focus on ROI**: Highlight how sentiment analysis can lead to increased customer satisfaction and revenue.
- **Data-Driven Insights**: Emphasize the importance of leveraging data for strategic advantages.
- **Scalability**: Explain how the solution can scale with growing data and business needs.
