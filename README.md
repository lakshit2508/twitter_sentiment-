85,921 Trump-related tweets  
  *(Source: [Kaggle Twitter US El# 2020 US Election Sentiment Analysis

![Project Banner](https://example.com/path/to/banner_image.png) *(Optional: Add relevant image)*
###Twitter Sentiment Analysis Report

##Introduction
This project analyzes Twitter sentiment during the 2020 US Presidential Election to gain a deeper understanding of public opinion toward Joe Biden and Donald Trump. It aims to measure sentiment trends, identify geographic patterns in candidate support, and examine how these insights align with actual electoral outcomes.
The primary objectives of this analysis include:
**Measuring public sentiment toward Biden and Trump through social media by classifying tweets as positive, negative, or neutral.

Identifying geographic patterns in candidate support based on the regional distribution of tweets and sentiment scores.

Predicting potential election outcomes by aggregating sentiment data and comparing it to real-world results.

Comparing engagement metrics such as likes and retweets to evaluate which candidate generated more interaction and momentum over time.

Each of these objectives contributes to understanding how public expression on Twitter reflects political alignment and momentum. By using sentiment analysis and geospatial tools, we can explore not only who was supported but also how intensively, where, and when.

Methods & Work Done

Data Sources

The analysis used two Kaggle datasets:

hashtag_joebiden.csv: 1777073 Biden-related tweets

hashtag_donaldtrump.csv: 971087 Trump-related tweets(Source: Kaggle Twitter US Election 2020 Dataset)

Data Processing

Tweets were cleaned by removing URLs, mentions, special characters, and short tweets. Non-English tweets and duplicates were filtered. Location data was extracted where available.

Sentiment Analysis

VADER sentiment analyzer was applied to categorize tweets into positive, neutral, or negative. Compound sentiment scores were calculated to quantify tweet tone.

Geospatial Analysis

We mapped tweet volumes and sentiment by U.S. state to observe regional support and engagement.

Statistical Modeling

Charts and Sentiment weighting were used to examine trends and candidate momentum.

Tools Used

The analysis leveraged several Python libraries:

pandas: for data cleaning, filtering, and manipulation of tweet datasets.

plotly: created interactive plots such as sentiment pie charts and engagement scatter plots.

seaborn: used for statistical data visualization and trend heatmaps.

geopandas: enabled mapping tweet distributions and sentiment scores geographically across US states.

nltk.sentiment.vader.SentimentIntensityAnalyzer: performed sentiment analysis on tweet content, returning polarity scores to classify tweets.

Key Results

Sentiment Findings

Trump received 54.4% positive sentiment, reflecting strong base enthusiasm. Biden had 45.6% positivity but faced fewer sharp declines. Weighted sentiment leaned narrowly toward Biden at 50.9% over Trump’s 49.1%, closely matching actual results. As the weights increased, there was a clear shift towards Biden.

To explain further, weighted sentiment is a metric that assumes not only a candidate's direct positive sentiment matters, but also that a portion of negative sentiment toward the opposing candidate could translate into indirect support. For instance, if a user expresses strong dislike toward Trump, it's likely—though not guaranteed—that they may support Biden, and vice versa. This assumption allows us to approximate real-world voting behavior more accurately.

In our methodology, we calculated net sentiment toward Candidate A as:

Net Sentiment of A = Positive Sentiment of A + α × Negative Sentiment of B

Here, α represents a fraction (like 10%, 25%, or 50%) of the opposing candidate's negative sentiment that is presumed to convert into support for Candidate A. By experimenting with different values of α, we observed how the sentiment balance shifted. As more weight was given to the opponent’s negativity, Biden’s projected support increased steadily, highlighting how public rejection of one candidate can indirectly influence favorability of the other.

When α was set to 50%, the weighted net sentiment was:

Biden: 53.1%

Trump: 46.9%

At α = 100%, the values were:

Biden: 56.3%

Trump: 43.7%

These results closely resemble the actual popular vote share from the 2020 U.S. Presidential Election, where:

Joe Biden received approximately 51.3% of the vote (81.4 million votes)

Donald Trump received approximately 46.8% of the vote (74.4 million votes)

Compared to the weighted sentiment results:

At α = 50%: Biden 53.1%, Trump 46.9%

At α = 100%: Biden 56.3%, Trump 43.7%

The average of these two α-based predictions gives:

Biden: 54.7%

Trump: 45.3%

This clearly shows that about 40–50% of people who disliked one candidate tended to vote for the other, validating our assumption behind the net sentiment model. While this slightly overestimates Biden’s share, it still tracks closely with actual public opinion data.

Geographic Insights

Trump performed better in rural and southern states, while Biden was stronger in coastal and urban areas. The analysis successfully reflects public opinion trends in over 40 states.

Engagement Patterns

Trump’s tweets had higher average interactions. However, Biden gained positive momentum nearing election day, with distinct daily tweet trends for each candidate. Biden also had higher average engagement, with 10.58 likes per tweet compared to Trump's 7.41 likes per tweet.

Word Frequency

Common Biden tweet terms included "president", "vote", and "covid". Trump tweets focused on words like "fraud", "MAGA", and "fake".

Limitations

VADER struggles with sarcasm and complex political language. Twitter data skews younger and urban, omitting older or offline voters. Location data was incomplete, and potential bot activity wasn't fully filtered.

Conclusion

Social media sentiment analysis provided valuable election insights. While Trump had high engagement, Biden’s stable sentiment and regional strength were key. The trends captured in this project mirror real electoral outcomes and offer a framework for future digital political analysis.


