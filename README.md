### Problem Statement:

Gathering text data from Reddit posts from the baseball and basketball subreddits using Pushshift’s API, we are comparing the accuracy scores of logistic regression and random forest models.



### Data:

I got the data by using Pushshift's API to retrieve text data from Reddit posts.
The columns I used to build my model are

|Feature|Type|Dataset|Description|
|---|---|---|---|
|subreddit|integer|df|0 = baseball and 1 = basketball| 
|title|string|df|The title of the posts


### Methodolgy:

- Dropped all the columns except for subreddit and title. The selftext column had too many missing values.
- Removed of special characters
- Removed punctuation marks
- Tokenized text data
- Removed English stop words


### EDA:

![] (baseball_top_words.png)
![] (basketball_top_words.png)
![] (top_words.png)


### Data Preprocessing:

- Data Augmentation: One hot encoded subreddit column so baseball = 0 and basketball = 1
- Vectorizing title column to use in the models


### Modeling:

- Feature: title column
- Models: Logistic Regression and Random Forest
- Used gridsearching/hyperparameter tuning to use the best parameters to get the best score for the model


### Results:

- Logistic Regression Accuracy Scores:
- Train: 0.906  Test: 0.858
- Confusion Matrix: ![] (lr_confusion_matrix.png)
- Specificity: 0.78  Sensitivity: 0.936


- Random Forest Accuracy Scores:
- Train: 0.998  Test: 0.904
- Confusion Matrix: ![] (rf_confusion_matrix.png)
- Specificity: 0.884  Sensitivity: 0.924


### Conclusions:

When comparing both of these models, it is clear that the random forest model performed significantly better than the logistic regression model in terms of accuracy.


### Next Steps:

In the future, I would like to use more posts from the past year to possibly better our models. I would also like to try other types of classification models and compare them to random forest.
