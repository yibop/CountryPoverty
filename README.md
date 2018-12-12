## Overview

Our task is to estimate a country’s poverty rate based on several economic, social, and geographical factors such as total GDP, level of research,  annual growth rate, percentage of arable land and many more. With access to a comprehensive set of data found on the UN website featuring human activities and a geographic dataset found on Kaggle,  we are able to integrate geography with societal  factors to identify possible causes of poverty. In particular, we will attempt to train a machine learning algorithm to predict the poverty rate of a given country, and study from data and results to find which of these attributes, either societal or geographical, are most strongly correlated with high poverty rates, and identify the critical problems that  the world has to tackle in order to end poverty.


## Methodology and Result

We will be using three main algorithms in this projects, which are decision tree, logistic regression and neural network. Since we are trying to explore the correlation between each attribute and poverty level, we will run the three algorithms iteratively, each time removing a different attribute. Then we compare the accuracies during each run, and identify which attribute is removed when the algorithm reaches highest accuracy. Then that attribute is permanently removed, and we repeat the same  process for the remaining dataset. All the societal and geographical attributes are numeric. The outcome "Poverty level" is numeric as well, but we discretize the poverty levels into upper half and lower half categories based on the median poverty rate, so that they can be used to train decision tree and logistic and regression models. 



![DL3Tree](https://yibop.github.io/CountryPoverty/DL3Tree.png)



We built an implementation of ID3 that accepted continuous attributes from scratch (see repository). If an attribute is discrete, we calculate the entropy based on the entropy gain classifying into each value. If an attribute is continuous, we calculate a “best split” value. After repeated trials, and trying to predict multiple markers of economic prosperity (poverty rate, annual gdp growth, consumption), we found that the decision tree that resulted in the highest test accuracy was one that predicted a country’s poverty rate relative to the rest of the world based on 7 geographical and climate attributes: ['Precipitation', 'Climate', 'Arable ', 'Population', 'Area sq mi', 'Pop Density per sq mi', 'CoastlineLength']. The decision tree shown above was part of a set of 100 trials that achieved on average 70% accuracy when trained on 75% and tested on 25% of the dataset. Other decision trees that tried to predict the annual growth rate and consumption resulted in at best 60% accuracy. We will focus on the experiment that produced the above tree in our analysis section. 

### [Click Here](https://yibop.github.io/CountryPoverty/Final_Report.pdf) for a detailed report.

## Contact Information
Thomas Yang
thomasyang2019@u.northwestern.edu

Yibo Pan
yibopan2021@u.northwestern.edu
