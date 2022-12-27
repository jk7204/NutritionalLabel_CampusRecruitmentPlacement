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




Furthermore, the boolean feature in the input dataset is the work experience (workex) described
as the table below:

Moreover, the 7 numerical features includes serial number (sl_no), secondary education (10thgrade)
percentage (ssc_p), higher secondary education (12th-grade) percentage (hsc_p),
Categorical Feature Distinct
Count
Distinct Count Details Missing Value
Gender 2 Male (139)
Female (76)
0
SSC_B 2 Central (116)
Others (99)
0
HSC_B 2 Central (131)
Others (84)
0
HSC_S 3 Commerce (113)
Science (91)
Arts (11)
0
Degree_T 3 Commerce & Management (145)
Science & Technology (59)
Others (11)
0
Specialisation 2 Marketing & Finance (120)
Marketing & Human Resources (95)
0
Status 2 Placed (148)
Not Placed (67)
0
Boolean Feature Distinct Count Distinct Count Description Missing Value
WorkEx 2 No (141)
Yes (74)
0
undergraduate degree percentage (degree_p), employability test percentage (etest_p),
postgraduate MBA percentage (mba_p) and salary offered by corporate (salary). Below is a table
of description by numerical features listed as above:
The author also conducted a pairwise correlation between features. From the correlation
matrix, values obtained will lie between 0 and 1, where 0 indicates no correlation and 1 indicates
strong correlation between features. The correlation between features are displayed in heatmaps:
Numerical
Feature
Minimum Maximum Mean Median Standard
Deviation
Missing
Value
SL_NO 1 215 108 108 62.1 0
SSC_P 40.9 89.4 67.3 87 10.8 0
HSC_P 37 97.7 66.3 65 10.9 0
Degree_P 50 91 66.4 66 7.34 0
Etest_P 50 98 72.1 71 13.2 0
MBA_P 51.2 77.9 62.3 62 5.82 0
Salary 200000 940000 289000 265000 93100 67
The output obtained from executing this automated decision system according to the
category of of output are class labels. The output of this automated decision system reports
features that affect placement from campus recruitment as well as salaries that are offered by the
corporation to the students that were offered placement for the students studying at Jain
University.
