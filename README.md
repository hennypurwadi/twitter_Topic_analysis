To perform 3 separated tweets analysis from Twitter in particular area location (radius 30 km around London)

- Entity analysis to find 5 most active users. 
- Entity analysis to find 5 most frequently used hashtags. 
- Entity analysis to extract five most prevalent topics in the tweets.

---------------------

To install .yaml environment dependencies using conda powershell cmd: 

>(base) PS C:\Users\HENNY\Documents\PYTHON\DLBDSEDA02> conda env create -f DLBDSEDA02.yaml

To activate .yaml environment : 

>(base) PS C:\Users\HENNY\Documents\PYTHON\DLBDSEDA02> conda activate DLBDSEDA02

To add library and update .yaml environment : 

>(base) PS C:\Users\HENNY\Documents\PYTHON\DLBDSEDA02> conda env update -f DLBDSEDA02.yaml

To deactivate .yaml environment : 

>(base) PS C:\Users\HENNY\Documents\PYTHON\DLBDSEDA02> conda deactivate

To Run jupyter notebook from cmd:

>(nlp_tweet_env) PS C:\Users\HENNY\Documents\PYTHON\DLBDSEDA02>jupyter notebook

If it doesn't work:

>(nlp_tweet_env) PS C:\Users\HENNY\Documents\PYTHON\DLBDSEDA02>python -m notebook

To escape :
>Ctrl + C

Back to cmd:
>ctrl + Z
------------------
Additional:

!pip3 install snscrape

!pip install tweepy

!pip install wordcloud

------------------

To analyze data from Twitter, need to prepare several steps:

1. Collect Twitter's data:
Without Twitter Developer Account API: with snscrape.
Installation from command prompt: #pip3 install snscrape.

2. Set up an open GitHub repository in https://github.com/hennypurwadi/twitter_analysis 
 to store the code created later in development phase. 
 
3. Create YAML file as virtual environment.
 It contained Python libraries as virtual dependencies, such as NumPy, Scikit-learn, Pandas, NLTK.
 
4. Retrieving twitter's data for username, hashtags, Retrieving twitter's data for username, hashtags, 
tweets in location within 30 km radius from DowningStreet10 London.

2. Perform data analysis:

2.1. Entity analysis to find 5 most active users.
Doesn't need cleaning proses to make lowercase, since Capital letter is unique part of the name. 

2.2. Entity analysis to find 5 most frequently used hashtags.
Lite cleaning with regex to make lowercase special characters, etc. 

2.3. Entity analysis to extract five most prevalent topics in the tweets.

2.3.1. Tweets pre-processing data cleaning: 
Using regex to make lowercase, removing URLs, special characters, web scraping, 
lemmatization, stemming. Using nltk for stop words, tokenization. 

2
2.3.2. Vectorize cleaned tweets with CountVectorizer.
 Vectorize cleaned tweets with Tf-IDF.
Tf-IDF outperforms CountVectorizer.

TF-IDF is better than Count Vectorizers because it not only focuses on the frequency of words 
present in the corpus but also provides the importance of the words. We can then remove the words 
that are less important for analysis, hence making the model building less complex by reducing the 
input dimensions. (Sheel Saket, 2020).

2.3.3. Topics extraction using LDA/ Latent Dirichlet Allocation from CountVectorizer.
 Topics extraction using LDA/ Latent Dirichlet Allocation from Tf-IDF.
 Topics extraction using NMF/Non-Negative Matrix from CountVectorizer.
 Topics extraction using NMF/Non-Negative Matrix from Tf-IDF.
 
Compared the result.

LDA and NMF doesn't need Tf-IDF to infer topics. But using Tf-IDF can improve result.
LDA is good in identifying coherent topics.
NMF usually good for incoherent topics.
