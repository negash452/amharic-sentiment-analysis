# Sentiment Analysis for Amharic Language

# Project Description

Amharic is one of the 86 languages spoken in Ethiopia. It is the "working language" of the federal government. 

The goal of this project is to have a more accurate sentiment analysis for Amharic language. The data that I will be using is an annotated data (tweet_ID with label of Positive, Negative or Neutral).

The potential value is that there isn't a robust sentiment classifier for low-resource languages such as Amharic, so by working on a model hopefully I will improve the accuracy of the model.

## Dataset

The dataset I will be using is composed of 9.4k Amharic tweets that are pre-classified as Positive, Negative or neutral. 

[Link to data & description](https://github.com/uhh-lt/ASAB/tree/main/data)

## MVP

A more accurate classification/NLP model that predict new Amharic tweets as Positive, Negative or Neutral.

Input: A tweet written in Amharic

Output: Positive, Negative or Neutral

## Goals

The Amharic language is one of the low-resource languages and there have been some researches done in sentiment analysis. The goal of this project is to have a more accurate sentiment analysis for Amharic sentences by improving upon techniques used by previous researchers and also using pre-trained models that have a similar language structure with Amharic but with a high resource by utilizing transfer learning. 

## Stretch Goals

- Add a feature for sarcasm detection

### Justification that the scope of your project is appropriate for 6 weeks with respect to learning curve, compute and storage resources

In order to successfully implement this project, I will do more research on NLP models, measuring and improving accuracy of NLP models. I will be using Google Colab notebook for running my model with GPU runtime.




[https://towardsdatascience.com/sentiment-analysis-for-low-resourced-languages-on-social-media-128bf01f2547](https://towardsdatascience.com/sentiment-analysis-for-low-resourced-languages-on-social-media-128bf01f2547)

This article is focused on how sentiment analysis was done on the Arabizi. "Arabizi is a very informal transcription of the spoken Dialectal Arabic in Latin script". The structure of the Arabic language is similar to Amharic because they're both agglutinative so it was an interesting read. One word could have many inflection points meaning it can be an origin to hundreds of other words in Arabic. And because of that, it is quite difficult to classify a sentiment as positive or negative by just seeing the word. Similar to Amharic, there is no standard way to spell some words because there are some letters in the alphabet that are phonetically similar but are different letters and they can be used interchangeably. There is also the problem of having many dialects for one language. All this and more reasons increase the lexical sparsity of the language. In addition, Arabizi is popular for its codeswitching. Codeswitching is when you are switching between two languages in your sentences. This is pretty common in social media posts according to the writer. It's also common in the Amharic language. 

# Summary of research and articles

The rise of social media has helped in collecting a lot of data for making analysis, and prediction models. Sentiment analysis is one of the popular benefits that came about due to this mass data. Languages such as English were easier to do a model on because the data was already labeled and there was many available corpus for English. 
However, there are many languages out there that are difficult to do sentiment analysis on. We call them low-resource languages. The structure of these languages makes it really hard to build a model because of lack of availability of labeled data, and because of their many dialects and how their words are structures. 

Amharic is one of the low-resource languages. Because of the scarcity of labeled data, it's been quite difficult to make an NLP model for sentiment analysis. However, recent researchers and Data Scientists are using platforms such as Telegram bots to label already existing Amharic tweets by asking users whether they are Positive, Negative or Neutral. Using this data, they were able to build models to classify Amharic tweets. But even then, it is quite difficult sometimes to classify a tweet since it's hard to tell sarcasm in tweets and their data collection didn't account for that.

# Explanation and results

The 4 models I used for my sentiment analysis was Naive Bayes with Count Vectorizer, Naive Bayes model with TFIDF vectorizer, Text blob sentiment, and SVM. 
Both the Naive Bayes had an accuracy of ~21%, but when the Mixed sentiments were removed from the datasets, the accuracy increased to ~32%. 
The text blob sentiment model has an accuracy of ~45.9%. A lot higher than the Naive Bayes model. 
The last working model I currently have is the SVM model. It has an accuracy of 50.7% with mixed sentiments removed. The model further improves to 70% when the classification is binary (positive/ negative). This shows that the model performs well when the dataset is composed of only 2 classifications. 

# Describe the implementation process, including assumptions, pitfalls, problems solved, what worked, what didn’t work.

After getting a dataset that contained tweet_id and sentiments, I wrote a script file to extract the tweets for each tweet_id using the twitter API. 
Once I got the dataset, I started cleaning the data and made it ready to implement different models to it. The extracting and cleaning part was difficult because there were a lot of edge cases that I had to make sure I didn't miss. The data extraction by itself took few days since twitter didn't allow morethan 150 requests per 15 minutes and there was around 9,000 tweet_ids to extract tweet.

I was able to contact some of the researchers that were working on amharic sentiment analysis and was able to join in their collaboration. I will be able to use their embedding models as well, and their pre-trained models. Once I have access to those, I can continue in making deep-learning models and make a more accurate sentiment model. 

What I learned is that the most difficult part of NLP is the data extraction and data cleaning than creating the actual models.

# Implementation Plan

- [ ]  Exploration of the tweet datasets of ASAB
- [ ]  Start from analyzing the already built models from other researches ([models](https://github.com/uhh-lt/ASAB/tree/main/model))
- [ ]  Find a high-resource language that is similar to Amharic in its structure (Germany and Arabic is similar by their morpheme structure)
- [ ]  Start with a pre-trained model from the high-resource language and use transfer learning
- [ ]  Work on improving it's accuracy
- [ ]  Built different types of NLP models and compare their accuracies for the given data

# How to run the code

You can run EDA, models and preprocess part from the colab notebooks. Which are located in their designated folders. Description is also on the readmes of the folders.

# Resources

[https://linguaphiles.livejournal.com/716083.html](https://linguaphiles.livejournal.com/716083.html)

[ASAB github](https://github.com/uhh-lt/ASAB)

[https://www.findke.ovgu.de/findke/en/Research/Data+Sets/Contemporary+Amharic+Corpus+(CACO)-p-1142.html](https://www.findke.ovgu.de/findke/en/Research/Data+Sets/Contemporary+Amharic+Corpus+%28CACO%29-p-1142.html)

[https://github.com/hltdi/HornMorpho](https://github.com/hltdi/HornMorpho)
