# twitter_analysis
Twitter analysis using Python

Extract prevalent topics from Twitter messages

Conception Phase
To extract the most frequently discussed topics on custom city or region in London on Twitter, 
need to prepare several steps:
1. Create an Essential developer account on Twitter in https://developer.twitter.com/en and retrieve
API key, API secret, Access token, and Access token secret. Apply for Elevated developer account 
to get higher level of access with an approved applicated.
2. Set up an open GitHub repository in https://github.com to store the code created later in 
development phase.
3. Create YAML file as virtual environment which contained several Python libraries as virtual 
dependencies, such as NumPy, Scikit-learn, Pandas, NLTK, Spacy, etc.
4. Perform data analysis:
 a. Retrieving several tweets in London area.
 b. Preprocessing data cleaning: tokenization, lowercase, lemmatization, stemming, stop words.
 c. Entity analysis steps regarding most active users, and frequently used hashtags.
 d. Vectorize document with CountVectorizer, topic extraction using LDA/ LatentDirichletAllocation
 as probabilistic model to extract the five most commonly discussed topics.
 e. Vectorize document with TfidfVectorizer, topic extraction using NMF/Non-Negative Matrix
 Factorization as matrix factorization and multivariate analysis technique.
