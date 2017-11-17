# SENTIMENT AND CLUSTER ANALYSIS THROUGH TWITTER API	

```
Developed an application in python where given the hashtags that are trending in twitter, it identifies the users who has used those hashtags and builds a graph between them. Using Girvan Newman cluster analysis algorithm, clusters among them are identified. Tweets that are collected are classified using Machine learning models like Support Vector Machine, naïve based and logistic regression for predicting the sentiment of the tweets and accuracy comparision is made.
```

### PYTHON FILES AND ITS ACTIONS

```

 `collect.py`: It is used to collect data whihc is used for analysis. Running this script will create a file or files containing the data that is need for the subsequent phases of analysis.

 `cluster.py`:  It is used to read the data collected in the previous file and using  community detection algorithm to cluster users into communities. 

 `classify.py`:  It is used to classify data along any dimension of your choosing (e.g., sentiment, gender, spam, etc.). You may write any files you need to save the results.

 `summarize.py`:  It is used to read the output of the previous methods to write a textfile called `summary.txt` containing the following entries:

```


### 1.DATA COLLECTION

It is based on the data collected from the Twitter based on the NBA teams and its hash tags.


```
--> '#DubNation'
--> '#WeTheNorth'
--> '#GrindCity'
--> '#DetroitBasketball'
--> '#thunderup'
--> '#LakeShow'
--> '#DefendTheLand'
```

# 1.1 Collecting unique data 

```
•	My source of data will be from twitter. 
•	We can collect data using thier API which provides data with many restriction, usually we will be able to get only data 		which are pusblished within 15 days. 
•	For making my dataset unique I need to collect the data in regular interval during game season. 
•	Each tweet has a id, each time I run my collect.py I store the recent Tweet ID and later when I re-run my code i will be 		able to get the unqiue tweets. 
•	I am collecting tweets for each hashtag and storing the tweets in of each hashtag in a pickle file with the name as hastag.
	example: ubNation.pkl
			 WeTheNorth'.pkl

```

# 1.2 Data Report

```
 Number of Unique Tweets collected : 54082
 Number of unique users collected : 5985
```

# 2. cluster.py

```
•	In this process I pass my previously collected data from collect to do the cluster process. To make the clustering more 		sensible I choose only users who have focused and tweeted about atleast more than one team to identify clusters among them 		and made a graph for them.
•	I removed all user who follows or tweeted only for a single team.
•	Later the graph is sent to grivan newman to identify cluster.
•	All the teets and cluster information is stored in a file Cluster.pkl
```

# 2.1 OUTPUT FOR CLUSTER
```
Mutual number of followers for the team #thunderup #WeTheNorth ----> 6
Mutual number of followers for the team #thunderup #DefendTheLand ----> 9
Mutual number of followers for the team #thunderup #DetroitBasketball ----> 12
Mutual number of followers for the team #thunderup #GrindCity ----> 9
Mutual number of followers for the team #thunderup #LakeShow ----> 5
Mutual number of followers for the team #thunderup #DubNation ----> 7
Mutual number of followers for the team #WeTheNorth #DefendTheLand ----> 6
Mutual number of followers for the team #WeTheNorth #DetroitBasketball ----> 11
Mutual number of followers for the team #WeTheNorth #GrindCity ----> 16
Mutual number of followers for the team #WeTheNorth #LakeShow ----> 3
Mutual number of followers for the team #WeTheNorth #DubNation ----> 14
Mutual number of followers for the team #DefendTheLand #DetroitBasketball ----> 24
Mutual number of followers for the team #DefendTheLand #GrindCity ----> 8
Mutual number of followers for the team #DefendTheLand #LakeShow ----> 3
Mutual number of followers for the team #DefendTheLand #DubNation ----> 7
Mutual number of followers for the team #DetroitBasketball #GrindCity ----> 15
Mutual number of followers for the team #DetroitBasketball #LakeShow ----> 11
Mutual number of followers for the team #DetroitBasketball #DubNation ----> 15
Mutual number of followers for the team #GrindCity #LakeShow ----> 4
Mutual number of followers for the team #GrindCity #DubNation ----> 7
Mutual number of followers for the team #LakeShow #DubNation ----> 7

graph has 109 nodes and 240 edges

cluster 1  Number of nodes/followers 18
cluster 2  Number of nodes/followers 20
cluster 3  Number of nodes/followers 20
cluster 4  Number of nodes/followers 19

Cluster Information stored in file Cluster.pkl 
```

 Computed average testing accuracy for each model over k-fold of Cross validation and accuracy comparison analysis is made and documented.


 algorithms in scikit-learn, networkx, scipy, numpy, nltk to perform your analysis. You do not need to implement the methods from scratch.
 It is expected that when I run your `collect.py` script, I may get different data than you collected when you tested your code. While the final results of the analysis may differ, your scripts should still work on new datasets.
