# Network-Anomaly-Detection-application

## PROBLEM STATEMENT

### Objective
Create a Spark Streaming based Network Anomaly Detection application using StreamAnalytix

### Dataset Description
A network dataset collected as a raw TCP dump for a local area network (LAN).

### Problem Statement
Determine possible abnormal network activities - characterized by and, sparse data point values that are distinctly different from the data patterns of discovered / known normal and abnormal network data characteristics.
In order to solve this problem, two different data sets are provided:

* Training dataset csv
* Prediction dataset csv 

### Participants need to:
Examine the dataset and identify the parameters on which the anomaly could be determined Use the training dataset to model an online real-time learning algorithm.

Apply the model on the prediction dataset to identify anomalies, if any Participants may choose to use one of the existing algorithms provided by StreamAnalytix or write their own.

The application flow must include the following:

* Cleansing/filtering of ‘bad data’ - ignore data for which ‘land field’ value is not 0 or 1
* Enrichment of data with latitude and longitude values using IP to Geo-mapping: a static dataset of IP to Geo-mapping is provided in an HBase table (ip2geo)
* Calculating the cumulative count of the number of anomalies detected
* Triggering a General Alert for every anomaly detected
* Triggering a Critical Alert if more than 20 anomalies are detected within 1 minute
* Persistence of the entire incoming record along with the enriched fields in Elasticsearch
* Persistence of every anomaly that is detected in RabbitMQ
* Visualization of the following (using the real-time dashboard feature of StreamAnalytix):
* Cumulative count of the number of anomalies as a counter
* Each anomaly plotted as a time series line chart

Input Data Dictionary is csv 


https://streamanalytix.com/contest/image/contest-problem.png
