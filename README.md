# Sentiment-Analysis-on-Twitter-Data-using-Hadoop-Apache-Hive-and-Mapreduce
## Overview:
This project aims to perform sentiment analysis on Twitter data using Apache Hive and MapReduce. Sentiment analysis involves determining the sentiment or opinion expressed in a piece of text, in this case, tweets from Twitter. By leveraging Apache Hive and MapReduce, large volumes of Twitter data can be efficiently processed and analyzed to extract insights about the sentiment of the tweets.
## Requirements
1)Apache Hive
2)Apache Hadoop
3)Apache Flume
4)Twitter Developer Account
## Methodology
## Collection of Data using Twitter APIs: 
Twitter data is collected by creating a Twitter application, installing and starting HDFS, and configuring Flume to fetch and store the data.
## Performing Sentiment Analysis using Apache Hive: 
Apache Hive is utilized to process the data in batch mode. The process involves extracting tweet IDs and text, splitting text into words, joining with a sentiment dictionary, and calculating the average sentiment rating for each tweet.
## Performing Sentiment Analysis using MapReduce: 
MapReduce is employed for distributed sentiment analysis. The process involves implementing distributed caching for the sentiment dictionary, writing mapper and reducer classes, and executing the MapReduce program.
## Procedure :
The tweet is in the nested JSON format. From this tweet, we will extract the id, which is the tweet_id and text, which is the tweet_text.
Next, we will split the text into words using the split() UDF available in Hive. If we use the split() function to split the text as words, it will return an array of values. So, we will create another Hive table and store the tweet_id and the array of words.
Next, let’s split each word inside the array as a new row. For this, we need to use a UDTF(User Defined Table Generating Function). We have built-in UDTF called explode which will extract each element from an array and create a new row for each element.
Let’s use a dictionary called AFINN to calculate the sentiments. AFINN is a dictionary that consists of 2500 words rated from +5 to -5 depending on their meaning.
Now, we will join the ​tweet_word table and ​dictionary table so that the rating of the word will be joined with the word.
Now we will perform the ‘groupby’ operation on the tweet_id so that all the words of one tweet will come to a single place. And then, we will be performing an Average operation on the rating of the words of each tweet so that the average rating of each tweet can be found.
we will calculat the average rating of each tweet by using each word of the tweet and arranging the tweets in the descending order as per their rating.
## Perform Sentiment Analysis using MapReduce
1)Implementing Distributed Caching
2)Writing a mapper class to calculate the sentiments
3)Writing a reducer class to display all the mapper output
4)Writing a Driver class for our MapReduce program


After this we need to make an executable jar file for the further process.
On top of this, we need to provide the input(tweets_folder) path and the output folder path as arguments.

## How To Run :

In order to run this program, we need to build a jar file of the above java files.
hadoop jar twitter.jar /Hadoop/twitter_data/ /Hadoop/output/

