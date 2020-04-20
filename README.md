# twitter-sentiment-analysis
Twitter Sentiment Analysis with Spark, SparkStreaming, Kafka, Elasticsearch &amp; Kibana

Objective:
The goal of this project is to perform sentiment analysis on Twitter data for extracting sentiment insights to analyze Emotion attached to the tweet.
Reading the Twitter stream from the Twitter-API with Kafka and stream them into a Spark-Cluster to process it.

Tools & Technologies:
•	Tweepy (And your own pair of API Keys from Twitter)
•	Kafka-Python
•	Pyspark (Python 3.7, Spark 2.4)
•	Elasticsearch5.4 
•	Kibana5.4 Dashboard 
•	NLTK with VADER 
•	Jupyter Notebook
•	Spark Streaming
•	Spark SQL
Tweepy: An easy-to-use Python library for accessing the Twitter API. Tweepy is a Python wrapper for the Twitter API. It accesses the Twitter REST (including Search) and Stream APIs.
Twitter API: It is the source of the system. We are collecting real time tweets using API service provided by Twitter.
PySpark: PySpark is a Spark API that allows you to interact with Spark through the Python shell.
Spark Steaming: Breakdown the Streaming data into smaller pieces which are then sent to the Spark Engine.
Kafka:  Kafka is real-time streaming data pipelines that reliably get data between systems or applications. Kafka® is used for building real-time data pipelines and streaming apps. Apache Kafka is a community distributed event streaming platform capable of handling trillions of events a day. Initially conceived as a messaging queue, Kafka is based on an abstraction of a distributed commit log.
NLTK with VEDAR: VADER (Valence Aware Dictionary for sEntiment Reasoning) is a model used for sentiment analysis that is sensitive to both polarity (positive/negative) and intensity (strength) of emotion.
Jupyter Notebook: Jupyter Notebook is an interactive computing environment and Python web server, providing a browser-based UI (user interface) for Jupyter users. Jupyter Notebooks are an ordered list of input/output cells, each providing a REPL (read-eval-print loopread-eval-print loop) for writing code and a window to show output in real time.
SparkSQL: Spark SQL is a component on top of Spark Core that introduced a data abstraction called DataFrames, which provides support for structured and semi-structured data. Spark SQL provides a domain-specific language (DSL) to manipulate DataFrames in Scala, Java, or Python.
Elasticsearch: Elasticsearch is an open source distributed, RESTful search and analytics engine capable of solving a growing number of use cases. Elasticsearch is a distributed, open source search and analytics engine for all types of data, including textual, numerical, geospatial, structured, and unstructured. Elasticsearch is built on Apache Lucene and was first released in 2010 by Elasticsearch N.V. (now known as Elastic). Known for its simple REST APIs, distributed nature, speed, and scalability, Elasticsearch is the central component of the Elastic Stack, a set of open source tools for data ingestion, enrichment, storage, analysis, and visualization. Commonly referred to as the ELK Stack (after Elasticsearch, Logstash, and Kibana), the Elastic Stack now includes a rich collection of lightweight shipping agents known as Beats for sending data to Elasticsearch.
Kibana: Kibana is an open source data visualization plugin for Elasticsearch. It provides visualization capabilities on top of the content indexed on an Elasticsearch cluster. Users can create bar, line and scatter plots, or pie charts and maps on top of large volumes of data.

Implementation >> How it works:

We have the twitter users tweeting those posts with certain hashtags at the start of our journey. Twitter provides an API for a few days to test them in the past, or to read the livestream. 

With a Kafka Writer written in Python we read the stream and send the related part of the tweet to a topic on the Kafka Server after some cleaning. 

The Spark-Consumer is waiting on the other side of the Kafka Message queue while the tweets are being sent to the subject. The Spark-Streaming library has some Kafka Functionality to collect the messages from the Kafka server and return them for processing in Spark RDDs. 

Within the Spark-Consumer we let the Sentiment-Magic do the NLTK Vader package and add the result (negative / positive / neutral) to the tweet results. 

We can submit the data to Elasticsearch at the end of a consuming loop to create some dashboards with Kibana to display the outcome of our sentiment analysis and prove that the tweets are being processed in real time. 

Refer for full document, twittersentiment_doc.docx

