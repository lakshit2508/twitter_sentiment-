# 2020 US Election Sentiment Analysis

![Project Banner](https://example.com/path/to/banner_image.png) *(Optional: Add relevant image)*

## 1. Objective
This project analyzes Twitter sentiment during the 2020 US Presidential Election to:
- Measure public sentiment toward Biden and Trump through social media
- Identify geographic patterns in candidate support
- Predict election outcomes based on sentiment analysis
- Compare engagement metrics between candidates

## 2. Methods & Work Done

### Data Sources
- **Kaggle Datasets**:
  - `hashtag_joebiden.csv`: 126,838 Biden-related tweets
  - `hashtag_donaldtrump.csv`: 185,921 Trump-related tweets  
  *(Source: [Kaggle Twitter US Election 2020 Dataset](https://www.kaggle.com/datasets/manchunhui/us-election-2020-tweets))*

### Methodology
1. **Data Processing**:
   - Cleaned tweets (removed URLs, mentions, special characters)
   - Filtered non-English tweets and duplicates
   - Extracted location data (country/state)

2. **Sentiment Analysis**:
   - Applied VADER sentiment analyzer
   - Classified tweets as Positive/Negative/Neutral
   - Calculated compound sentiment scores

3. **Geospatial Analysis**:
   - Mapped tweet volumes by US states
   - Compared regional sentiment patterns
   - Generated heatmaps of engagement

4. **Statistical Modeling**:
   - Weighted net sentiment calculations
   - Time-series analysis of tweet volumes
   - Comparative visualizations

## 3. Key Results

### Sentiment Findings
- **Trump**: 54.4% positive sentiment (higher base enthusiasm)
- **Biden**: 45.6% positive sentiment but more resilient to negative sentiment
- **Weighted Net Sentiment** (10% opposition weighting):
  - Biden 50.9% vs Trump 49.1% *(closest to actual election results)*

### Geographic Insights
- Trump dominated in Southern/Rural states
- Biden showed stronger support in Coastal/Urban areas
- Correctly predicted 45/50 state outcomes

### Engagement Patterns
- Higher average engagement for Trump tweets
- Biden gained sentiment momentum in final weeks
- Distinct daily activity patterns by candidate

## 4. Limitations

1. **VADER Sentiment Analysis Constraints**:
   - Primarily designed for social media but struggles with:
     - Sarcasm/irony detection
     - Context-dependent political jargon
     - Complex sentence structures

2. **Twitter Demographic Bias**:
   - Over-represents younger, urban populations
   - Includes non-voters and underage Americans (~20% of Twitter users are 13-17)
   - Only ~22% of US adults use Twitter regularly

3. **Platform Representation Gap**:
   - Twitter users represent <10% of actual voters
   - Excludes non-social-media voters (older demographics)
   - Misses private/closed platforms (Facebook groups, WhatsApp)

4. **Data Quality Issues**:
   - Potential bot activity not fully filtered
   - Non-English tweets excluded from analysis
   - Location data often missing/imprecise (~35% of tweets had no GPS)

5. **Temporal Limitations**:
   - Only captures pre-election period (Oct-Nov 2020)
   - Misses late-breaking news impacts
   - No post-election sentiment tracking
   - 
