# COVID-19 Mental Health Study

## DESCRIPTION 

The Coronavirus pandemic has caused a large upset to people of all ages and walks of life, as it has led to job loss, school and college closures,  postponement or cancellation of sporting, religious, political, and cultural events, widespread supply shortages exacerbated by panic buying. One of the most pressing concerns during these times, is the mental health of the general population, therefore, this study mainly focuses on the anxiety of people due to the abrupt change in their day to day lifestyle. This project aims to find how the lifestyle of denizens has been affected by the pandemic and correlate these changes with the level of anxiety that people have. To conduct this research, we circulated an online survey to assess the current conditions of the people and their corresponding anxiety levels using a GAD-7 scale.  

## SOFTWARES USED

- Jupyter Notebook 
- Excel
- Google Forms

## LANGUAGE USED

Python

## DEPENDENCIES NEEDED

- scipy

- pandas 

- numpy

- sklearn

- seaborn 

- matplotlib

To install the above mentioned dependencies use:

- pip install scipy
- pip install pandas
- pip install numpy
- pip install sklearn
- pip install seaborn
- pip install matplotlib

## DATA COLLECTION

- The survey was conducted from June 19, 2020 to June 23, 2020, and had a total of 32 questions.
-  To assess the anxiety levels, this survey gathers important information about the respondent, including factual information such as location, age, gender, health issues, and other visceral information based on large stress factors such as “Do you feel like you have wasted your time during the lockdown?” and “Have you felt anxious to go to the hospital?”. 
-  The last seven questions of the survey were based on a standardized scale GAD, or Generalized Anxiety Disorder Scale, which accurately determines anxiety of the person and segregates it into one of the four basic categories, 0 - Minimal Anxiety, 1 - Mild Anxiety, 2 - Moderate Anxiety, 3 - Severe Anxiety. 
-  We garnered a total of 832 responses, from 25 different locations worldwide. 

## EXPLORATORY DATA ANALYSIS

- Once the survey data had been converted into a majority of numerical values, we decided to split the data by age groups, which is a fundamental factor in determining anxiety levels, and conduct individual analysis on each of the age groups. 

#### Less than 18 group

#### Data Analysis using Excel

-	We found 65 number of samples belonging to the age group of less than 18, out of which 43(64.6%) belonged to the female gender and 23(35.3 %) belonged to the male gender.
-	Then, we further split up the data into 4 anxiety groups based on the GAD 7 scale.
-	We conducted further analysis on each anxiety group and analyzed the different questions that could have contributed to a higher anxiety.
-	We took each question and found the number of people who said Yes/Frequently (1) to the question and then calculated the percentage of people who answered 1 to each question in each anxiety group.
-	It was found that as the level of anxiety increases, the percentages also increase for a few questions(Highlighted in green). 
-	Also, it can be observed that for a few questions the percentages of people are higher in the case of moderate and severe anxiety and lower in the cases of 0 and mild anxiety(Highlighted in yellow).

