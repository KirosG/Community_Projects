# Project: Project 3: Reddit's API WebScrapping for Predicting Comments and Modeling
  Kiros Gebremariam    June 2018
  Data SCience Immersive student @ General Assembly

### Overview

  Reddit is one of the top social news distribution and websites rating by users every day from politics to specific daily life. The Reddit website was 6th most visted and ranked here in the united states and accessed globally with high 30's rank.  The site was significantly dependent on users comments and the comments ups(votes). Project three focuses on webscraping using hot/json. The importance of this web scraping project was to  understand,see and predict the prominent factors that makes reddit posts popular. The  Scenario given was i am a fresh Data science bootcamp and looking to break throgh  in the world of freelance data journalism.  Nate Silver and Co at FiveThirtyEight have agreed to hear for a pitch in two weeks.   The goal here was as a Data scientist to determine What characteristics of a post on Reddit are most predictive of the overall interaction on a thread (as measured by number of comments/ups)?
   
   
   -----------
   Executive Summary
   --------------
  I have scrapped 31,975 posts  using the HotJson API for seven days.  The timing was arranged to be in the morning and afternoon and finally after removing duplicates and conducting the data munging I  have left with only 3300 posts. The Data collection  and data cleaning took a significant  portion of the time. In the first step, I did some feature analysis. Then I picked up score, title, subreddits and number of comments as my target.  In order to answer and satisfy my goal i reviewed and assesed  variety of models i have been thought in my Data science Immersive course and to determine the best  possible approach to accurately predicting the factors that lead to a popular post , here when i say popular post; its a post defined  with greater than the median number of comments from the collected dataset. After going through all the exploratory data analysis, knowing the multidimensionality of the data elements. I focused on  analysing the data of greatest importance on Reddit I have opted to use a classifier analysis looking at a wide variety of factors.i chosed to see and  investigate the effect of titles on the popularity of a reddit posts.  The stage after  cleaning and munging real data of reddit API, i start manipulating the data for analysis purpose and then after this i scaled the data to check the dimension compatibility and comparability. After going through I then updated my model to gauge the effect of adding several features to the model. I have applied count vectorizer and found the most common words as well as i found that posts with less than 40 characters were the most commented by the reddit users.  As reddit is one of the top three most visited website  in the united states focusing on short titles and using  the third quantile of the number of comments by subreddit, i found out that Askreddit was the most visited site followed by worldnews,technologysubreddit,personalfinance and videos.  Finally, I have picked  Logistic regression,RandomForest Classifier as my model. I found a model that accurately predicts the whether or not a post will be popular with about  72% accuracy on a consistent basis. My predictive features (title,subreddit, num_comments) were highly effective in other models as well. Ultimately the most effective model selected in my analysis was LogisticRegressionClassifier. My findings suggest that this is a highly effective model which has the potential for further analysis both within the reddit sight. I believe this analysis can also be replicated in the same site or other similar websites to other post base discussion and social media sites. 
  
------------------------
## Presentation: 
Presentation linke:  https://docs.google.com/presentation/d/1aR8oIEEyCnFE8EqKGk96u-IzMyF8dCXpBWUWF69ymfY/edit#slide=id.g3c20741785_2_144
----------------------------
## DATA SOURCE
*  url = "https://www.reddit.com/hot.json
* collected for almost 7 days
* Collected 31,975 posts
* Reduced to 3,300 unique
* Every Day collected data was concatenated  until the last day
*  The memory size of the Excel CSV files exceeded more than 1.5 GB
------------------------------
## DATA COMPONENTS
* TITTLE 
* Subreddit
* ASKSUBREDDIT
* NUMBER OF COMMENTS

--------------
#### DATA SCIENCE TOOLS AND METHODS APPLIED

### Natural Language Processing
* I applied Countvectorizer and TFIDF “vectorization” the process of turning text into numbers so that we can predict an outcome. Using these i have generated some out puts and can be accessed on 
* Using this count vectorization  i applied randomforest and logistic regression to predict what text will engage readers most 

## MACHINE LEARNING (PREDICTION/Modeling)
* Random Forest
* Logistic Regression
* KNN
*  The Logistic Regression performed better than RF and KNN

