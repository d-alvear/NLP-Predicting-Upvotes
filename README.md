# NLP: Predicting Upvotes Based on Headline
## Introduction
Hacker News is a community where users can submit articles, and other users can upvote those articles. The articles with the most upvotes make it to the front page, where they're more visible to the community.
## Goal
In this project, I'll be predicting the number of upvotes articles received, based on their headlines. Because upvotes are an indicator of popularity, I'll discover which types of articles tend to be the most popular.
## Data

The data set consists of submissions users made to Hacker News from 2006 to 2015. Developer Arnaud Drizard used the Hacker News API to scrape the data, which can be found in one of his [GitHub repositories](https://github.com/arnauddri/hn). I've sampled 3000 rows from the data randomly, and removed all of the extraneous columns. I will solely be working with the following four columns:

* `submission_time` - When the article was submitted
* `upvotes` - The number of upvotes the article received
* `url` - The base URL of the article
* `headline` - The article's headline

## Conclusion

Headlines may not be the best feature to predict upvotes since it is not necessarily indicative of the post activity. Comments or views may be a better feature to use as well as time posted.