![alt text](https://github.com/charanya78/covid19_mental_health_study/blob/master/diagrams/excel.png)

#### Data Analysis using EDA

We find that the people who answered Yes for the questions 

- Have you ever felt symptoms of COVID?
- Do you have any of the following conditions?	
- Are you stuck somewhere alone without support from friends or family?	
 don't have moderate/severe anxiety which makes it insignificant in its contribution to anxiety.

When we sum up the people who answered 
- Yes/ Frequently for a question and have moderate and severe anxiety
- No/Rarely for a question and have moderate and severe anxiety

We find that if the sum of the latter is greater than the former, it does not contribute significantly to anxiety(1).
There are 9 questions which satisfy the above condition which become trivial in their contribution to anxiety.
For all the questions that were selected as important from the data analysis in Excel,it is found that 3 of the questions:
- Is it difficult to get essentials?
- Is someone from your family in the medical field everyday? 
-	How often do you eat outside food? (per week) 
satisfy the condition mentioned at (1) which makes them less significant in their contribution to anxiety.

The rest of the 9  features have notable correlation with the anxiety of a person.
On plotting several relationship plots, it was found that it is not possible to differentiate features based on gender as almost every feature was applicable for both the genders.
So, gender, too ,becomes an important parameter in its contribution to the anxiety of a person.

We,then, applied a feature selection method- Extra Tree Classifier and to get the top 10 features of importance.When we compare the top 10 features selected by the Extra Tree Classifier and the 10 features selected by careful analysis and observation of the data , 8/10 features overlap.

The important 8 features are:
- During the lockdown have you been doing more household work?
- Do you miss hanging out with people outside of your house?
- Have you or anyone you know have corona virus/recovered from COVID/been tested for COVID?
- Do you have online classes/assignments/assessments/tests?
- Have you felt frustrated by having your activities, major life events or opportunities affected by the virus?
- Do you have children less than 3 years, or elders 65+ at your house?
- Have you ever felt afraid or anxious to go to hospital during this pandemic?
- Has your sleep cycle changed drastically?
- What is your gender?
- Do you feel like you have wasted your time during the lock down or have you ever felt pressured by your peer’s accomplishments during the lockdown?

The analysis performed here are avaiblabe in Analysis/18_Analysis.xlsx (https://github.com/charanya78/covid19_mental_health_study/blob/master/Analysis/18_Analysis.xlsx)

## CLUSTERING

- We took the 23 features and scaled the data frame using Standard Scaler and constructed a dendrogram to work out ways in which samples can be allocated to clusters.
- Upon analyzing the dendrogram we can observe that we draw a horizontal line at y=6,we have 4 clusters formed which is equal to the four anxiety groups we have. 
- On further analysis, it was found that the four clusters consisted of 12,14,17,22 samples each.
- We split up the different anxiety groups amongst each cluster and got the following tabulation:
 
![alt text](https://github.com/charanya78/covid19_mental_health_study/blob/master/diagrams/cluster.png)

- It is clear that Cluster 4 contains all the severe anxiety samples and Cluster 3 contains only mild and 0 anxiety. 
- Clusters 2 and 4 have the greatest percentage of moderate anxiety samples.
- On examining each cluster separately, we found the number of people who answered similarly for each question.
- For example, in the cluster with 12 samples, all the samples belonged to the male gender,and, hence, the percentage of similarity is 100%.
- And,it is also important to note the majority response of each question.
- We tabulated the percentage of similarity and the majority response for each question under each cluster and counted the number of questions which have the majority response to be Yes/Frequently(Highlighted in green).

![alt text](https://github.com/charanya78/covid19_mental_health_study/blob/master/diagrams/cluster_analysis.png)

- In cluster 1 there were 8 questions where the majority response was Yes/Frequently and in cluster 2 there were 4, in cluster 3 there were 7 and cluster 4 there were 9.
- It is interesting to note that, cluster 4 has the highest number of questions with Yes/Frequently as the majority response and cluster 4 also houses all the severe anxiety samples.
- It was also found that for a few questions, the majority response was found to be the same for all the four clusters.
- Those questions have either a majority Yes/ majority No response, in general, which makes its impact minimal in the anxiety of a person(Highlighted in Red).

![alt text](https://github.com/charanya78/covid19_mental_health_study/blob/master/diagrams/cluster2.png)
 
The analysis and code performed here are avaiblabe in 
- Analysis/Cluster_Analysis.xlsx (https://github.com/charanya78/covid19_mental_health_study/blob/master/Analysis/18_Analysis.xlsx)
- Hierarchical_Clustering.ipynb (https://github.com/charanya78/covid19_mental_health_study/blob/main/Hierarchical_Clustering.ipynb)

## PAPER

- The paper was presented at ICRTAC 2020(3rd International Conference on Recent Trends in Advanced Computing) and was published in Springer Lecture Notes in Electric Engineering - https://link.springer.com/chapter/10.1007/978-981-16-6448-9_23

- Jayasimha, A., Jayashanker, P., Charanya, S.K., Krithika, K. (2022). A Study on the Repercussions of the COVID-19 Pandemic in the Mental Health of the Common Public: Machine Learning Approach. Artificial Intelligence and Technologies. Lecture Notes in Electrical Engineering, Springer

