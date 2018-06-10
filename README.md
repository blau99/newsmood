

```python
import tweepy
import numpy as np
import pandas as pd
from datetime import datetime
import matplotlib.pyplot as plt
from matplotlib import style
```


```python
# Import and Initialize Sentiment Analyzer
from vaderSentiment.vaderSentiment import SentimentIntensityAnalyzer
analyzer = SentimentIntensityAnalyzer()
```


```python
# Twitter API Keys
from config import (consumer_key, 
                    consumer_secret, 
                    access_token, 
                    access_token_secret)

# Setup Tweepy API Authentication
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth, parser=tweepy.parsers.JSONParser())
```


```python
# Target User Account
target_user = ["@BBCBreaking"]


# Variables for holding sentiments
sentiments_1 = []

for target in target_user: 
    # Variables for holding sentiments
    compound_list = []
    positive_list = []
    negative_list = []
    neutral_list = []

    # Counter
    counter = 1

    # Loop through 10 pages of tweets (total 100 tweets)
    for x in range(5):

        # Get all tweets from home feed
        public_tweets = api.user_timeline(target, page=x)

        # Loop through all tweets
        for tweet in public_tweets:

            # Run Vader Analysis on each tweet
            results = analyzer.polarity_scores(tweet["text"])
            compound = results["compound"]
            pos = results["pos"]
            neu = results["neu"]
            neg = results["neg"]
            tweets_ago = counter

            # Add each value to the appropriate list
            compound_list.append(compound)
            positive_list.append(pos)
            negative_list.append(neg)
            neutral_list.append(neu)

            sentiments_1.append({"Source": target,"Date": tweet["created_at"],
                               "Tweet": tweet["text"],
                               "Compound": compound,
                               "Positive": pos,
                               "Negative": neu,
                               "Neutral": neg, 
                               "Tweets Ago": counter})
            # Add to counter 
            counter += 1
            
bbc_compound = np.mean(compound_list)
```


```python
# Target User Account
target_user = ["@CBSNews"]


# Variables for holding sentiments
sentiments_2 = []

for target in target_user: 
    # Variables for holding sentiments
    compound_list = []
    positive_list = []
    negative_list = []
    neutral_list = []

    # Counter
    counter = 1

    # Loop through 10 pages of tweets (total 100 tweets)
    for x in range(5):

        # Get all tweets from home feed
        public_tweets = api.user_timeline(target, page=x)

        # Loop through all tweets
        for tweet in public_tweets:

            # Run Vader Analysis on each tweet
            results = analyzer.polarity_scores(tweet["text"])
            compound = results["compound"]
            pos = results["pos"]
            neu = results["neu"]
            neg = results["neg"]
            tweets_ago = counter

            # Add each value to the appropriate list
            compound_list.append(compound)
            positive_list.append(pos)
            negative_list.append(neg)
            neutral_list.append(neu)

            sentiments_2.append({"Source": target,"Date": tweet["created_at"],
                               "Tweet": tweet["text"],
                               "Compound": compound,
                               "Positive": pos,
                               "Negative": neu,
                               "Neutral": neg, 
                               "Tweets Ago": counter})
            # Add to counter 
            counter += 1

cbs_compound = np.mean(compound_list)
```


```python
# Target User Account
target_user = ["@cnnbrk"]


# Variables for holding sentiments
sentiments_3 = []

for target in target_user: 
    # Variables for holding sentiments
    compound_list = []
    positive_list = []
    negative_list = []
    neutral_list = []

    # Counter
    counter = 1

    # Loop through 10 pages of tweets (total 100 tweets)
    for x in range(5):

        # Get all tweets from home feed
        public_tweets = api.user_timeline(target, page=x)

        # Loop through all tweets
        for tweet in public_tweets:

            # Run Vader Analysis on each tweet
            results = analyzer.polarity_scores(tweet["text"])
            compound = results["compound"]
            pos = results["pos"]
            neu = results["neu"]
            neg = results["neg"]
            tweets_ago = counter

            # Add each value to the appropriate list
            compound_list.append(compound)
            positive_list.append(pos)
            negative_list.append(neg)
            neutral_list.append(neu)

            sentiments_3.append({"Source": target,"Date": tweet["created_at"],
                               "Tweet": tweet["text"],
                               "Compound": compound,
                               "Positive": pos,
                               "Negative": neu,
                               "Neutral": neg, 
                               "Tweets Ago": counter})
            # Add to counter 
            counter += 1
            
cnn_compound = np.mean(compound_list)
```


