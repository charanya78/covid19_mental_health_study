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

Once the survey data had been converted into a majority of numerical values, we decided to split the data by age groups, which is a fundamental factor in determining anxiety levels, and conduct individual analysis on each of the age groups. 
- In the next step, the spectrogram and its corresponding amplitude-time graph is plotted. 
- EDA is performed and it has to be noted that there is a clear peak that can be seen right at the time of the fall which is absent for all non fall audios
- On looking at the spectrogram, the brightest color is at the same time, and when it is compared to the amplitude-time graph above it shows that the amplitude or loudness has drastically increased at around the same time.
- After this, the MFCC is plotted for the same. Here the lower amplitudes are indicated by blue and the higher ones by shades of red and it is clear that there are different points of high and low amplitudes for each feature. 
- The next graph is an actual plot of the features using their amplitudes as the y-axis and time as the x-axis. 
- It is very difficult to get meaningful information about the maximum amplitude overall by dissecting the preexisting audio. 
- But nevertheless, it is important to observe that amplitude is a very important feature for classification.

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

![alt text](https://github.com/charanya78/fall_detection_audios/blob/main/diagrams/repo.PNG)

This diagram shows the input - output flow through the different modules in the classifier.


