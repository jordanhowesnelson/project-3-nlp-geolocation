Project 3 Executive Summary

What makes something distinct to your hometown? Is where you live really that different from the next town? Can you “place” what someone is writing about? All of these ideas are explored by scraping 2 subreddits and using machine learning to determine if a post can be classified as being from Washington, DC or Chicago, IL. Using machine learning, I have tuned a model to identify the contextual clues that define Washington, DC and Chicago, IL to about 90% accuracy. 

The goal for this project was compare the reddit posts of 2 location based subreddits to determine if the machine could learn to determine location from text. I chose to analyze the posts in the Washington, DC and Chicago subreddits. The data was gathered from reddit using the Pushshift API. I created a function to read 1000 posts, every 30 days, for 36 iterations. This 3 year time frame yielded 68,760 posts, 50.9% from Chicago and 49.1% from Washington, DC.

While each post yielded 78 potential variables, many of them contained NaNs or were irrelevant to location (for example: approved, cakeday, background color). I eliminated all but 4 variables: post title, post text, author name, author flair text. 

I tuned a TFIDF Vectorizer to count my data and found that tuning my most performant models (Logisitic Regression, Naïve Bayes, and Random Forest) and including all three in a voting classifier yielded an accuracy score of 89%.

I pulled one more sample to run through my model and gauge it’s performance. I scraped reddit for 10 posts from each of the two subreddits. DC scored a 10/10 for it’s posts, while Chicago got an 80% accuracy. It misclassified 2 posts, one which was inevitable removed from the site. The other seemed to predict DC, I assume based on it's reference to "Old Town." 

In order to clean up these last few misclassifications, there are two potential routes to include more data into this model: include post comments, and/or include some of the author's posts to other subreddits.