```python
# Target User Account
target_user = ["@FoxNews"]


# Variables for holding sentiments
sentiments_4 = []

for target in target_user: 
    # Variables for holding sentiments
    compound_list = []
    positive_list = []
    negative_list = []
    neutral_list = []

    # Counter
    counter = 1

    # Loop through 10 pages of tweets (total 100 tweets)
    for x in range(5):

        # Get all tweets from home feed
        public_tweets = api.user_timeline(target, page=x)

        # Loop through all tweets
        for tweet in public_tweets:

            # Run Vader Analysis on each tweet
            results = analyzer.polarity_scores(tweet["text"])
            compound = results["compound"]
            pos = results["pos"]
            neu = results["neu"]
            neg = results["neg"]
            tweets_ago = counter

            # Add each value to the appropriate list
            compound_list.append(compound)
            positive_list.append(pos)
            negative_list.append(neg)
            neutral_list.append(neu)

            sentiments_4.append({"Source": target,"Date": tweet["created_at"],
                               "Tweet": tweet["text"],
                               "Compound": compound,
                               "Positive": pos,
                               "Negative": neu,
                               "Neutral": neg, 
                               "Tweets Ago": counter})
            # Add to counter 
            counter += 1
            
fox_compound = np.mean(compound_list)
```


```python
# Target User Account
target_user = ["@nytimes"]


# Variables for holding sentiments
sentiments_5 = []

for target in target_user: 
    # Variables for holding sentiments
    compound_list = []
    positive_list = []
    negative_list = []
    neutral_list = []

    # Counter
    counter = 1

    # Loop through 10 pages of tweets (total 100 tweets)
    for x in range(5):

        # Get all tweets from home feed
        public_tweets = api.user_timeline(target, page=x)

        # Loop through all tweets
        for tweet in public_tweets:

            # Run Vader Analysis on each tweet
            results = analyzer.polarity_scores(tweet["text"])
            compound = results["compound"]
            pos = results["pos"]
            neu = results["neu"]
            neg = results["neg"]
            tweets_ago = counter

            # Add each value to the appropriate list
            compound_list.append(compound)
            positive_list.append(pos)
            negative_list.append(neg)
            neutral_list.append(neu)

            sentiments_5.append({"Source": target,"Date": tweet["created_at"],
                               "Tweet": tweet["text"],
                               "Compound": compound,
                               "Positive": pos,
                               "Negative": neu,
                               "Neutral": neg, 
                               "Tweets Ago": counter})
            # Add to counter 
            counter += 1
            
nyt_compound = np.mean(compound_list)
```


