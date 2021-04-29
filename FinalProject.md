# DATA 310 Final Project - California Startups Success Forecasting Analysis  
### Due Date: 5/18/2021 5:00PM

## Abstract 
With the more advanced knowledge on Machine learning techniques, there is a boundless amount of applications with the help of Tensorflow Package, a mainstream Machine Learning Package for Python users. With the ability to predict and evaluate the values based on the training and testing sets, we want to explore the landscape of Startups and investigate the key factors that a Startup needs to succeed in the state of California, which is one of the major birthplaces of US Startups.     

## Data Description
With the dataset that I collected from [Kaggle](https://www.kaggle.com/manishkc06/startup-success-prediction), we are looking at the in-depth profile of 923 startups in the United States. To narrow the scope of the investigation, we will only be analyzing 488 startups in California, which is accounted for more than half (53%) of the dataset. We will create a subset that includes startups that are founded in California. There are 49 features/columns in this data, we will only be focusing on several quantiative features and a few categorical features as well. Figure 1 displays a list of the chosen variables and their descriptive statistics of the California Startups.  

**Figure 1: Descriptive Statistics for the CA Startups**
<img src="./descriptive_stats.PNG" />

*Since the duration of the first milestone has a significant amount of missing values and it does not define the variable "milestone", I will not include "milestone" for the following analysis.  

Based on Figure 1, we have observed some interesting characteristics. The first thing we can imply is that most Startups do not have a VC nor Angel as the funding source (With the mean of 0.30 and 0.23), this also stimulate a follow-up question, what would be the long-term funding source of these Startups? We can also tell that the average participants of a Startup is around 3 people. Since it is a quantitative variable, we will consider the average participants of a Startup as a variable in the analysis. In terms of the age of the first funding, we can tell that the average time is two years. Related to the the first funding, we also discover that the average total funding is 20.5 million. 

## Problem Statement 
Google, Facebook, Apple, Amazon, Netflix, all these Big-Tech companies that we know today have been through the stage of Startup. Startup describes the young, rising companies that have started from Zero to One. The First Pot of Gold from a Venture Capitalist and any investor is usually the priority of a Startup. To operate a Startup successfully, apart from the stability of the funding, the duration of surviving in the business environment is another indicator for the investor. When a Startup is able to run for more than an extensive time frame, either the company has found an Angel that has faith in the potential of the company or they have established a trust-worthy reputation in the venture capitalists' world. Regardless of the outcome of a Startup, one of the safest approaches for a Startup to create its legacy is to get acquired by other big-brand companies. Hence, due to the nature of the dataset, the measure of a successful startup is the status of whether getting acquired. The goal of this project is to setup a supervised model that the investor's can use to predict the success of a Startup. We aim to investigate the average time for a Startup to first gain the trust from investors?  What are some commonalities related to the funding among these successfully acquired Startups? 

## Model Specification/Architecture

With all the descriptive statistics in mind, we will establish a supervised model that can predict the necessary conditions of these variables. Before we use Keras function as the skeleton structure, we will first create another subset for the Startups that are successfully acquired.

```
# Change the status of acquired and closed to qualitative variable
startup['status'] = startup.status.map({'acquired':1, 'closed':0})
startup['status'].astype(int)

#Create a subset for all success Startup
startup_all = startup
success = startup_all['status']==1
startup_success = startup_all[success]
```

## Model Performance Assessment 

## Conclusion
