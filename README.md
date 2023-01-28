# UCBE-MLAI-PracticalAssignment-17.1
Practical Application Assignment 17.1: Comparing Classifiers

## Problem 1: Understanding the Data

To gain a better understanding of the data, please read the information provided in the UCI link above, and examine the Materials and Methods section of the paper. How many marketing campaigns does this data represent?
Marketing Campaigns represented in the data 
1. The telephone, with a human agent as the interlocutor, was the dominant marketing channel.
2. although sometimes with an auxiliary use of the Internet online banking channel (e.g. by showing information to specific targeted client).

No. of Marketing campaigns was quoted in the article below in the Materials and Methods section: 17 Marketing campaigns

**_The dataset collected is related to 17 campaigns that occurred between May 2008 and November 2010, corresponding to a total of 79354 contacts. 
During these phone campaigns, an attractive long-term deposit application, with good interest rates, was offered. For each contact, a large number of attributes was stored (e.g. see Table 2) and if there was a success (the target variable). For the whole database considered, there were 6499 successes (8% success rate)._**

## Problem 2: Read in the Data
<img width="319" alt="image" src="https://user-images.githubusercontent.com/115063137/215252970-857abf73-18ce-45ab-a983-033d180fa55b.png">

We can see from above that out of the 21 columns present in the dataset, there are 10 Numerical datatypes and 11 Categorical ones.

Numerical/Quantitative DataTypes: Numerical data refers to the data that is in the form of numbers, and not in any language or descriptive form. ex: age,duration,campaign,pdays,previous,emp.var.rate,cons.price.idx,cons.conf.idx,euribor3m,nr.employed

Categorical/Qualitative DataTypes: Categorical data refers to a data type that can be stored and identified based on the names or labels given to them. ex: job,marital,education,default,housing,loan,poutcome,contact,month,day_of_week,y

## Problem 3: Understanding the Features

Examine the data description below, and determine if any of the features are missing values or need to be coerced to a different data type.

<img width="812" alt="image" src="https://user-images.githubusercontent.com/115063137/215253050-ace710a9-ef51-43ca-b387-06f39d260c2e.png">
<img width="697" alt="image" src="https://user-images.githubusercontent.com/115063137/215253084-460b6bcf-926a-4e96-9190-ff37980f6eb2.png">

<img width="733" alt="image" src="https://user-images.githubusercontent.com/115063137/215253203-b8360e0c-59cb-4216-b1cd-c297e1f2c169.png">
you can see that the following features has direct influence on the acceptance of the term deposit (value =y)
1. marital = Yes is higher when couple is married then any other status
2. job  = admin in nature helpes drive understanding of the importance of term deposits as source of additional interest income
3. default = shows no default customers tend to take up more than then defaulted customers.
So the bank should focus more efforts to market to customers based on these attributes above.

the following seem to be unimportant features due to the lack of differences in the demand for such products during the week, see the constant in the following features- day of week, housing does not seem to differ much between yes and no on the term deposit 

<img width="915" alt="image" src="https://user-images.githubusercontent.com/115063137/215254749-db275536-0948-4145-ae86-1611ed866511.png">

duration is different from age, Age has 78 values and Duration has 1544 different values, mostly focused around less than 2000 calls happening across frequencies of 1 to 0.0030. occurence of calls seems very narrow in the band of datasets.
<img width="1102" alt="image" src="https://user-images.githubusercontent.com/115063137/215254864-03a69c31-09ea-4736-a594-3a8c90b1c23f.png">

<img width="1085" alt="image" src="https://user-images.githubusercontent.com/115063137/215254913-bf0c45b4-22a3-4535-afcd-7f3d254a6db8.png">
Note: if the expense of losing customers due to these excessive calls continue is a risk, the banks need better forecasting models to cluster and identify customers' features to better target the specific customer attributes for marketing focus for the highest return of successful sale of term deposits, i.e. target specific demographics like mid to pre-retirement life (age 20-50), education higher or equal to high school and married

<img width="1042" alt="image" src="https://user-images.githubusercontent.com/115063137/215255110-9d790b18-a915-43cb-80f6-5dae4749d998.png">
<img width="899" alt="image" src="https://user-images.githubusercontent.com/115063137/215255159-4e57d0dd-2ce9-4757-bf36-0e61f83af1b6.png">
<img width="1127" alt="image" src="https://user-images.githubusercontent.com/115063137/215255195-c7f4f429-7d8f-479a-9b77-dfb6e466418f.png">

To summarize the type of clientele that dominates this bank's customer database:
1. mostly blue collar workers and admin as well as tecnicians dominate the clientele at this bank
2. 20-60 years of age

