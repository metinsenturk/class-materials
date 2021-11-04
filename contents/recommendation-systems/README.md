# Recommendation Systems

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

<!-- ## How do the Recommendation Systems Function? -->

## References

- [An In-Depth Guide to How Recommender Systems Work](https://builtin.com/data-science/recommender-systems)
- [Recommendation systems crash course by Google](https://developers.google.com/machine-learning/recommendation)
- 