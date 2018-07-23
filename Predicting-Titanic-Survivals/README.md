---
layout: post
title: Titanic Survivability Odds

 While the infamous shipwreck happened over 100 years ago, its cultural significance is sunk deep into our collective memory as one of the most tragic manifestations of hubris, classism, and dumb luck.  To that end, I analyzed the data provided on Kaggle's website to determine more specifically how features such as age, gender, class, and wealth predetermined a passenger's fate on April 15, 1911 aboard the USS Titanic.
---

While the infamous shipwreck happened over 100 years ago, its cultural significance is sunk deep into our collective memory as one of the most tragic manifestations of hubris, classism, and dumb luck.  To that end, I analyzed the data provided on Kaggle's website to determine more specifically how features such as age, gender, class, and wealth predetermined a passenger's fate on April 15, 1911 aboard the USS Titanic.

## "Where to, Miss?"

<iframe src="https://giphy.com/embed/ghvWn8S0jiI0M" width="480" height="203" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/movie-titanic-ghvWn8S0jiI0M">via GIPHY</a></p>


For this project, I want to predict a passenger's fate using machine learning across several different types of models.  I am also interested in identifying which features had the greatest impact on a person's chances of survival.

This dataset is neatly packaged in a csv file that can be downloaded from Kaggle's [Titanic competition](https://www.kaggle.com/c/titanic/data) page.  Other projects are not as accessible, and I explore other methods of extracting data in other posts.  

After I downloaded the 'train' set, I read the data into my Jupyter Notebook to begin my analysis.  You can see all of the code associated with this project in the corresponding [GitHub repo](https://github.com/KirosG/GA_Projects).

## "Remember, they love money, so pretend like you own a gold mine and you're in the club"


Whenever I begin with a new dataset, I like to get an understanding of its shape, stats, and potential pitfalls (null values, outliers, categorical data).  I use descriptors like train.info(), train.shape(), train.describe() as well as a mask I wrote to slice on columns that specifically have null values.  There are many ways to do this, but masking makes the most sense to me.  

In sum, this dataset has 891 rows across 12 columns, five of which are categorical columns: 'Name',	'Sex',	'Ticket',	'Cabin',	'Embarked' and seven of which are numerical columns: 'PassengerId',	'Survived',	'Pclass',	'Age',	'SibSp',	'Parch',	'Fare'.

For illustrative purposes, I plotted some graphs to help visualize the dataset.   and can be accessed [here](https://github.com/KirosG/GA_Projects)

There are three columns with null values: 2 in Embarked, 177 in Ages, and 687 in Cabin.  I dropped the two rows with missing values in Embarked since 2 rows out of 891 did not seem like it would make a huge difference in my model.  I then filled the 177 missing values in Ages with the mean age of all the passengers.  Finally, I relabeled the NaN values in Cabin to "Unidentified" from which I then stripped just the first letter from all the cabins in order to make a dummy column called Cabin_category.  This column organized the cabins in this neat array: 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'T', 'U'.  


## "You don't know what hand you're gonna get dealt next"


Here's where I engineered my features, whether it was dropping columns entirely or creating new columns.  For this dataset, I decided to drop the PassengerId, Name, and Ticket columns since their values do not contribute to predicting whether someone survived or not.  Whether someone was male or female, however, did so I encoded those columns: 0 for male and 1 for female.  I also dummified the Embarked and Cabin_category columns to determine whether those features played a role in survivability.  Finally, I added columns like 'IsReverend' which encoded whether someone was a Reverend or not and 'FamilyCount' which combined the values of 'SibSp' and 'Parch' to give further detail to the model.  

In order to get the most of the dataset, I polynomialized all of my features after enigneering them.  Every feature was multiplied by every other feature in order to build out and identify the features that are most highly correlated to each other.  231 features were built out.


After polynomializing, I scaled my data using StandardScaler.



<iframe src="https://giphy.com/embed/Y4aRyFaavT9ss" width="460" height="480" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/Y4aRyFaavT9ss">via GIPHY</a></p>


## "It is a mathematical certainty."


Because this is a binary prediction, I chose to build two types of models: one using Logistic Regression and the other using k-Nearest Neighbor Classifier using best parameter gridsearch.  Within my LogReg model I tried using both Ridge and L2 penalties each with an alpha of 1.  For my kNN models, I tried  weights uniform and k=5. BernoulliNB with alpha 0.497 All seemed to perform pretty well, but which one should I choose to make my predictions?

To more easily compare my scores, I generated a table to catalogue my training and test scores across all of my models.  As expected, my training scores were higher than my test scores given that I fit my models to my training data.  It looks like the models all fared pretty well, however, it looks like kNN=3 is overfit given the discrepancy in the training v. test data.  On the other hand, kNN=25 looks like a great model given how close the training and test scores are.  This means that if more data were to become available in other test dataset, the kNN=25 model would account for about 80% variance of the variance from the test dataset.all are generated using the Grid searchCV best parameter tunning.

| Model  | Penalty | Alpha | Train Score | Test Score |
|--------|---------|-------|-------------|------------|
| LogReg | L2      | 1     | 0.821       | 0.793      |
| kNN    |manhattan| 5     | 0.855       | 0.757      |
| kNN    |Uniform  | 5     | 0.855       | 0.757      |
| BNB    |         | 0.49  | 0.771       | 0.771      |


In the end, though, while kNN=5 did perform well on training dataset, I'm going to go with the LogReg model with penalty L2and alpha = 1 given that it performed the best overall.


