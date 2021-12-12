# Project 3: Classifying subreddits posts from UEFA Champions League and English Premier League

EuroFootball is a monthly football magazine covering both the major leagues in Europe (Premier League, Serie A,La Liga etc) as well as the European competition such as the UEFA Champions League and Europa League.

One of the columns in EuroFootball publishes readers' comments on any topics on the teams they support. Invariably, these comments usually revolves around players' performance, celebration of winning an important match and criticism of the manager's selection.

Fans submit their comments through email, the best ones of which are then reviewed and selected by the editor for publication. However, this is an extremely time-consuming process where the submitted comments needs to be sorted into topics before the editor review. In particular, comments regarding the English Premier League and the UEFA Champions League forms the majority.

The editorial team in EuroFootball has therefore tasked its data science team with creating a model which can predict whether comments submitted by readers has to do with the English Premier League or the UEFA Champions League.

In order for the model to predict and categorise the comments correctly, the model needs to be trained on labeled data. The data science team therefore propose to scrape posts from Reddit under the the r/championsleague and r/PremierLeague for the labeled data.

---

## Executive Summary
For this project, posts from subreddits r/championsleague and r/PremierLeague were scraped. The following summarises the analysis process:

1. Clean the raw posts from the scraped data by removing duplicates, urls and unwanted strings

2. For each posts, tokenize into words convert them into lower-case. POS-tag the word tokens before lemmatizing the tokens

3. Train and evaluate the performance of Multinomial Naive Bayes, Logistic Regression with both l1 and l2 regularization and Random Forest to arrive at the model. Identify word features of importance and analyse misclassified posts for further improving the models


### Key Conclusions and Recommendations

#### Conclusion

1. The CountVectorizer with RandomForest is the best performing model. One of the advantages of RandomForest over algorithms which work on the assumption that classes can be separated by a straight line (e.g.Logistic Regression) is that it can handle high dimensional and complex data structures.

2. Some word features is related exclusively to champions league and the premier league respectively. These words are usually club names or player names and appears in the important features of all four models that were trained.

3. It was observed that during the training of both RandomForest models, choosing to gridsearch over specific max_depth reduced the accuracy of the models. The gridsearch eventually selected max_depth as None. Theoretically, allowing the RandomForest unrestricted depth may lead to overfitting. The average depth of the fitted models were around 70 to 75. Empirically, however, there was no overfitting of the training set when compared to the test set. A plausible explanation is that RandomForest algorithm splits the tree using a subset of trees for each bootstrap, this itself is a defence mechanism against overfitting which reduces the effect of depth.

4. The misclassified posts typically falls into the following categories:

    - The post was too short to contain any significant influential words for the model to make a correct prediction

    - The post was talking about the Champions League in a Premier League subreddit and vice-versa.

    - The content of the posts had nothing to do with the subreddit. This happens quite frequently when users ask about links for pirated football match streams or vpns to watch streams outside of their country.

### Recommendations and Further Study

There is clearly room for improvement for the EuroFootball Data Science team to further improve the performance of the classifier model. 

The following are suggested actions to improve the models:

1. Further scraped posts from subreddit needs to be reviewed to ensure they are free from the above mentioned type of posts before they are used to train the models.

2. Comments should be scraped from another football website (e.g the Athletic) where high quality football journalism foster discussion and not about sharing video clips.