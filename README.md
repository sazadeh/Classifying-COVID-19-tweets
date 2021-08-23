# Classifying-COVID-19-tweets
Classifying COVID-19 related Tweets based on Gender and Sentiment

**Objective** <br />
The objective of this research is to do sentiment analysis and gender prediction based on the tweet text and then try to classify the tweets based on their 
sentiments and gender with different machine learning models and compare the results. 

**Background**<br />
News and awareness about COVID-19 spread like the pandemic itself on social media.  During the resulting lockdown, people used social media to express their
feelings and find and share Covid-19 related information. Estimating the “Sentiment” associated with a message is one aspect of how Twitter data is analyzed.
Different tools have been used for sentiment analysis in the literature. It can be performed by a lexicon-based approach such as LIWC, machine learning approaches
such as SVM, NB, RF, or MLP, or a hybrid approach. For Gender prediction there are some researches base on the tweets or images or mixed of them with RNN. 
The information extracted from sentiment analysis and gender prediction can be used in different fields such as marketing, legal investigation, and personalization.

**Data set**<br />
We used this Covid-19 tweet data set :
https://www.kaggle.com/gpreda/covid19-tweets

We did some pre-processing steps on tweet text such as remove Emojies,Usernames ,URLs, Hashtags , Stemming and prepare it for further analysis.<br />

**Explatory Analysis**<br />
We found the most 10 frequent words in tweets, Top 10 Hshtags , Top 10 Locations with most tweets , Top 10 Sources for tweets , Prevalen words in tweets. 
You can find all these parts in Jupyter Notebook file. Some sample output is as bellow:<br />

*Most Frequent Words*

<img align=center width="1024" alt="Most Frequent Words" src="https://user-images.githubusercontent.com/81987771/130511540-699aeb76-b3d2-4236-a1e5-ead8753ea8f7.png">

*Word Cloud*

<img align=center width="475" alt="Word Cloud" src="https://user-images.githubusercontent.com/81987771/130511419-ddfa7571-4de3-4372-8f92-27e608a5b8ce.png">



**Methodology**<br />
We used **VaderSentiment Package** and **LIWC** for predicting the sentiment of each tweets.<br />
**Note:** You should have a license for using LIWC.<br /> 
Then we chose the result of *VaderSentiment* as our labels for the dataset and tried to classify the tweets based on **Naive Bayes , XGBoost , Random Forest and Support Vector Machine**.  We got the best result based on **XGBoost** and tried to classify the tweets based on that and here is the result:<br />

<img align=left width="400" alt="Comparing the result of ML models for Classification" src="https://user-images.githubusercontent.com/81987771/130513166-4b44e911-2888-46e7-b656-7d5ad1f95370.png"> <br /><img align=right width="350" alt="Classify Tweets based on the Sentiments by XGBoost" src="https://user-images.githubusercontent.com/81987771/130513007-6b985c2f-8e0c-4ada-916e-1a221b4f3209.png"> <br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
*Gender Prediction*<br />

We wanted to predict the gender-based on their tweet. We found a data set (https://www.kaggle.com/crowdflower/twitter-user-gender-classification) that has a gender for each tweet. We did the pre-processing steps on tweet text and considered the genders, female or male (we ignored unknown genders). Also kept the genders have the gender-confidence > 0.80. Then we used CountVectorize library to convert the tweet text into vectors. We changed female to 0 and male to 1 . The gender column is considered as our label. <br />

We used **Naive Bayes , XGBoost , Random Forest and Support Vector Machine** and this time we got the best result based on **Naive Bayes** while training the model and then we used it to predict the gender on the main data set. We could not get the accuracy more than *60% *on this dataset. We checked this process with pre-trained BERT models and the maximum accuracy which we could get there was *61%* .<br />

Here is the result:<br /> 

<img align=left width="400" alt="Naive Bayes - Gender Prediction" src="https://user-images.githubusercontent.com/81987771/130515255-f0ed789a-9696-465d-a73b-d55fd2c61654.png"> <img align=right width="350" alt="Naive Bayes- Gender Classification" src="https://user-images.githubusercontent.com/81987771/130515263-8c8b183b-459a-4bcb-80c7-72c71396755c.png">


