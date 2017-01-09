 Developed an application in python where given the hashtags that are trending in twitter, it identifies the users who has used those hashtags and builds a graph between them. Using Girvan Newman cluster analysis algorithm, clusters among them are identified.

 Tweets that are collected are classified using Machine learning models like Support Vector Machine, naïve based and logistic regression for predicting the sentiment of the tweets.

 Computed average testing accuracy for each model over k-fold of Cross validation and accuracy comparison analysis is made and documented.

python collect.py
python cluster.py
python classify.py
python summarize.py



- `collect.py`: This should collect data used in your analysis. This may mean submitting queries to Twitter or Facebook API, or scraping webpages. The data should be raw and come directly from the original source -- that is, you may not use data that others have already collected and processed for you (e.g., you may not use [SNAP](http://snap.stanford.edu/data/index.html) datasets). Running this script should create a file or files containing the data that you need for the subsequent phases of analysis.
- `cluster.py`: This should read the data collected in the previous steps and use any community detection algorithm to cluster users into communities. You may write any files you need to save the results.
- `classify.py`: This should classify your data along any dimension of your choosing (e.g., sentiment, gender, spam, etc.). You may write any files you need to save the results.
- `summarize.py`: This should read the output of the previous methods to write a textfile called `summary.txt` containing the following entries:

  - Number of users collected:
  - Number of messages collected:
  - Number of communities discovered:
  - Average number of users per community:
  - Number of instances per class found:
  - One example from each class:


-algorithms in scikit-learn, networkx, scipy, numpy, nltk to perform your analysis. You do not need to implement the methods from scratch.
- It is expected that when I run your `collect.py` script, I may get different data than you collected when you tested your code. While the final results of the analysis may differ, your scripts should still work on new datasets.
