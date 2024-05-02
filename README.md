## Sentiment-Analysis-on-Twitter-Data-using-Hadoop-Apache-Hive-and-Mapreduce
# Overview:
This project aims to perform sentiment analysis on Twitter data using Apache Hive and MapReduce. Sentiment analysis involves determining the sentiment or opinion expressed in a piece of text, in this case, tweets from Twitter. By leveraging Apache Hive and MapReduce, large volumes of Twitter data can be efficiently processed and analyzed to extract insights about the sentiment of the tweets.
# Requirements
1)Apache Hive
2)Apache Hadoop
3)Apache Flume
4)Twitter Developer Account
# Methodology
# Collection of Data using Twitter APIs: 
Twitter data is collected by creating a Twitter application, installing and starting HDFS, and configuring Flume to fetch and store the data.
# Performing Sentiment Analysis using Apache Hive: 
Apache Hive is utilized to process the data in batch mode. The process involves extracting tweet IDs and text, splitting text into words, joining with a sentiment dictionary, and calculating the average sentiment rating for each tweet.
# Performing Sentiment Analysis using MapReduce: 
MapReduce is employed for distributed sentiment analysis. The process involves implementing distributed caching for the sentiment dictionary, writing mapper and reducer classes, and executing the MapReduce program.


