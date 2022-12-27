# NutritionalLabel_CampusRecruitmentPlacement
Nutritional Label for Automated Decision System

## Background
Our project will be focusing on analyzing an automated decision system of students’ job
placement by campus recruitment. The purpose of this automated decision system is to predict
whether a student gets a job placement and the salary secured by successfully placed students.
The author of the analyzed automated decision system is interested to determine the features
from the dataset that affects placements and salaries. Therefore, the author’s goals is to answer
the following questions: Does GPA affects placement? Does higher secondary education
percentage still affects placement? Is work experience a requirement to secure a placement?
Access to the automated decision system including the input dataset can be located by the link:
https://www.kaggle.com/code/atishadhikari/placement-dataanalysis-classification-regression

## Input and Output
According to the Kaggle site that holds the implementable codes and the dataset used for
the automated decision system, the input that is utilized for the system is provided by a professor
from Jain University. The dataset consists of placement data of the students in Jain University.
Taking a further look into the dataset, the dataset is comprised of 15 features and 215
observations where the 15 features includes 7 categorical features, 7 numerical features and 1
boolean feature. As missing values or nulls are may contain important information for the
features and will affect the prediction, it is also essential for us to identify whether is there cells
that contain missing values or nulls in the dataset. In the utilized input, there are 67 identified
missing values in the salary features.

The 7 categorical features includes gender, board of education for secondary education
(10th-grade) (ssc_b), board of education for higher secondary education (12th-grade) (hsc_b),
specialization in higher secondary education (hsc_s), undergraduate degree field (degree_t),
postgraduate MBA specialization (specialisation) and status of placement (status). Below is a
table of description by categorical features listed as above:

<img width="892" alt="Screenshot 2022-12-27 at 4 12 22 PM" src="https://user-images.githubusercontent.com/120950225/209723407-551ac527-515e-48c7-8573-ac81c5310863.png">

Furthermore, the boolean feature in the input dataset is the work experience (workex) described
as the table below:

<img width="892" alt="Screenshot 2022-12-27 at 4 18 15 PM" src="https://user-images.githubusercontent.com/120950225/209723343-be1ada78-e2a0-4554-9698-7470c9c29a6e.png">

Moreover, the 7 numerical features includes serial number (sl_no), secondary education (10thgrade)
percentage (ssc_p), higher secondary education (12th-grade) percentage (hsc_p), undergraduate degree percentage (degree_p), employability test percentage (etest_p),
postgraduate MBA percentage (mba_p) and salary offered by corporate (salary). Below is a table
of description by numerical features listed as above:

<img width="892" alt="Screenshot 2022-12-27 at 4 20 40 PM" src="https://user-images.githubusercontent.com/120950225/209723492-de616c83-4714-4799-bd25-7e0a6b56f429.png">

The author also conducted a pairwise correlation between features. From the correlation
matrix, values obtained will lie between 0 and 1, where 0 indicates no correlation and 1 indicates
strong correlation between features. The correlation between features are displayed in heatmaps:

<img width="636" alt="Screenshot 2022-12-27 at 4 20 53 PM" src="https://user-images.githubusercontent.com/120950225/209723744-04b070bd-3075-4c71-b0e0-4d4283ada90d.png">

The output obtained from executing this automated decision system according to the
category of of output are class labels. The output of this automated decision system reports
features that affect placement from campus recruitment as well as salaries that are offered by the
corporation to the students that were offered placement for the students studying at Jain
University.


## Implementation and Validation
Analyzing the author’s code for the ADS, it is obvious that the author is utilizing different approaches to the prediction for both students’ placement and salary secured by students that are placed. For prediction of students’ placement, the author decides to utilize binary classification approach whereas for prediction of salary secured, the author decides to utilize the regression approach. Before diving into each of the approach, the author also engage in some data preprocessing. From the input dataset, the author determines that features like ssc_b and hsc_b, which are both board of education did not seems to have much effect on both prediction. Hence, both ssc_b and hsc_b are dropped from the dataset and only focused on the other features from the input. Moreover, the author also encodes all categorical features in the dataset to ease the prediction processes.

Looking into the placement prediction that is performed by binary classification, the
author approaches this with two different models, decision tree based model and logistic
regression model. The author first engage in more pre-processing and drop the salary feature
from the dataset to prevent the salary feature from affecting the placement prediction. After undergoing data pre-processing, below is the distribution obtained:

<img width="748" alt="Screenshot 2022-12-27 at 5 20 09 PM" src="https://user-images.githubusercontent.com/120950225/209727532-22ee3fe7-9867-4b27-a37b-ae6fa0df5f62.png">

