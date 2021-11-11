# Natural Language Processing (NLP)

## Table of Contents

- [Natural Language Processing (NLP)](#natural-language-processing-nlp)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
    - [NLP Applications](#nlp-applications)
    - [Terminology](#terminology)
  - [Basic NLP Operations](#basic-nlp-operations)
    - [Tokenization (Word, Sentence)](#tokenization-word-sentence)
    - [Stopwords Removal](#stopwords-removal)
    - [Punctuation Removal](#punctuation-removal)
    - [Part of Speech Tagging](#part-of-speech-tagging)
    - [Chunking](#chunking)
    - [Chinking](#chinking)
    - [Stemming](#stemming)
    - [Lemmatization](#lemmatization)
  - [Text Vectorization](#text-vectorization)
    - [Bag of Words](#bag-of-words)
    - [Term Frequency - Inverse Document Frequency (TF-IDF)](#term-frequency---inverse-document-frequency-tf-idf)
    - [Word Embeddings](#word-embeddings)
      - [Word2Vec](#word2vec)
  - [Algorithms Used in NLP Tasks](#algorithms-used-in-nlp-tasks)
  - [NLP Libraries](#nlp-libraries)
  - [Sample Repositories for Hands on Testing](#sample-repositories-for-hands-on-testing)
  - [References](#references)

## Introduction

Natural language processing is the field of studying langauges and computer science to develop intelligent applications. NLP helps machines to understand human languages the way humans naturally do. The field involves use of computer science techniques to both speaking and typing.

We can consider 3 aspects of any given text:

- **Semantic information:** Refers to the specific meaning of a word. The word bat in sentence "The bat flies in the sky" can refer to a winged mammal or a wooden stick.
- **Syntax Information**: Refers to sentence or phrase structure. A sentence can have a different meaning with respect to how you read it.
- **Context information**: Understand the context of that a word, phrase appears in a text. The word "sick" can be negative in healthcare, and in the context of a gaming, can refer to positive.

"Tom hit the ball so far". The ball in this sentence can refer to any sport, even tough we may imagine a specific sport.

Below sentence, the three aspects of information would return seperate meanings of the sentence and would not be helpful individually.

> “Billy hit the ball over the house.” 

Semantic information: person – act of striking an object with another object – spherical play item – place people live
Syntax information: subject – action – direct object – indirect object
Context information: this sentence is about a child playing with a ball

To make it work, we need to combine all 3 aspects. NLP can utilize machine learning or rule based/ pattern matching solutions.

### NLP Applications

- Smart Assistants 
- Predictive Text
- Email filters
- Automatic Summarization
- Named Entity Recognition (extraction of names, adresses, time, organizations, location, etc.)
- Sentiment Analysis (whether the context of the text is positive or negative)
- Speech Recognition
- Topic Segmentation
- Question Answering
- Information Retrieval/ Latent Semantic Indexing (Search engines)

And many, many more applications.

### Terminology

A brief glossary of NLP that will help us to understand more while reading.

| Term              | Definition                                                                                                                                                                    |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Corpus (Corpora)  | Is a collection of text. Can refer to collection of books, conversations, news, reviews, etc.                                                                                 |
| Documents         | A body of a text. A collection of documents makes into a corpus. Each conversation, each news article, etc.                                                                   |
| Token             | The output of breaking a large text into smaller pieces. Pieces are tokens.                                                                                                   |
| Tokenization      | The process of breaking large text into smaller pieces.                                                                                                                       |
| Morpheme          | THe smallest meaningful unit in a language.                                                                                                                                   |
| Lexicon           | The component that contains any type of information (semantic or grammatical) about the token.                                                                                |
| Preprocessing     | The process of cleaning the text data.                                                                                                                                        |
| n-grams           | A sequence of n-tokens in a text. 1-gram is single tokens, 2-grams or bi-grams are 2 words together `[(the, book), (We, are), ...]`, 3-grams are 3 words together, and so on. |
| Vocabulary        | Entire set of terms used in a body of text.                                                                                                                                   |
| Out of Vocabulary | Model can encounter limited number of words during training. Words that are out of model's vocabulary typically gets assigned to a common placeholder.                        |

Find out more on [The Natural Language Processing Dictionary](http://www.cse.unsw.edu.au/~billw/nlpdict.html).

## Basic NLP Operations

Analyzing textual data involves data cleanup and feature extraction. Some most common operations are listed below.

- Tokenization (Word, Sentence)
- Stopwords Removal
- Punctuation Removal
- Part of speech tagging
- Stemming and Lemmatization

Find out more about Analyzing Text with the Natural Language Toolkit in [NLTK Book](https://www.nltk.org/book/).

### Tokenization (Word, Sentence)

The action of splitting any text by word or sentence is known as tokenization. Generally this is the first step in a NLP pipeline.

**Tokenizing by Word:** Words are known as atoms of the human languages. Tokenizing by word allows to identify words that are particularly come up more often.

**Tokenizing by Sentence:** Allows to see how words are connected and see more context around the words.

There are other tokenization methods, such as [white-space tokenization](https://nlp.stanford.edu/nlp/javadoc/javanlp/edu/stanford/nlp/process/WhitespaceTokenizer.html), which is also known as unigram tokenization. This process splits the text into by white space into tokens. [Regular expression tokenization](https://goodboychan.github.io/python/datacamp/natural_language_processing/2020/07/15/01-Regular-expressions-and-word-tokenization.html) is another type of tokenization utilizes regular expression patterns to get the tokens from a text.

### Stopwords Removal

Stop words refers to the very common words like `in`, `is`, `are`, `have` that we use as part of languages but they don't contribute any value towards the goals of NLP.

Stop words can be considered as the noise in the textual data. Along with stopwords, there are other noisy tokens that can be removed along with stopwords, such as URLs, social media entities (hashtags, mentions, etc), punctuations, etc.

### Punctuation Removal

Like stop words, this task is to remove punctuations in a text. Punctuations like commas, apostrophes, quotes, question marks, and more.

### Part of Speech Tagging

Words have a role in a sentence. Part of speech refers to assigning these roles to the words. Tagging parts of speech (POS tagging), is the task of labeling the type of the word in the text. For example, using POS tagging, we can find the strengths and weaknesses of a product by calculating most and least used descriptors.

There are eight parts of speech for english.

| Part of speech | Role                                                                       | Examples                   |
| -------------- | -------------------------------------------------------------------------- | -------------------------- |
| Noun           | A person, place, or thing                                                  | mountain, bagel, Poland    |
| Pronoun        | Replaces a noun                                                            | you, she, we               |
| Adjective      | Information about what a noun is like                                      | efficient, windy, colorful |
| Verb           | Is an action or a state of being                                           | learn, is, go              |
| Adverb         | Gives information about a verb, an adjective, or another adverb            | efficiently, always, very  |
| Preposition    | Gives information about how a noun or pronoun is connected to another word | from, about, at            |
| Conjunction    | Connects two other words or phrases                                        | so, because, and           |
| Interjection   | Is an exclamation                                                          | yay, ow, wow               |

POS tagging can be very useful for both intermediate or final product NLP applications. Below are some examples that POS tagging can be helpful.

- **Word sense disambiguation**: Words can have multiple meanings and POS tagging can identify which meaning is used. The word "book" can refer to a noun or a verb depends on the context. The sentence `I booked a flight` and `I read this book for my studies` examplifies this case.
- **Improve word features**: "Book the flight, I am about the finish my book" sentence, if tokenized, will have 2 counts of `book`. However, if POS tagging is used, `book_NN` and `book_VB` can be made which may help capturing the context better.
- **Normalization and Lemmatization**: Can be used for effective lemmatization while converting to the lemma of the word.
- **Efficient noise removal**: POS tagging can help removal of stopwords, etc.

### Chunking

Chunking is the operation to identify phrases in a language. A phrase is a word or group of words that works as a single unit to perform a grammatical function. Noun phrases are built around a noun.

Here are some examples:

- A planet
- A tilting planet
- A swiftly tilting planet

### Chinking

Chinking is like chunking, but it removes chunks from chuncks. While chunking creates phrases, chinking breaks up or removes unwanted chunks. For example, you may want to exclude adjectives from your chunks.

### Stemming

Stemming is a text processing task to reduce the word into it's root, the core of the word. For example, words `helping, helper` has the same root of `help`. It allows to get the basic meaning of the word rather than how the word is used.

### Lemmatization

Lemmatization does the same operation as stemming does, but instead of just chopping of to the root, lemmatazing will give the core meaning of the word.

A lemma is a word that represents a whole group of words, and that group of words is called a lexeme. The word “blend” is the lemma, and “blending” is part of the lexeme. So when you lemmatize a word, you are reducing it to its lemma.

## Text Vectorization

The process of converting words into numbers are called Vectorization.

- Bag of Words
- Word Embeddings

### Bag of Words

Simplest form of converting words into numbers. If you have a vocabulary of 10000 words, each word will be 1x10000 represented arrays. 

Consider below example with a few documents. All the words are mapped in columns and based on their occurance in a document, vectorization is done by assigning 1 and 0s, counts, frequencies, etc.

| Document       | Best | Food | Wisdom | Age | Empires | Young |
| -------------- | ---- | ---- | ------ | --- | ------- | ----- |
| Best food      | 1    | 1    | 0      | 0   | 0       | 0     |
| Best wisdom    | 1    | 0    | 1      | 0   | 0       | 0     |
| Age of Empires | 0    | 0    | 0      | 1   | 1       | 0     |
| Young age      | 0    | 0    | 0      | 1   | 0       | 1     |

Once the vocabulary is set and documents converted to matrix, the scoring of the words can be done in many ways. The simplest ones are:

- One Hot Encoding (whether the word seen or not seen)
- Counts (as seen above)
- Frequencies (calculating the frequency of a word that appears in a document out of all documents)

The vocabulary can have more than just words. Features can be created by unigrams, bigrams, etc.

### Term Frequency - Inverse Document Frequency (TF-IDF)

TF-IDF considers the relative importance of the word to a document. Vector is constructed the same way as Bag of Words, but instead of counts, frequencies are used as numbers. The words appear in more documents are penalized, and words that are distinct gets a higher score.

**Term Frequency**: is a scoring of the frequency of the word in the current document.
**Inverse Document Frequency**: is a scoring of how rare the word is across documents.

The calculation of TF-IDF with an example. We have a corpus of 10 million documents. There is a document:

- Where the word "chocolatte" appears 3 times. The term frequency (i.e., tf) for cat is then (3 / 100) = 0.03.
- Ouf of a 10 million, "chocolatte" appears in 1000 of the documents. The inverse document frequency (i.e., idf) is calculated as log(10,000,000 / 1,000) = 4.
- Tf-idf weight is (TF X IDF). That is 0.03 * 4 = 0.12.

Therefore, each TD-IDF of the token can be calculated and the vectorization matrix can be calculated for each document in the corpus.

| Document            | best | chocolatte | ..  | food |
| ------------------- | ---- | ---------- | --- | ---- |
| Document 1          | ..   | ..         | ..  | ..   |
| best chocolatte ... | ..   | 0.12       | ..  |

### Word Embeddings

Word embedding is a langauge modeling technique that is used for mapping words to vectors of real numbers. Words or phrases are represented in vector space with multiple dimensions. Word embeddings can be generated through neural networks, co-occurence matrix, probabilistic models, etc. These vectors are used to find word predictions, similarities/ semantics, etc. Some common use cases are:

- Finding similar words (use Euclidean distance, cosine similarity, etc.)
- Text classifications
- Document clustering
- Feature extraction for text classifications

Some well-known pre-trained word embeddings libraries are:

- Word2Vec — From Google
- Fasttext — From Facebook
- GloVe — From Standford

The basic idea of word embedding is words that occur in similar context tend to be closer to each other in vector space.

#### Word2Vec

![](cbow-skipgram.png)

These models are shallow two layer neural networks having one input layer, one hidden layer and one output layer. Word2Vec utilizes two architectures:

1. Continous Bag of Words(CBOW): the distributed representations of surrounding words combined to **predict the word in the middle**.
2. Skip Gram: the distributed representation of the input word used to **predict the context**.

## Algorithms Used in NLP Tasks

The most popular supervised NLP machine learning algorithms are:

- Support Vector Machines
- Bayesian Networks
- Maximum Entropy
- Conditional Random Field
- Neural Networks / Deep Learning

Some common unsupervised algorithms are:

- Latent Semantic Indexing (LSI)
- Matrix Factorization

## NLP Libraries

There are many libaries in python and other languages for NLP. Some most widely used ones are:

- [nltk](https://www.nltk.org/)
- [spacy](https://spacy.io/)
- [gensim](https://radimrehurek.com/gensim/)

## Sample Repositories for Hands on Testing

- https://github.com/DistrictDataLabs/intro-to-nltk
- https://github.com/hb20007/hands-on-nltk-tutorial
- https://github.com/dipanjanS/text-analytics-with-python
- https://course.spacy.io/en
- https://github.com/Cristianasp/spacy

## References

https://www.lexalytics.com/lexablog/machine-learning-natural-language-processing
https://www.geeksforgeeks.org/python-word-embedding-using-word2vec/
https://realpython.com/nltk-nlp-python/
https://medium.com/analytics-vidhya/nlp-glossary-for-beginners-c3093529ee4
https://www.oreilly.com/library/view/applied-text-analysis/9781491963036/ch04.html