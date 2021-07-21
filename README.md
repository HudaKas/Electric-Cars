# Electric Vehicle Twitter Sentiment Analysis

<img src="https://media.giphy.com/media/6h8jgwC3dU6vS/giphy.gif" width="700">

## Business Problem
Apple and Google both hired a data scientist to build a machine learning model to analyze shared tweets about their products during the 2011 SXSW Tech Conference. The algorithm will predict whether the sentiment of the tweet is positive or negative. So The model will predict whether a customer is satisfied or not with both apple and google products from the tweet content, so both companies can improve the customer’s experience

### The Data

The dataset is from the data.world website. The information will give us an insight into the customers' satisfaction from the tweets about the apple or google products. The dataset consists of 9,093 rows and 3 columns with different features. These features will help to predict whether the tweet is positive or negative.

## Observasion

There is a significant target class imbalance because out of 9065 sentiments:
- 61% are Neutral sentiments
- 32.7% are Positive sentiments
- 6.3% are Negative sentiments

The data is imbalanced and skewed towards the neutral sentiment

![](images/Sentiment%20Distribution.png)

**Sentiments per Product**
 * All the products mostly have positive reviews associated with them.
 * Iphone has the highest proportions of negative sentiments of all products.
 * The neutral (no emotion,I can't tell) sentiment has a very small proportion in the entire data spread, which is contradictary to our original data. It means, that a lot of rows where product is null, the sentiment is neutral.
![](images/Products%20Count.png)

**Features(words) importance**

Features (words) are being used by the model to make the positive and negative classifications from a sentiment dataset

![](images/feature.png)


### Conclusions

After exploring multiple classifying models through cross validation technique and vectorizing withTfdif

 * Visualized the dataset and observed that there were more neutral sentiments as compared to positive and negative sentiments.
 * However,vafter dropping all the products which had null values, observed that the neutral sentiment has a very small proportion in the entire data spread, which is contradictory to our original data. It means, that in a lot of rows where the product is null, the sentiment is neutral.
 * All the models perform better with Tfdif vectorizer. Tfdif gives us most frequently present n-grams(words) within our dataset that helps our model to understand the data more efficiently and map correlations.
 * TThe best performing model of the whole lot was LinearSVC. It gave us an accuracy of 84.9% with F1 score of 91%
 * LinearSCV which works on the concept of hyperplanes helps us distinguish between positive and negative sentiments with a decent accuracy
 * Also, the most important features(words) in negative tweets were : hate, long, suck, heck, money,issue etc.
 * The most important features(words) in positive tweets were : party, ipad better, free, ipad launch, thanks, great etc.




### Limitaion
More data is needed to better categorize the sentiment, especially in the negative sentiment category.

### Future work
- Add Neutral sentiments to the target variables along with Positive and Negative. 
- Strategies need to be implemented to balance the data.
- Use of Embeddings.CBoW, Glove, or Bert embeddings can be used to cluster similar meaning words together. This will help to distinguish words between positive, negative and neutral sentiments thoroughly.
- Use pre-trained models such as Transformer-5(T5) and check how they perform over the dataset.