# Arnold Mochama Phase 3 Project

## Introduction
In this project, I will be solving a classification problem using the Terry Traffic Stops.

In Terry v. OhioLinks , a landmark Supreme Court case in 1967-8, the court found that a police officer was not in violation of the "unreasonable search and seizure" clause of the Fourth Amendment, even though he stopped and frisked a couple of suspects only because their behavior was suspicious. Thus was born the notion of "reasonable suspicion", according to which an agent of the police may e.g. temporarily detain a person, even in the absence of clearer evidence that would be required for full-blown arrests etc. Terry Stops are stops made of suspicious drivers.

I will build a classifier to predict whether an arrest was made after a Terry Stop, given information about the presence of weapons, the time of day of the call, etc. This is a binary classification problem.

## Data Pre processing
csv files were loaded from my local machine and read into a pandas dataframe. This was done after the necessary libraries were imported.
The data was then explored using functions and methods such as .describe(), .shape(), .info() and .duplicated()

## Data Cleaning
After exploring the data, the data was cleaned. There were no duplicates values. However there were missing values. The missing values, however only occupied 0.9% of the data 
    
I removed the outliers in the officers age.
Necessary additional columns were added for example, month and year which were derived from the column 'Reported Date'

## Data Visualisations
Various visualisations were made starting with a count plot to show how various columns were distributed in relation to arrested and not arrested.

Afterwards, many distribution plots were created to see the various relations between arrests made and the column features.
Bar graphs were also plotted:

### Findings
Most movies ran for just under 90 min, (but above 80 min) as seen on the histogram.

-Top 5 genres (most genres in the dataset): 1.Documentary 2.Drama 3.Comedy 4.Horror 5.Comedy, Drama

-Top 5 movies with highest Total Gross Income: 1.Marvel's The Avengers 2.Avengers:Age of Ultron 3.Black Panther 4.Harry Potter and Deathly Hallows Part 2 5.Star Wars:The Last Jedi

-Top 5 movies with highest Domestic Gross: 1.Star Wars:The force awakens 2.Black Panther 3.Avengers:Infinity War 4.Jurassic World 5.Marvel's The Avengers

-Top 5 movies with highest Foreign Gross: 1.Harry Potter and Deathly Hallows Part 2 2.Avengers:Age of Ultron 3.Marvel's The Avengers 4.Jurassic World:Fallen kingdom 5.Frozen

## Modeling
                
After finishing our EDA and visualizing most of our features, we will move on to model our data so as to predict whether an arrest will be made. I will be modelling using logistic regression, K-Nearest Neighbors (KNN), Decision Trees and lastly Random Forests. I will then compare the models and choose the best one. I will start by looking at the classes for imbalance, splitting the data into train sets and test sets, performing One Hot Encoding and lastly fitting and training the models.

I have used SMOTE above to balance the classes

To evaluate the performance of the classifiers, I will use confusion matrix. Here I will use True Positives, True Negatives, False Positives and False Negatives. furthermore, I will also use Precision, Recall, Accuracy and F1_score to quantify the performance of classifiers.

Precision measures how precise the predictions are.
precision = Number of true positives / Number of predicted positives

Recall indicates what percentage of the classes we're interested in were actually captured by the model.
Recall = Number of true positives / Number of Actual Total Positives

Accuracy is probably the most intuitive metric.
Accuracy = (Number of true positives + true negatives) / Total observartions

F1 score represents the Harmonic Mean of Precision and Recall.
F1 score = 2(Precision x recall) / (Precision + Recall)

### Conclusion
The conclusion is that Random Forests, at 86.25%, are the most accurate of the four classification models, closely followed by Decision Trees at 80.49%, Logistic Regression at 76.69%, and KNN at 75.52%.

Consequently, 86.25% of the time we can reliably detect whether or not a Terry Stop resulted in an arrest using the Random Forest model. When utilizing the Random Forest model, the precinct and whether or not there was an arrest flag are the most important features.

The following are the top 5 prominet features:

1. An arrest flag was raised (Arrest Flag_Y)
2. No arrest flag was given (Arrest Flag_N)
3. Precinct
4. Year 2018
5. Year 2020

So 86.25% of the time there was an arrest flag raised, there was an arrest made

### Recommendations
-Since this is an important indication of arrests, teach police when it is permissible to make an arrest during a traffic stop and when it is better to wait till later (Arrest flag_Y and Arrest Flag_N)
-For every traffic stop, attempt to record the officer's precinct in order to improve your chances of determining whether an arrest will take place.(Precinct)
-Look into why ages 26 to 35 are arrested most of the time. This can be done by collecting more information about the arrests such as was the driver drunk?

### Next steps
Even though 86.25% accuracy is respectable, it can still be improved and be higher.
Going forward, my goal is to fine-tune our model even more, by changing and adjusting the inputs of the model. A more accurate model might potentially be produced by investigating other kinds of categorization methods, particularly deep learning models

