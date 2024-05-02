# Sentiment Analysis on Twitter Data using Hadoop Apache Hive and MapReduce

## Overview
This project aims to perform sentiment analysis on Twitter data using Apache Hive and MapReduce. Sentiment analysis involves determining the sentiment or opinion expressed in a piece of text, in this case, tweets from Twitter. By leveraging Apache Hive and MapReduce, large volumes of Twitter data can be efficiently processed and analyzed to extract insights about the sentiment of the tweets.

## Requirements
1. Apache Hive
2. Apache Hadoop
3. Apache Flume
4. Twitter Developer Account

## Methodology

### Collection of Data using Twitter APIs
Twitter data is collected by creating a Twitter application, installing and starting HDFS, and configuring Flume to fetch and store the data.

### Performing Sentiment Analysis using Apache Hive
Apache Hive is utilized to process the data in batch mode. The process involves extracting tweet IDs and text, splitting text into words, joining with a sentiment dictionary, and calculating the average sentiment rating for each tweet.

### Performing Sentiment Analysis using MapReduce
MapReduce is employed for distributed sentiment analysis. The process involves implementing distributed caching for the sentiment dictionary, writing mapper and reducer classes, and executing the MapReduce program.

## Procedure
1. Extract tweet_id and tweet_text from nested JSON format tweets.
2. Split text into words using the `split()` UDF available in Hive.
3. Store tweet_id and array of words in a new Hive table.
4. Split each word inside the array as a new row using a UDTF like `explode`.
5. Use the AFINN dictionary to assign sentiment ratings to words.
6. Join tweet_word table and dictionary table to associate word ratings with words.
7. Group by tweet_id to bring all words of one tweet together.
8. Calculate the average rating of words for each tweet.
9. Arrange tweets in descending order based on their rating.

## How To Run
1. Build an executable JAR file containing the Java files.
2. Execute the following command:
   
   ```bash
   hadoop jar twitter.jar /Hadoop/twitter_data/ /Hadoop/output/