Then, the dataset is split into train and test sets by 70% and 30% respectively. Under the decision tree based model, decision tree classifier is initiate with criteria “entropy” for the information gained and fitted. According to the accuracy score obtained from this classifier, this classifier is 83% accurate in predicting whether a student is placed. On the other hand, random forest classifier is also initiated with n_estimators = 100 and fitted, obtaining an accuracy score of 86% accurate in prediction. Under the logistic regression model, the author utilize one-hot encoding and encode all categorical features and scale all features to be in a range between 0 and 1 before splitting and fitting the data into the logistic regression model. This obtained an accuracy score of 89% accurate prediction for placement. Looking into the salary offered prediction, the author’s approach is modeling with linear regression. First, the author drop all null values in the salary feature as those null values represent students that are not placed and the status feature from the dataset. After process of data pre-processing, below is the display of distribution obtained:

<img width="730" alt="Screenshot 2022-12-27 at 5 19 21 PM" src="https://user-images.githubusercontent.com/120950225/209727631-e1ec1d0f-a468-4ed0-a79f-a0782ecf9f35.png">

Then, the author continues with feature scaling for all features in the X dataset containing all features except salary and remove outliers of salary greater than 400000 as there are limited students offered that range of salary. Lastly, the author determines least significant features by rsquared score indicating the top-5 most significant features among all features and by determining p-value with OLS Regression indicating top-5 most significant features among all features. This determines the top-5 features affecting salary. The ADS is validated by answering the stated goal of the ADS, which is mentioned in the background part of this report. We know that this ADS achieves the goals as it determines that academic performance affects placement regardless of whether it is higher secondary education percentage, undergraduate percentage or postgraduate MBA percentage. Moreover, the goal is also achieved when the ADS indicates that having work experience affect placement status of students.


## Outcomes
According to the author, prediction of the students’ placement are determined using three
different models which all yield different accuracy score. The decision tree based model yield an
83% accuracy in making prediction, random forest model yield an 86% accuracy in predicting
and logistic regression model yield an 89% accuracy in placement prediction. However, when we
run through the same models using LIME, decision tree based model yield a 77% accuracy in
prediction, random forest model yield an 89% accuracy score and logistic regression model yield
a 90% accuracy in predicting.
We decided to deploy LIME to interpret this chosen ADS as LIME has an undeniable
benefit that provides local model interpretability as it modifies single data sample by tweaking
the feature values and observes the resulting impact on the output. This aids us in pinpointing the
important features that contributes greater to the prediction of both placement and salary offered
to the students. With LIME, we are able to indicate that for secondary education percentage that
is greater than 61.00, higher secondary education percentage that is greater than 65.58, degree
percentage that is greater than 69.00, MBA percentage that is greater than 58.31, have working
experience and is a male will have higher probability being placed during campus recruitment.
Below is the snippet for each models for the LIME prediction:

### Decision tree based model:

![image](https://user-images.githubusercontent.com/120950225/209727854-ef38e1ae-aa9c-4753-ab52-da9596312978.png)

### Random forest model:

![image](https://user-images.githubusercontent.com/120950225/209727890-e9bf1484-f766-4bd6-b7dd-6b11ed0cf542.png)

### Logistic regression model:

![image](https://user-images.githubusercontent.com/120950225/209728011-02fc7b25-b8fa-4b54-b03a-cb8449084fe1.png)

According to the simulation ran on LIME, we determined that the gender, employability
test percentage, work experience, postgraduate MBA specialization and postgraduate MBA
percentage have great influence on determining the amount of salary offered to a student when
being placed in the process of campus recruitment. Comparing to the results obtained from the
ADS run of the author himself, the results obtained from the LIME simulation is consistent.
Below is the snippet for LIME prediction:

![image](https://user-images.githubusercontent.com/120950225/209728039-1945e3c2-70c0-479b-acfe-f8dbc367ddd9.png)

## Summary
All in all, we summarize that this data is appropriate for the ADS that is deployed by the author.
Most of the predictions that is determined by this ADS is accurate to predict placement of
students’ in Jain University. Since, gender’s feature importance in determining the students’
placement is rather high, it is to our concern that the dataset that is utilized in this ADS does not
statistical parity as the number of male students are higher than the number of female students.
We also identify that group without working experience is unprivileged as they are less likely to
be placed compare to group with working experience. In addition, since this dataset is a rather
small dataset that is obtain from a professor in Jain University, we conclude that this ADS is not
suitable to be deployed in public sector or industry as the accuracy may vary when the number of
sample in the dataset increases. Although the predictions made by the ADS is accurate with the
input dataset, it is rather unstable to deploy for large scale usage. We recommend future
researchers to diversify the data during data collection as the data collected are unbalance among
all collected categorical features and numerical features.
