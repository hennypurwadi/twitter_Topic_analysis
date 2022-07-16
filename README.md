### To analyze data from Twitter, need to prepare several steps:

A. Collect Twitter's data:
   There are 2 ways to collect data from Twitter: 
    1.1. 
      Without Twitter Developer Account API: with snscrape
      Installation from command prompt: #pip3 install snscrape

    1.2.
      With Twitter Developer Account API: with tweepy
      Create an Essential developer account on Twitter in https://developer.twitter.com/en  
      Retrieve API key, API secret, Access token, and Access token secret. 
      Apply for Elevated developer account to get higher level of access with an approved applicated.

    2. Set up an open GitHub repository in https://github.com/hennypurwadi/twitter_analysis  
       to store the code created later in development phase. 

    3. Create YAML file as virtual environment which contained several Python libraries as virtual dependencies, 
       such as NumPy, Scikit-learn, Pandas, NLTK, Spacy, etc.
    
    4. Retrieving twitter's data for username, hashtags, and tweets in location within radius 30 kilometers around London.
       (geocode 51.55201,-0.05824) with tweepy. https://tinyurl.com/nh26dkkn    
    

B. Perform data analysis:

    1. Entity analysis to find 5 most active users.
       Doesn't need cleaning proses to make username become lowercase etc, since Capital letter is unique part of the name.          
    2. Entity analysis to find 5 most frequently used hashtags.
       Lite cleaning pre-processsing with regex to make lowercase, removing URLs, special characters, web scraping, HTML,
       
    3. Entity analysis to extract five most prevalent topics in the tweets.
    
       3.1.Tweets Preprocessing data cleaning: 
           3.1.1.
           Using regex to make lowercase, removing URLs, special characters, web scraping, HTML, lemmatization, stemming.
           Using nltk for stop words, tokenization. 
           3.1.2.
           Vectorize cleaned tweets with CountVectorizer.
           3.1.3.
           Vectorize cleaned tweets with Tf-IDF.
           Tf-IDF is better than Count Vectorizer,because it provides the importance of the words, 
           and not only focus on the frequency of words in the corpus, and ignore less important words for analysis.
        
       3.2.Topic extraction using LDA/LatentDirichletAllocation to extract the five most commonly discussed topics.
           LDA doesn't need Tf-IDF to infer topics, but using Tf-IDF can improve result.
           LDA outperforms NMF in terms of their topic coherence 
           https://link.springer.com/chapter/10.1007/978-3-030-66840-2_12
       
       3.3.Topic extraction using NMF/Non-Negative Matrix to extract the five most commonly discussed topics. 
