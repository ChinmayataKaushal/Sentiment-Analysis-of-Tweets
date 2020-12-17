TITLE:  Sentiment Analysis of Twitter Data

OVERVIEW:

The project focuses on classifying the tweets into 3 categories - ‘negative’, ‘neutral’ and ‘positive’ i.e., The objective is to do the sentiment analysis of the given data by pre-processing( like removal of mentions, punctuation and stop words) to gather the useful data and use vectorization, tokenization, stemming and finally comparing the regression model and naive bayes model for optimal results.

SUMMARY:

Step 1: Converting to lowercase
Lowering the case of text is essential for the following reasons:
The words, ‘Tweet’, ‘TWEET’, and ‘tweet’ all add the same value to a sentence.
Lowering the case of all the words helps to reduce the dimensions by decreasing the size of the vocabulary.

Step 2: Removal of mentions
Mentions are very common in tweets. However, as they don’t add value for interpreting the sentiment of a tweet, we can remove them. Mentions always come in the form of ‘@mention’, so we can remove strings that start with ‘@’.

Step 3: Removal of HTML links/tags
Now we can remove URLs from the data. It’s not uncommon for tweets to contain URLs, but we won’t need to analyze them for our task.

Step 4: Removal of special characters and punctuations
This text processing technique will help to treat words like ‘hurray’ and ‘hurray!’ in the same way. At this stage, we remove all punctuation marks.


Step 5: Removal of Stop words
Stopwords are commonly occurring words in a language, such as ‘the’, ‘a’, ‘an’, ‘is’ etc. We can remove them here because they won’t provide any valuable information for our Twitter data analysis.

Step 6: Tokenization
Tokenization is the process of splitting text into smaller chunks, called tokens. Each token is an input to the machine learning algorithm as a feature. NLTK (Natural Language Toolkit) provides a utility function for tokenizing data.

Step 7: Stemming
Stemming is the process of removing and replacing suffixes from a token to obtain the root or base form of the word. This is called a ‘stem’. For example, the stem for the words, ‘satisfied’, ‘satisfaction’, and ‘satisfying’ is ‘satisfy’ and all of these imply the same feeling. Stemming is faster than lemmatization. Porter stemmer is a widely used stemming technique. nltk.stem provides the utility function to stem ‘PorterStemmer’

Step 8: Vectorization
Vectorizing is the process to convert tokens to numbers. It is an important step because the machine learning algorithm works with numbers and not text. The well-known techniques for vectorization of words in Natural Language Processing are: CountVectorization and Tf-IDF transformation. 

CountVectorization generates a sparse matrix representing all the words in the document.
Tf(d,t) (Term frequency) is defined as the number of occurrences of the term t in document d. Idf(t) (Inverse document of frequency) is defined as log(D/t), where D: Total number of documents and t: Number of documents with the term. What Tf-Idf transformer does is returns the product of Tf and Idf which is the Tf-Idf weight of the term.


RESULTS:

The pre-processed data was trained and tested on two models - 
Naive Bayes Models
Logistic Regression Models

For Count Vectorization, the two models gave the following results:
Naive Bayes ~ 77.219%
Logistic Regression ~ 78.859%
For Tf-idf, the results were as follows:
Naive Bayes ~ 68.852%
Logistic Regression ~ 78.244%

From these results we can conclude that training a logistic regression model on data pre-processed by count vectorization gave the best results.
