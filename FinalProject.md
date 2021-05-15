# DATA 310 Final Project - California Startups Success Forecasting Analysis  
### Due Date: 5/18/2021 5:00PM

## Final Presentation Link [Click Here](https://docs.google.com/presentation/d/1sZCz2qkfwxofQ5vASabRpsx0R50TtfQO2pVes0UZJL4/edit?usp=sharing)


## Abstract 
With the more advanced knowledge on Machine learning techniques, there is a boundless amount of applications with the help of Tensorflow Package, a mainstream Machine Learning Package for Python users. With the ability to predict and evaluate the values based on the training and testing sets, we want to explore the landscape of Startups and investigate the key factors that a Startup needs to succeed in the state of California, which is one of the major birthplaces of US Startups.     

## Data Description
With the dataset that I collected from [Kaggle](https://www.kaggle.com/manishkc06/startup-success-prediction), we are looking at the in-depth profile of 923 startups in the United States. To narrow the scope of the investigation, we will only be analyzing 488 startups in California, which is accounted for more than half (53%) of the dataset. We will create a subset that includes startups that are founded in California. There are 49 features/columns in this data, we will only be focusing on several quantiative features and a few categorical features as well. Figure 1 displays a list of the chosen variables and their descriptive statistics of the California Startups. 

**Figure 1: Descriptive Statistics for the CA Startups**
<img src="./descriptive_stats.PNG" />

*Since the duration of the first milestone has a significant amount of missing values and it does not define the variable "milestone", I will not include "milestone" for the following analysis.  

Before we discussed about the descriptive statistics, it is essential to define some of the variables. To start off, we can define how a round financing works. These funding rounds usually refer to the second stage of financing, which is after seed capital (from friends, family, and founders) and the first major round of funding from VCs. These investors offer money in exchange for an equity stake (such as stocks and shares of the Startup). Startups use the money received for talent acquisition and research & development. These funding rounds are usually not profitable but can certain generate revenues and assets for the company. Another variable that we need to understand is Angel investor. These Angels are high net-worth individuals who provide investment in the early difficult stages. The last variable that I would like to acknowledge is the average participants. This is the average size of the employees in a Startup.        

Based on Figure 1, we have observed some interesting characteristics. The first thing we can imply is that most Startups do not have a VC nor Angel as the funding source (With the mean of 0.30 and 0.23), this also stimulate a follow-up question, what would be the long-term funding source of these Startups? We can also tell that the average participants of a Startup is around 3 people. Since it is a quantitative variable, we will consider the average participants of a Startup as a variable in the analysis. In terms of the age of the first funding, we can tell that the average time is two years. Related to the the first funding, we also discover that the average total funding is 20.5 million. 


## Problem Statement 
Google, Facebook, Apple, Amazon, Netflix, all these Big-Tech companies that we know today have been through the stage of Startup. Startup describes the young, rising companies that have started from Zero to One. The First Pot of Gold from a Venture Capitalist and any investor is usually the priority of a Startup. To operate a Startup successfully, apart from the stability of the funding, the duration of surviving in the business environment is another indicator for the investor. When a Startup is able to run for more than an extensive time frame, either the company has found an Angel that has faith in the potential of the company or they have established a trust-worthy reputation in the venture capitalists' world. Regardless of the outcome of a Startup, one of the safest approaches for a Startup to create its legacy is to get acquired by other big-brand companies. Hence, due to the nature of the dataset, the measure of a successful startup is the status of whether getting acquired. The goal of this project is to setup a supervised model that the investor's can use to predict the success of a Startup. We aim to investigate the average time for a Startup to first gain the trust from investors?  What are some commonalities related to the funding among these successfully acquired Startups? 

## Model Specification/Architecture

With all the descriptive statistics in mind, we will establish a supervised model that can predict the necessary conditions of these variables. I decided to change the "status" column to binary variable. Before we use Keras function as the skeleton structure, we will first create another subset for the Startups that are successfully acquired, which gives us 332 samples.

```
# Change the status of acquired and closed to qualitative variable
startup['status'] = startup.status.map({'acquired':1, 'closed':0})
startup['status'].astype(int)

#Create a subset for all success Startup
startup_all = startup
success = startup_all['status']==1
startup_success = startup_all[success]
```

We also created a lot of 

## Model Performance Assessment 

## Conclusion

## Reference
Ang, Y. Q., Chia, A., &amp; Saghafian, S. (2020). Using Machine Learning to Demystify Startups Funding, Post-Money Valuation, and Success. Harvard Kennedy School Faculty Research Working Paper Series. https://doi.org/10.2139/ssrn.3681682 
Ganti, A. 2020. Angel investor. Retrieved April 30, 2021, from https://www.investopedia.com/terms/a/angelinvestor.asp <br/>
Huang, G. (2016). Predict Startup Success using Network Analysis and Machine Learning Techniques . Stanford CS224W: Social and Information Network Analysis (Autumn 2016). http://snap.stanford.edu/class/cs224w-2016/projects.html. 
KC, M. (2020, September 16). Startup Success Prediction. Kaggle. https://www.kaggle.com/manishkc06/startup-success-prediction. 
Kenton, W. 2021. What is a round financing? Retrieved April 30, 2021, from https://www.investopedia.com/terms/a/a-round-private-equity.asp