```python
# Convert sentiments to DataFrame
sentiments1_pd = pd.DataFrame.from_dict(sentiments_1)
sentiments1_pd.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Compound</th>
      <th>Date</th>
      <th>Negative</th>
      <th>Neutral</th>
      <th>Positive</th>
      <th>Source</th>
      <th>Tweet</th>
      <th>Tweets Ago</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.3182</td>
      <td>Sat Jun 09 23:52:23 +0000 2018</td>
      <td>0.887</td>
      <td>0.000</td>
      <td>0.113</td>
      <td>@BBCBreaking</td>
      <td>The G7 summit ends in disarray after US Presid...</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.0000</td>
      <td>Fri Jun 08 21:32:33 +0000 2018</td>
      <td>1.000</td>
      <td>0.000</td>
      <td>0.000</td>
      <td>@BBCBreaking</td>
      <td>Actress Emma Thompson becomes a dame, with Liv...</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-0.4215</td>
      <td>Fri Jun 08 19:58:46 +0000 2018</td>
      <td>0.676</td>
      <td>0.203</td>
      <td>0.122</td>
      <td>@BBCBreaking</td>
      <td>American special forces soldier killed in fire...</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.0000</td>
      <td>Fri Jun 08 18:35:39 +0000 2018</td>
      <td>1.000</td>
      <td>0.000</td>
      <td>0.000</td>
      <td>@BBCBreaking</td>
      <td>World leaders assemble for 'family photo' at G...</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-0.8176</td>
      <td>Fri Jun 08 16:57:32 +0000 2018</td>
      <td>0.638</td>
      <td>0.362</td>
      <td>0.000</td>
      <td>@BBCBreaking</td>
      <td>Man charged with manslaughter of 100-year-old ...</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Convert sentiments to DataFrame
sentiments2_pd = pd.DataFrame.from_dict(sentiments_2)
sentiments2_pd.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Compound</th>
      <th>Date</th>
      <th>Negative</th>
      <th>Neutral</th>
      <th>Positive</th>
      <th>Source</th>
      <th>Tweet</th>
      <th>Tweets Ago</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>-0.5106</td>
      <td>Sun Jun 10 03:18:04 +0000 2018</td>
      <td>0.784</td>
      <td>0.216</td>
      <td>0.000</td>
      <td>@CBSNews</td>
      <td>Video of TSA agents searching 96-year-old woma...</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.2960</td>
      <td>Sun Jun 10 03:03:04 +0000 2018</td>
      <td>0.733</td>
      <td>0.093</td>
      <td>0.173</td>
      <td>@CBSNews</td>
      <td>Pay Attention: Exploring how forest bathing be...</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-0.3182</td>
      <td>Sun Jun 10 02:48:06 +0000 2018</td>
      <td>0.796</td>
      <td>0.204</td>
      <td>0.000</td>
      <td>@CBSNews</td>
      <td>Group photo masks underlying tension at G-7 su...</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-0.1154</td>
      <td>Sun Jun 10 02:40:10 +0000 2018</td>
      <td>0.935</td>
      <td>0.065</td>
      <td>0.000</td>
      <td>@CBSNews</td>
      <td>He risked his life, traveling thousands of mil...</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.5719</td>
      <td>Sun Jun 10 02:33:04 +0000 2018</td>
      <td>0.791</td>
      <td>0.000</td>
      <td>0.209</td>
      <td>@CBSNews</td>
      <td>Meghan Markle joins Trooping the Color ceremon...</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Convert sentiments to DataFrame
sentiments3_pd = pd.DataFrame.from_dict(sentiments_3)
sentiments3_pd.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Compound</th>
      <th>Date</th>
      <th>Negative</th>
      <th>Neutral</th>
      <th>Positive</th>
      <th>Source</th>
      <th>Tweet</th>
      <th>Tweets Ago</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.0000</td>
      <td>Sun Jun 10 01:39:09 +0000 2018</td>
      <td>1.000</td>
      <td>0.000</td>
      <td>0.000</td>
      <td>@cnnbrk</td>
      <td>After Trump reversed his position on a G7 stat...</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-0.7501</td>
      <td>Sat Jun 09 23:46:08 +0000 2018</td>
      <td>0.738</td>
      <td>0.262</td>
      <td>0.000</td>
      <td>@cnnbrk</td>
      <td>Trump calls Canada's Trudeau "very dishonest a...</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.5859</td>
      <td>Sat Jun 09 22:56:43 +0000 2018</td>
      <td>0.826</td>
      <td>0.000</td>
      <td>0.174</td>
      <td>@cnnbrk</td>
      <td>Justify becomes the 13th thoroughbred to win t...</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-0.6705</td>
      <td>Sat Jun 09 22:24:01 +0000 2018</td>
      <td>0.791</td>
      <td>0.209</td>
      <td>0.000</td>
      <td>@cnnbrk</td>
      <td>Mexican congressional candidate Fernando Puron...</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-0.5574</td>
      <td>Sat Jun 09 21:40:48 +0000 2018</td>
      <td>0.847</td>
      <td>0.153</td>
      <td>0.000</td>
      <td>@cnnbrk</td>
      <td>Former Fleetwood Mac guitarist Danny Kirwan, w...</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Convert sentiments to DataFrame
sentiments4_pd = pd.DataFrame.from_dict(sentiments_4)
sentiments4_pd.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Compound</th>
      <th>Date</th>
      <th>Negative</th>
      <th>Neutral</th>
      <th>Positive</th>
      <th>Source</th>
      <th>Tweet</th>
      <th>Tweets Ago</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.2263</td>
      <td>Sun Jun 10 03:28:00 +0000 2018</td>
      <td>0.909</td>
      <td>0.000</td>
      <td>0.091</td>
      <td>@FoxNews</td>
      <td>Nile Gardiner: "You have protectionist tariffs...</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-0.1531</td>
      <td>Sun Jun 10 03:21:00 +0000 2018</td>
      <td>0.897</td>
      <td>0.103</td>
      <td>0.000</td>
      <td>@FoxNews</td>
      <td>'Jersey Shore' star Mike 'The Situation' Sorre...</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.3818</td>
      <td>Sun Jun 10 03:14:00 +0000 2018</td>
      <td>0.729</td>
      <td>0.000</td>
      <td>0.271</td>
      <td>@FoxNews</td>
      <td>President @realDonaldTrump promises "America F...</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-0.3612</td>
      <td>Sun Jun 10 03:07:00 +0000 2018</td>
      <td>0.828</td>
      <td>0.172</td>
      <td>0.000</td>
      <td>@FoxNews</td>
      <td>#MeghanMarkle criticized for ‘inappropriate’ o...</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-0.5302</td>
      <td>Sun Jun 10 03:00:00 +0000 2018</td>
      <td>0.819</td>
      <td>0.181</td>
      <td>0.000</td>
      <td>@FoxNews</td>
      <td>.@GrecianFormula on NK summit: "My fear here i...</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Convert sentiments to DataFrame
sentiments5_pd = pd.DataFrame.from_dict(sentiments_5)
sentiments5_pd.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Compound</th>
      <th>Date</th>
      <th>Negative</th>
      <th>Neutral</th>
      <th>Positive</th>
      <th>Source</th>
      <th>Tweet</th>
      <th>Tweets Ago</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>-0.4767</td>
      <td>Sun Jun 10 03:29:03 +0000 2018</td>
      <td>0.853</td>
      <td>0.147</td>
      <td>0.000</td>
      <td>@nytimes</td>
      <td>RT @nytlizrobbins: Pablo Villavicencio, arrest...</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.0000</td>
      <td>Sun Jun 10 03:13:04 +0000 2018</td>
      <td>1.000</td>
      <td>0.000</td>
      <td>0.000</td>
      <td>@nytimes</td>
      <td>Anthony Bourdain understood that eating was si...</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.5719</td>
      <td>Sun Jun 10 02:59:05 +0000 2018</td>
      <td>0.861</td>
      <td>0.000</td>
      <td>0.139</td>
      <td>@nytimes</td>
      <td>RT @peterbakernyt: With a petulant tweetstorm ...</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.0000</td>
      <td>Sun Jun 10 02:50:25 +0000 2018</td>
      <td>1.000</td>
      <td>0.000</td>
      <td>0.000</td>
      <td>@nytimes</td>
      <td>On Horse Racing: At 52, Mike Smith Has the Rid...</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-0.2263</td>
      <td>Sun Jun 10 02:25:06 +0000 2018</td>
      <td>0.921</td>
      <td>0.079</td>
      <td>0.000</td>
      <td>@nytimes</td>
      <td>RT @amyvirshup: Kris Kobach email in group of ...</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Create plot
x_val1 = sentiments1_pd["Tweets Ago"]
y_val1 = sentiments1_pd["Compound"]
plt.scatter(x_val1,
         y_val1, facecolors="lightskyblue", marker="o", linewidth=0.5,
         alpha=0.8,edgecolors="black",label="BBC")

x_val2 = sentiments2_pd["Tweets Ago"]
y_val2 = sentiments2_pd["Compound"]
plt.scatter(x_val2,
         y_val2, facecolors="green", marker="o", linewidth=0.5,
         alpha=0.8,edgecolors="black",label="CBS")

x_val3 = sentiments3_pd["Tweets Ago"]
y_val3 = sentiments3_pd["Compound"]
plt.scatter(x_val3,
         y_val3, facecolors="red", marker="o", linewidth=0.5,
         alpha=0.8,edgecolors="black",label="CNN")

x_val4 = sentiments4_pd["Tweets Ago"]
y_val4 = sentiments4_pd["Compound"]
plt.scatter(x_val4,
         y_val4, facecolors="blue", marker="o", linewidth=0.5,
         alpha=0.8,edgecolors="black",label="Fox")

x_val5 = sentiments5_pd["Tweets Ago"]
y_val5 = sentiments5_pd["Compound"]
plt.scatter(x_val5,
         y_val5, facecolors="yellow", marker="o", linewidth=0.5,
         alpha=0.8,edgecolors="black",label="New York Times")

# Incorporate the other graph properties
now = datetime.now()
now = now.strftime("%Y-%m-%d %H:%M")
plt.title(f"Sentiment Analysis of Tweets ({now})")
plt.xlim([x_vals.max(),x_vals.min()]) #Bonus
plt.ylabel("Tweet Polarity")
plt.xlabel("Tweets Ago")
plt.legend(loc=9, bbox_to_anchor=(1.2, 1), title="Media Sources", markerscale=0.5)
plt.savefig("Sentiment_Analysis_Tweets.png")
plt.show()
```


