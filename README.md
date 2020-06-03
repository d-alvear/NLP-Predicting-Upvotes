# NLP: Predicting Upvotes Based on Headline
## Introduction
Hacker News is a community where users can submit articles, and other users can upvote those articles. The articles with the most upvotes make it to the front page, where they're more visible to the community.
## Goal
In this project, I'll build a model that can predict the number of upvotes an article received, based on their headline. Because upvotes are an indicator of popularity, I'll discover which types of articles tend to be the most popular.
## Data

The data set consists of submissions users made to Hacker News from 2006 to 2015. Developer Arnaud Drizard used the Hacker News API to scrape the data, which can be found in one of his [GitHub repositories](https://github.com/arnauddri/hn). I've sampled 3000 rows from the data randomly, and removed all of the extraneous columns. I will solely be working with the following four columns:

* `submission_time` - When the article was submitted
* `upvotes` - The number of upvotes the article received
* `url` - The base URL of the article
* `headline` - The article's headline

## Modeling
The resulting regression model had an average error of 51.5 upvotes, which is a very large error considering the mean number of upvotes per article is 10. Implementing a random forest model reduced the error to 48.9 upvotes. I decided to remove the following stopwords and retrain the model to try to improve the accuracy of the random forest model.

`stops = ['as', 'you', 'what', 'de', 'at', 'back', 'an', 'from', 'via', 'into', 'or', 'it', 'using', 'but', 'part', '1', 'get', 'after', 'his', 'three', 'us', 'why', 'that', 'can', 'may', 'this', 'my', 'i', 'by', 'them', 'some','its', 'are', 'be', 'so', 'one', 'any', 'being', '4', '5', 'goes', 'me', 'we', '40', 'has', 'only', '|', 'if','have', 'will', 'x', '8', 'did', 'could', 'isnt', 'through', 'ever', 'should', '3', 'even', 'word', 'they', 'come','must', 'two', 'whats', 'who', 'lets', 'san', '20', 'other', 'there', 'tells', 'center', 'y', 'every', 'too','know', 'put', 'ways', 'were', '100', '6', 'things', 'say', 'when', 'youre', 'head', 'before', 'made', 'right','cant', 'makes', 'inside', 'thoughts', '18', 'let', 'take', '500', 'got', 'another', 'making', '14']`

Removing the stopwords only slightly improved the model's accuracy from an error of 51.1 upvotes to 46.3. This error is still large considering the mean number of upvotes is 10.

## Conclusion

Headlines may not be the best feature to predict upvotes since it is not necessarily indicative of the post activity. Comments or views may be a better feature to use as well as time posted.
