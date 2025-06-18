<div align="center">
  <img src="https://github.com/user-attachments/assets/309a716f-2361-40fe-af09-6829149e5f1b" alt="Sentiment Plot" width="400"/>
</div>

# Twitter Sentiment Analysis Report

## Introduction

This project analyzes Twitter sentiment during the 2020 US Presidential Election to gain a deeper understanding of public opinion toward Joe Biden and Donald Trump. It measures sentiment trends, identifies geographic patterns in candidate support, and examines how these insights align with actual electoral outcomes.

The main objectives of this analysis are:

- Measuring public sentiment toward Biden and Trump through social media by classifying tweets as positive, negative, or neutral.
- Identifying geographic patterns in candidate support based on the regional distribution of tweets and sentiment scores.
- Predicting potential election outcomes by aggregating sentiment data and comparing it to real-world results.
- Comparing engagement metrics such as likes and retweets to evaluate which candidate generated more interaction and momentum over time.

By using sentiment analysis and geospatial tools, we explore not only who was supported but also how intensively, where, and when.

## Methods & Work Done

### Data Sources

- **hashtag_joebiden.csv**: 1,777,073 Biden-related tweets  
- **hashtag_donaldtrump.csv**: 971,087 Trump-related tweets  
(Source: Kaggle - Twitter US Election 2020 Dataset)

### Data Processing

- Cleaned tweets by removing URLs, mentions, special characters, and short or duplicate tweets.
- Filtered out non-English tweets.
- Extracted location data where available.

### Sentiment Analysis

- Used VADER sentiment analyzer to categorize tweets as positive, neutral, or negative.
- Calculated compound sentiment scores to quantify tweet tone.

### Geospatial Analysis

- Mapped tweet volumes and sentiment across U.S. states to observe regional support and engagement.

### Statistical Modeling

- Used charts and a sentiment weighting formula to examine sentiment trends and predict candidate momentum.

### Tools Used

- **pandas**: for data manipulation and processing  
- **plotly**: for interactive pie charts and scatter plots  
- **seaborn**: for visualizing trends and heatmaps  
- **geopandas**: for geographic mapping of tweets  
- **nltk.vader**: for performing sentiment analysis using VADER

## Key Results

### Sentiment Findings

- Trump received **54.4%** positive sentiment, indicating a highly engaged base.
- Biden had **45.6%** positive sentiment but with fewer sharp declines.
- **Weighted sentiment** leaned toward Biden at **50.9%** vs. Trump’s **49.1%**, closely matching actual election results.

We introduced a **weighted sentiment model** based on the idea that a portion of the negative sentiment for one candidate indirectly supports the other:

**Net Sentiment (Candidate A) = Positive Sentiment (A) + α × Negative Sentiment (B)**

Where **α** is a conversion factor (e.g., 10%, 25%, 50%, or 100%).

- At α = 50%:  
  Biden: **53.1%**  
  Trump: **46.9%**

- At α = 100%:  
  Biden: **56.3%**  
  Trump: **43.7%**

These weighted estimates closely align with the actual 2020 vote share:

- Biden: **51.3%** (81.4 million votes)  
- Trump: **46.8%** (74.4 million votes)

Taking the average of α = 50% and α = 100% gives:

- Biden: **54.7%**  
- Trump: **45.3%**

This confirms our hypothesis that 40–50% of negative sentiment toward one candidate likely translated into support for the other.

<div align="center">
  <img src="https://github.com/user-attachments/assets/5b18816b-ddd5-44f9-bda4-3c5e882f9fa9" alt="Sentiment Plot" width="700"/>
</div>

### Geographic Insights

- Trump showed stronger support in rural and southern states.
- Biden dominated coastal and urban regions.
- Sentiment trends across over 40 states closely reflected public opinion patterns.
- The analysis also unfolded global sentiments toward the US elections, revealing international trends for both Biden and Trump through worldwide tweet activity.

Global Tweet for Trump
  
<div align="center">
  <img src="https://github.com/user-attachments/assets/96eae371-ecde-4ce6-b770-43777a13d998" alt="Sentiment Plot" width="700"/>
</div>
                                    
Global Tweet for Biden
                                    
<div align="center">
  <img src="https://github.com/user-attachments/assets/d40bd0f9-9a8a-4e94-a87c-ce8f2c284f96" alt="Sentiment Plot" width="700"/>
</div>

### Engagement Patterns

- Trump’s tweets had **higher total interactions**, but:
- **Biden had higher average engagement**, with **10.58 likes per tweet** versus **Trump’s 7.41 likes per tweet**.
- Biden gained more consistent momentum closer to election day.

### Word Frequency Insights

- Common Biden-related terms: `"president"`, `"vote"`, `"covid"`
- Common Trump-related terms: `"fraud"`, `"MAGA"`, `"fake"`

## Limitations

- VADER may misinterpret sarcasm and complex political language.
- Twitter users skew younger and urban, missing older or offline voters.
- Location data was incomplete for ~35% of tweets.
- Bot accounts and coordinated activity were not fully filtered.

## Conclusion

Social media sentiment analysis provided strong insight into election dynamics. While Trump maintained high engagement, Biden’s consistent sentiment and growing momentum played a critical role. The weighted sentiment model, validated by vote share comparisons, serves as a useful framework for future digital political forecasting.



