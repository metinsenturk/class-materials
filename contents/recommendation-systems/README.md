# Recommendation Systems

## Table of Contents

- [Recommendation Systems](#recommendation-systems)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Data](#data)
  - [Different Types of Recommendation Systems](#different-types-of-recommendation-systems)
    - [Collaborative Filtering](#collaborative-filtering)
    - [Content Based Filtering](#content-based-filtering)
  - [How do the Recommendation Systems Function?](#how-do-the-recommendation-systems-function)
    - [Cosine Similarity](#cosine-similarity)
    - [Manhattan Distance](#manhattan-distance)
    - [Euclidean Distance](#euclidean-distance)
    - [Pearson Correlation Coefficient](#pearson-correlation-coefficient)
    - [Jaccard Similarity](#jaccard-similarity)
    - [Hamming Distance](#hamming-distance)
  - [References](#references)

## Introduction

Personalization is the de-facto standard of today's product and services. Anywhere you look, you may find lots of recommendation systems helping you to make a decision. Examples of use are like:

- Netflix movie recommendations 
- Amazon product recommendations
- Google similar search results
- Medium recomending similar articles or interests
- Social media newsfeeds like Facebook, Instagram
- App store recommendations (%40 of Google Play app installs come from recommendations)

and many, many more. Companies prefer to avoid overwhelming users by decisions while using their services, helps engagement to the products, increases loyalty to the company and hopefully boost the sales as well. In layman terms, recommender system is the sales agent guiding you through the product or services based on your relationship with the agent, your previous shoppings, demographics, preferences, etc.

## Data

A recommendation system can utilize any of the following data avaiable.

- Relationships
- User behaviour data
- User demographic data
- Product attribute data
- Explicit and implicit ratings
- Product similarity
- User similarity

## Different Types of Recommendation Systems

There are many types of recommendation systems utilizes machine learning algorithms, some of these are:

- Content Based Filtering
- Collaborative Filtering
- Candidate Generation Network
- Knowledge Based Recommendation Systems

### Collaborative Filtering

This type of recommendation system works with the following idea in mind: 

> Customers who bought this also bought ...

Similarity is measured by similarity to other users. For example, assume there is a person who has already bought a wallet and a computer mouse. If another person interested in buying a wallet, this type of recommendation system can recommend a computer mouse. It's been in use by many social network companies and e-commerce industry. 

Can further be classified into two sections:

- **User-based filtering:** Recommend products to a user that similar users have liked.
- **Item-based filtering:** Recommend products to a user that are similar to another item.

A good dataset to look for this is [movielens](https://grouplens.org/datasets/movielens/) by University of Minnesota.

### Content Based Filtering

Uses information about the product or service and user's interaction to recommend new product or services. Similarity of a product is measured with product attributes. 

Some aproaches for content based filtering:

- Using rated content for recommendation
- Recommendation through content descrition and attributes

Examples of this kind are:

- When you watch cat movies, you will see more cat movies in YouTube
- When you watch cat movie published by user A, more videos of user A will be shown to you
- User ratings
- Moview attributes
- Similar products in Amazon

<!-- Advantage of this method is that it works even when a product doesn't have any reviews. On the other hand, on large datasets it can be difficult asc every user has different opinion about products. -->

## How do the Recommendation Systems Function?

In all of the methods above, each product and attributes are mapped to an embedding space. The similarity of the product is defined by a similarity measure. This is a function that takes the embedding space and returns a value to measure the similarity. Most of the recommendation systems relay on below measurements:

- Cosine
- Dot Product
- Minkowski Distances(Manhattan, Euclidean)

### Cosine Similarity

Measures the angle between two vectors. It's a judgement of the orientation, rather than the magnitute. Therefore, a data point of [5, 7] and [50, 70] will have a similar cosine similarity since they have the same angle (With euclidean distance, they would be far from each other). 

Cosine of 0 means products are similar and 1 means they are dissimilar.

### Manhattan Distance

It is the minkowski distance where exponential part is equal to 1. It is also called rectilinear distance, L1-distance/L1-norm, Minkowski’s L1- distance, city block distance and taxi cab distance.

### Euclidean Distance

It is the minkowski distance where exponential part is equal to 2. It is also called as L2 norm or ruler distance. In general, default distance is considered Euclidean distance.

### Pearson Correlation Coefficient

It is the correlation between two variables and ranges between 1 and -1.

The value of 1 means it is a positive correlation, 0 is no correlation, and -1 is a negative correlation.

### Jaccard Similarity

Used for finding similarity between finite sets. It is defined as the cardinality of the intersection of sets divided by the cardinality of the union of the sample sets.

### Hamming Distance

Hamming distance is used for categorical variables where numbers are not used. 

- If the value of x and y is same, then it distance is 0
- If the value of x and y is different, then it distance is 1

For example, the Hamming distance between 1101111 and 1001001 is 3, while the Hamming distance between ‘batman’ and ‘antman’ is 2.

The lower value means the two categories are similar, higher means they are dissimilar.

## References

- [An In-Depth Guide to How Recommender Systems Work](https://builtin.com/data-science/recommender-systems)
- [Recommendation systems crash course by Google](https://developers.google.com/machine-learning/recommendation)
- https://github.com/amitkaps/recommendation
- [Best Practices on Recommendation Systems by Microsoft](https://github.com/microsoft/recommenders)