![png](output_13_0.png)



```python
# Create plot
colors = ["lightskyblue","green","red","blue","yellow"]

y = [bbc_compound,cbs_compound,cnn_compound,fox_compound,nyt_compound]
x = np.arange(len(y))
plt.bar(x,
         y, align="center",color=colors, edgecolor = "black")

# Tell matplotlib where we would like to place each of our x axis headers
now = datetime.now()
now = now.strftime("%Y-%m-%d %H:%M")
tick_locations = [value for value in x]
plt.xticks(tick_locations, ["BBC", "CBS", "CNN", "Fox", "NYT"])
plt.title(f"Overall Media Sentiment based on ({now})")
plt.xlabel("Media Sources")
plt.ylabel("Tweet Polarity")

plt.savefig("Overall_Media_Sentiment.png")
plt.show()
```


![png](output_14_0.png)



```python
sentiments1_pd.to_csv("bbc_sentiment.csv",sep=",")
sentiments2_pd.to_csv("cbs_sentiment.csv",sep=",")
sentiments3_pd.to_csv("cnn_sentiment.csv",sep=",")
sentiments4_pd.to_csv("fox_sentiment.csv",sep=",")
sentiments5_pd.to_csv("nyt_sentiment.csv",sep=",")
```

1. Overall, BBC is much more negative when compared to the other news sources.
2. The overall sentiments of Fox and NYT are similar and positive but not very positive.
3. The sentiment analysis of tweets across news sources shows that news sources tend to vary. 
