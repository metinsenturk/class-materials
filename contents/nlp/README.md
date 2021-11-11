# Natural Language Processing (NLP)

## Table of Contents

- [Natural Language Processing (NLP)](#natural-language-processing-nlp)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
    - [NLP Applications](#nlp-applications)
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
    - [Word Embeddings](#word-embeddings)
      - [Word2Vec](#word2vec)
  - [Algorithms Used in NLP Tasks](#algorithms-used-in-nlp-tasks)
  - [NLP Libraries](#nlp-libraries)
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
- Named Entity Recognition
- Sentiment Analysis
- Speech Recognition
- Topic Segmentation

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

## References

https://course.spacy.io/en
https://www.lexalytics.com/lexablog/machine-learning-natural-language-processing
https://www.geeksforgeeks.org/python-word-embedding-using-word2vec/
https://realpython.com/nltk-nlp-python/