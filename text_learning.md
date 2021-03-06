# Text Learning
### Bag of words in sklearn
```
>>> from sklearn.feature_extraction.text import CountVectorizer
>>> vectorizer = CountVectorizer()
>>> string1 = "hi Katie the self driving car will be late Best Sebastian"
>>> string2 = "Hi Sebastian the machine learning class will be great great greate Best Katie"
>>> string3 = "Hi Katie the machine learning class will be most excellent"
>>> email_list = [string1, string2, string3]
>>> bag_of_words = vectorizer.transform(email_list)
### Shows (document#, word) how many times appeared
>>> print vectorizer.vocabulary_.get("great")
6
```

### Stopwords
low-information, highly frequent word.<br>
***Example***) the, in, for, you, will, have, be

### Stopwords in NLTK(National Language Tool Kit)
```
>>> import nltk
>>> from nltk.corpus import stopwords
>>> nltk.download()
showing info http://nltk.github.com/nltk_data/
True
>>> sw = stopwords.words("english")
>>> swp[0]
'i'
>>> swp[10]
'yours'
```

### Stemming to Consolidate vocabulary
unresponsive
response
responsivity
responsiveness
respond
-> stemmer is 'respon'

### Stemming with NLTK
```
>>> from nltk.stem.snowball import SnowballStemmer
>>> stemmer = SnowballStemmer("english")
>>> stemmer.stem("responsiveness")
u'respons'
>>> stemmer.stem("responsivity")
u'respons'
>>> stemmer.stem("unresponsive")
u'unrespons'
```

### Weighting by Term Frequency
***TfIdf Representation***
TF - term Frequency (like bag of words)
Idf - inverse document frequency (weighting by how often word occurs in corpus)
