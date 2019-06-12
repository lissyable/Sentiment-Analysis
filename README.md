# Sentiment-Analysis
Sentiment analysis about 5 major banks in Canada


In today's world, opinions and reviews accessible to us are one of the most critical factors in formulating our views and influencing the success of a brand, product or service. Social networks are a rich platform to learn about people’s opinions, sentiments, evaluations, attitudes, and emotions and sentiment regarding different topics as they can communicate and share their opinion actively on social medias including Facebook and Twitter. There are different opinion-oriented information gathering systems which aim to extract people’s opinion regarding different topics. The sentiment-aware systems these days have many applications from business to social sciences. Since social networks, especially Twitter, contains small texts and people may use different words and abbreviations which are difficult to extract their sentiment by current Natural Language processing systems easily, therefore some researchers have used deep learning and machine learning techniques to extract and mine the polarity of the text. Some of the top abbreviations are FB for Facebook, B4 for before, OMG for oh my God and so on. Therefore, sentimental analysis for short texts like Twitter’s posts is challenging.
With the advent and growth of social media in the world, stakeholders often take to expressing their opinions on popular social media, namely Twitter. Data analysis of twitter data is very helpful for any of organization to reduce the efforts of taking feedback from people to go and take survey from society. By using twitter, we can get data from twitter profile on that they can tweet in 140 words. 
Here I use Twitter data to do sentiment analysis of people’s opinion of five different banks in Canada. The top 5 Canadian banks had over C$5 trillion assets, by market capitalization, by revenue, deposits and loans as of January 31, 2018 are 
1.	Royal Bank of Canada (RBC)
2.	Toronto-Dominion Bank (TD)
3.	Bank of Nova Scotia (SCOTIA)
4.	Bank of Montreal (BMO)
5.	Canadian Imperial Bank of Commerce (CIBC)
For this project, first I need to extract customer feedback on 5 banks from Twitter and then rated in three categories i.e., negative and positive. Then analyze the sentiments of customers by applying the sentiment analysis model or text analytics. 



Research questions:

Are the customers happy from their products or services?  
What do people think about our product (service, company etc.)?  
How positive (or negative) are people about our product?  
What would people prefer our product to be like?

Dataset

The dataset I am using is the data extracted from Twitter using R. The dataset has 16 variables namely text, favorited, favorite Count, created, is retweet, retweeted, longitude, latitude, …For the sentiment analysis I am using only the column text.  
Get tweets from Twitter

To have access to the Twitter API, we'll need to login the Twitter Developer website and create an application. After registering, grab your application’s Consumer Key, Consumer Secret, Access token and Access token secret from Keys and Access Tokens tab.
We use the setup_twitter_oauth function to set up our authentication. Authorizing with keys into Twitter is done as follows:

library(twitteR)

setup_twitter_oauth(consumer.key, consumer.secret, access.token, token.secret)

The searchTwitter allows you to download tweets. For this, I use the following command,

tweets_RBC <- searchTwitter("RBC+rbc -filter:retweets", since = '2000-01-01', lang ='en', n = 5000)

I did the same for each of the banks like RBC, TD, CIBC, BMO and SCOTIA. After that we need to convert into data frame and finally save this into csv file.
