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

## CLUSTERING

- First the sampling rate of the audio, which was 22050 was found. Next the hip length was set to 2205 so that the amplitude was extracted every tenth of a second. 
- Finally, all the values were saved as a dataframe and downloaded. 

## FEATURE SELECTION
- In feature selection the generations were set to 100, where only the best set of individuals moved on from each generation. 
- The fitness function, which indicates how close the algorithm is to finding the solution, was printed at every step. 
- The closer the generation, the smaller the value of the fitness function. 
- Finally, the best 12 features were selected. 
- The value of the fitness function was plotted across the number of generations or iterations and although the initial value of the fitness function started close to 0.25, the final value became 0.002.

## REPOSITORY STRUCTURE AND USAGE

- The final step to classification is the classifier, SVM. 
- The twelve features that were selected by the  genetic algorithm were passed to the SVM along with their labels. 
- The data was scaled and the  algorithm was executed after setting the appropriate parameters to their correct values, and the training set score of 95.23 and a testing set score of 92.31 was obtained. 

## PAPER

This diagram shows the input - output flow through the different modules in the classifier.