The demand has been low based on the response which is only 11.3 % yes, the goal should be to increase the demand to above at least 20% to ensure the campaign is successful, this would offset marketing costs associated and human effort to make calls and internet promotion setup.

<img width="879" alt="image" src="https://user-images.githubusercontent.com/115063137/215255560-c5b6ef18-ca0f-4bb9-8366-45f82198fffb.png">
<img width="1014" alt="image" src="https://user-images.githubusercontent.com/115063137/215255805-5c5b47d8-a49b-4fe6-9e83-fa119619d27e.png">
<img width="834" alt="image" src="https://user-images.githubusercontent.com/115063137/215255670-7151c30d-1773-4819-8523-a708b1c7abef.png">
HIGHEST Correlation in the heat map of the features show that the highest correlation to the response of Yes to take up the deposit
1. emp.var.rate
2. euribor3m
3. cons.price.idx
4. nr.employed
the above features have very close relationships to each other and also to driving the decision to take up the term deposit.


## Problem 4: Understanding the Task

After examining the description and data, your goal now is to clearly state the Business Objective of the task. State the objective below.

* find a model that can explain success of a contact, i.e. if the client subscribes the deposit.

Such model can increase campaign efficiency by :

* identifying the main characteristics that affect success,

* helping in a better management of the available resources (e.g. human effort, phone calls, time)

*  and selection of a high quality and affordable set of potential buying customers.


# Problem 5: Engineering Features

Now that you understand your business objective, we will build a basic model to get started. 
+ Before we can do this, we must work to encode the data. Using just the bank information features (columns 1 - 7), 
+ prepare the features and target column for modeling with appropriate encoding and transformations.
<img width="1098" alt="image" src="https://user-images.githubusercontent.com/115063137/215256930-15f93f3a-db7d-4863-9387-491303493b22.png">

<img width="493" alt="image" src="https://user-images.githubusercontent.com/115063137/215256694-907a863a-bb13-445f-8159-96b580b35bbc.png">
BANK CLIENTS CONCLUSION

+ The ages dont mean to much, has a medium dispersion and dont make sense relate with other variables will not tell any insight

+ Jobs, Marital and Education i think the best analisys is just the count of each variable, if we related with the other ones

+ its is not conclusive, all this kind of variables has yes, unknown and no for loan, default and housing.
+ + Building social economic group of variables - bank_se
<img width="950" alt="image" src="https://user-images.githubusercontent.com/115063137/215256960-b6ee13a5-84f3-4586-9ba1-ec10fcac90b1.png">
<img width="868" alt="image" src="https://user-images.githubusercontent.com/115063137/215256993-e322c95e-9fe4-4507-8aea-a86a39df29f2.png">
Grouping of features into the following feature sets
<img width="1026" alt="image" src="https://user-images.githubusercontent.com/115063137/215257135-54d868e8-6254-4cf9-9774-3fb18bb4c6df.png">

