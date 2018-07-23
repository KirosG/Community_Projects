# Project 1: SAT_ACT SCORE OF STATES
Author : Kiros Gebremariam  May 4,2018

### Overview
**Data science is a field in which we apply data to solve real-world problems. Therefore, projects and presentations are means by which we can assess our  ability to solve real-world problems in a data-driven manner.This project was basically focused on  some basic statistics and some Python programming concepts of the Data Science Immersive couse of the General Assembly  given in the  end of April and first week of May.**

For the first project,   the work is going to be  on  SAT and ACT scores around the United States. The given assignment was  Suppose that the College Board - the organization that administers the SAT - seeks to improve the participation rate of its exams. My presentation was geared toward **non-technical** executives with the College Board used, at minimum, the provided data to make recommendations about how the College Board might work to increase the participation rates of these exams across all the 50 US states.


---

### What was my Goal here in Analysing the SAT-ACT of 2017

-  Describing the data
- Performing methods of exploratory data analysis, including:
  - Use Matplotlib to create visualizations
  - Use NumPy to explore distributions of individual variables and relationships among pairs of variables
- Data Munging and cleaning using Jupyter notebook 

### Starter code

For this project I used a Jupyter notebook. This notebook will use matplotlib for plotting and visualizing the SAT-ACT data. This type of visualization is handy for prototyping and quick data analysis. 

Open the [starter code instructions](./code/) in a Jupyter notebook.

---

### Dataset

For this project, you'll be using two datasets:

- [Dataset: SAT Scores](./data/sat.csv)
- [Dataset: ACT Scores](./data/act.csv)

You can see the source for the SAT data [here](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent), and the source for the ACT data [here](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows).

These data give average SAT and ACT scores by state, as well as participation rates, for the graduating class of 2017.

---
### Useful Resources

- [How to find the data you need](http://flowingdata.com/2009/10/01/30-resources-to-find-the-data-you-need/)
- [How to give a good lightning talk](https://www.semrush.com/blog/16-ways-to-prepare-for-a-lightning-talk/)

---
# Executive summary
 1. Data Analyzed:

The 2017 data set included data on SAT and ACT participation rates, aggregated at the state level. It also included data on average state performance on the SAT and ACT across all 50 US states.


2. Relationship between the SAT and ACT
 The relationship between the Two sets of Exams was paradoxically negatively correlated  and have a tendency to displace each other in any particular state. Participating in one test is negatively correllated with participating in the other test (correlation = -.84). In approximately 20 states, ACT participation is nearly 100%, suggesting that that SAT has been largely displaced by the ACT.


 3. Relationship between test participation and performance
To see the relationships, its important to see the correlationcoefficientt and based on that the relationship between SAT and ACT participation rate shows  a very strong negative correlation(-0,84). Indicating that as SAT participation increases the ACT participation goes down and viceversa.I do not think this have causal relationship based on the existing data and its very hard to give final strategy based on this as the results may be a matter of coincidence or chance.A state's performance on the ACT is positively correllated with its SAT participation rate (.69) and negatively correllated with its ACT participation rate (-.86).  