+ 1. bank_client: age,	job	,marital,	education	,default,	housing,	loan
+ 2. bank_related : contact,	month,	day_of_week,	duration
+ 3. bank_se: 	emp.var.rate, 	cons.price.idx,	cons.conf.idx,	euribor3m,	nr.employed
+ 4. bank_o:p_outcome (replace(['nonexistent', 'failure', 'success'], [1,2,3])

<img width="903" alt="image" src="https://user-images.githubusercontent.com/115063137/215257179-d1077e36-9665-413b-8327-6cd206fad043.png">

## Problem 6: Train/Test Split

With your data prepared, split it into a train and test set.

<img width="1163" alt="image" src="https://user-images.githubusercontent.com/115063137/215257322-06766e69-80e2-419c-a481-736caaefd691.png">

## Problem 7: A Baseline Model

Before we build our first model, we want to establish a baseline. What is the baseline performance that our classifier should aim to beat?

+ Our classifier should beat the competition by having the following qualities:

1. high training accuracy

2. low false positive value

3. high test accuracy

4. The area under the ROC curve (AUC) results were considered excellent for AUC values between 0.9-1, good for AUC values between 0.8-0.9, fair for AUC values between 0.7-0.8, poor for AUC values between 0.6-0.7 and failed for AUC values between 0.5-0.6.

###### 1. KNN Model:
<img width="423" alt="image" src="https://user-images.githubusercontent.com/115063137/215257713-93d3fea6-a71c-4781-8817-3ee907882581.png">


<img width="936" alt="image" src="https://user-images.githubusercontent.com/115063137/215257977-b9e8eaca-190c-4bd6-8aaf-f192ea6cbe87.png">


## Problem 8: A Simple Model

Use Logistic Regression to build a basic model on your data.

<img width="818" alt="image" src="https://user-images.githubusercontent.com/115063137/215258063-e7e4a6fc-ecf8-46cf-9f1d-6906177221d7.png">

## Problem 9: Score the Model

* **What is the accuracy of your model?**

<img width="596" alt="image" src="https://user-images.githubusercontent.com/115063137/215258415-cf809051-dc41-4c7a-aa16-88718a263c75.png">

Accuracy is measured by the area under the ROC curve. An area of 1 represents a perfect test; an area of .5 represents a worthless test.

A rough guide for classifying the accuracy of a diagnostic test is the traditional academic point system:

.90-1 = excellent (A)

.80-.90 = good (B)

.70-.80 = fair (C)

.60-.70 = poor (D)

.50-.60 = fail (F)

**Summary Score **
Only the following 2 models are considered excellent out of the 4 models used
	* Logistic Model	0.906100
  * K-Near Neighbors	0.902701
  



## Problem 10: Model Comparisons

Now, we aim to compare the performance of the Logistic Regression model to our KNN algorithm, Decision Tree, and SVM models. Using the default settings for each of the models, fit and score each. Also, be sure to compare the fit time of each of the models. Present your findings in a DataFrame similar to that below:

Model	Train Time	Train Accuracy	Test Accuracy
.	.**

<img width="589" alt="image" src="https://user-images.githubusercontent.com/115063137/215258447-607b38cb-3e31-4d6f-b072-ce2af23000dc.png">

<img width="296" alt="image" src="https://user-images.githubusercontent.com/115063137/215258455-28b7296b-7559-479f-b415-e90345d47768.png">
<img width="493" alt="image" src="https://user-images.githubusercontent.com/115063137/215258509-9cfa0272-b594-4fd4-90e2-0a717f2e1805.png">

*Conclusion that the Logistic regression shows the best Train and Test Accuracy combined with the least training time allows this model to perform well in predictions.

*Its important to know that we have identified clients attributes well enough with the above attributes, but we can still improve by eliminating some un-needed attributes to improve the model when used to predict outcomes with yes.

**ANALYZING THE RESULTS

So now we have to decide which one is the best model, and we have two types of wrong values:

1. False Positive, means the client do NOT SUBSCRIBED to term deposit, but the model thinks he did.

2. False Negative, means the client SUBSCRIBED to term deposit, but the model said he dont.

In my opinion:

The first one its most harmful, because we think that we already have that client but we dont and maybe we lost him in other future campaings

The second its not good but its ok, we have that client and in the future we'll discovery that in truth he's already our client

So, our objective here, is to find the best model by confusion matrix with the lowest False Positive as possible.

Therefore looking at the model with the lowest false Positive at 433 is Decision Tree Model**


## Problem 11: Improving the Model

Now that we have some basic models on the board, we want to try to improve these. Below, we list a few things to explore in this pursuit.

More feature engineering and exploration. For example, should we keep the gender feature? Why or why not?
Hyperparameter tuning and grid search. All of our models have additional hyperparameters to tune and explore. For example the number of neighbors in KNN or the maximum depth of a Decision Tree.
Adjust your performance metric

**11.1. More feature engineering and exploration : handling outliers**

**11.1.1 start a new data frame bank_copy to show improvement with new features incorporated**

<img width="843" alt="image" src="https://user-images.githubusercontent.com/115063137/215259137-ab848582-9be5-470f-afd6-c1e6d0224f65.png">
<img width="804" alt="image" src="https://user-images.githubusercontent.com/115063137/215259171-7c799310-8bcd-4eb1-b7c6-03f7d224bf82.png">

**11.1.2 Ordinal Number Encoding**

Here we are gonna encode the features which has yes,no and unknown. We'll assign yes:1,no:0 and unknown:-1**

<img width="695" alt="image" src="https://user-images.githubusercontent.com/115063137/215259407-091bc97d-7d23-4488-9d4b-a99903b684c6.png">

**11.1.3 Frequency Encoding**

<img width="598" alt="image" src="https://user-images.githubusercontent.com/115063137/215259455-da1c8e33-0500-412e-88c2-684ae475ddf7.png">

 **11.1.4 Target Guided Ordinal Encoding**

 Lets encode marital feature based on the target 'y' . First let's find the mean of target with respect to marital feature
<img width="672" alt="image" src="https://user-images.githubusercontent.com/115063137/215259613-28eb57a3-7835-44a2-88ab-31fb5f16f225.png">

**11.1.4 Standardization of numerical variables**

<img width="1249" alt="image" src="https://user-images.githubusercontent.com/115063137/215259642-6e00532d-3bb9-45c3-91a5-b3926374de13.png">


**11.1.5 Feature Selection with new engineered features

feature importances and prune our features to make our model perform well.**

<img width="671" alt="image" src="https://user-images.githubusercontent.com/115063137/215259697-b34c406b-0df3-4e67-8afb-ab82785e85ad.png">
we can see the coeff is highest in the following input variables:

* duration

* euribor3m

* age

* nr.employed

**Observing the results and the exploratory data analysis, the most important features which the bank should focus on to attract more customers to buy term deposit are:**

1.Duration being one of the most influential factors,i.e. the higher the call duration the higher the chances of a sale. So the bank should focus on enhancing the quality of calls by building a rapport with the customers, decreasing wait time, checking in with the customers, and most importantly take feedback from the customers.

2.Euribo3 is indicative of the trend that the higher interest rates attract more customers. So there are two things which the bank can pursue which are as follows: -Target the age group which is liable to get higher interest rates (4.5-5) particularly. -Increase the marketing campaign when the interest rates are higher, which can help in bringing more clients on board with the term deposits.¶

3. nr.employed shows employed trend indicates that more number of employees leads to more number of customers, which makes sense because if there are more employees, more leads can be targeted, proper followups and check-ins can be done. On the other hand, customer satisfaction could be achieved by creating a dedicated after-sales team. So, the bank should focus on hiring more people.

**11.2 Logistic regression with Hyperparameter tuning with GridSearchCV**

**Let's fit the model in logistic regression with parameter tuning and figure out the accuracy of our model**

<img width="663" alt="image" src="https://user-images.githubusercontent.com/115063137/215259807-c0487b0d-2e97-49fa-a425-27accbf8d530.png">

<img width="792" alt="image" src="https://user-images.githubusercontent.com/115063137/215259835-dff50b80-08d8-4790-9597-5960e5cfb3d4.png">

**The Confusion matrix result is telling us that we have 6399+178 correct predictions and 397+139 incorrect predictions. The Classification report reveals that we have 94% precision which means the accuracy that the model classifier not to label an instance positive that is actually negative which is important as we shouldn't label a lead as positive in making a term deposit when he/she isn't interested in making a deposit
**

<img width="1039" alt="image" src="https://user-images.githubusercontent.com/115063137/215259848-32cc4638-c62b-4f1d-9c46-028f2cee6be1.png">

**Let's fit the model in logistic regression with parameter tuning and figure out the accuracy of our model**
**Note: we have improved the model accuracy for the top 2 models especially using GridSearch CV we identified in the initial training of new features engineered.

LogisticRegression(random_state=0) The mean accuracy of the model is: 0.9246450161675804
**

**11.2.2 Tuning Hyperparameters with decision Trees
Utility Function to help with tuning**

<img width="897" alt="image" src="https://user-images.githubusercontent.com/115063137/215259888-afbc524e-4fc6-479b-875c-32c7adceb622.png">

**Let's fit the model in logistic regression with parameter tuning and figure out the accuracy of our model**
<img width="974" alt="image" src="https://user-images.githubusercontent.com/115063137/215259894-5073f3bc-3c0e-4b63-9939-72bd671ef04e.png">

**Let's fit the model in logistic regression with parameter tuning and figure out the accuracy of our model**
<img width="1146" alt="image" src="https://user-images.githubusercontent.com/115063137/215259946-8247d35c-6bf6-4245-ad17-786ff8b8bbcb.png">

**The optimal number of neighbors is 24 with 90.5% previously without additional feature engineering is now increasing accuracy to 93% with fewer neigbors of 8.**

its important to note the performance metric must adapt to the following with hyper parameters to accomodate for 
1. improved forecasting performance in terms of time to train the data by 
 + reducing time taken to train through reducing depth of tree
 + reduce the number of K neighbors if KNN is used
2. Focus on ROC and Recall is important as we see increasing customers being used in the client base.
**WHY?**
Because from our extensive analysis, we have learnt the Top take aways are:

* Duration has a huge impact on the outcome. The more the customer is engaged, the more the probability he/she would make a deposit.
* The state of the country's economy plays a huge role. The better the economy the more willing are customers to make a deposit. So campaigns should be targeted during this period. October being one of the bad months with highest fluctuations in the economic status of country, campaigns in such months should be avoided.
* People in blue-collor jobs, admins, technicians are more probable to make a deposit
* Customers with good background education are more likely to do well financially and would have the mind set to save. University degree or higher degree holders are more likely to deposit.
* Increasing the likelihood of sign up for these products could potentially include reducing the loan interest rates if the customer has loans with the banks if they stay with the term deposit longer than 1 year to encourage sign up and build relationship with the bank for longer and reduce churn!
* Therefore, the science of forecasting needs to be mixed with the need to understand the correlation of client attributes and existing products offered to create a portfolio that yields higher revenue and profits over time based on the cost it takes to maintain the products that customers have taken up.
