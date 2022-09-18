# Predicting if animal in the shelter would be adopted.
Analysis of data of animals outcomes of the Austin Animal Shelter
## Aim of the investigation: to find out what factors may influence the probability of an animal to leave the shelter to home and build a model that may predict if it leaves the shelter to home or to some other destination.

## Source of data: 
Austin Animal Shelter 
1. [Austin Animal Center Shelter Outcomes](https://data.austintexas.gov/Health-and-Community-Services/Austin-Animal-Center-Outcomes/9t4d-g238)
2. [Austin Animal Center Shelter Intakes](https://data.austintexas.gov/Health-and-Community-Services/Austin-Animal-Center-Intakes/wter-evkm)

## Tasks: 
clean the data;
<br> perform exploratory data analysis;
<br> modify the data to perform logistic regression and KNN-classifier machine learning.

## Questions answered: 
### Animals in what condition and in what age are coming to the shelter?
Dominant amount of animals are coming to the shelter in normal condition, babies up to month are coming in nursing condition too (and this is expected). Some visible part of animals of 2-5 years are coming injured.
<br> The dominant age of coming animals is from a month to 6 months, then 2-5 years and then 1-2 years (so from 0.5 to 5 years is the dominant age of coming animals).

![age_intake](https://user-images.githubusercontent.com/84775580/190916237-ad109a36-45b4-4037-96cb-3b4492765779.png)

### Animals from which sources are coming to the shelter? 
Stray animal adoption - is a not-profit organisation to help animals. 
<br> Owner surrender means that owner of the animal has brought an animal to the shelter.

![count of intakes](https://user-images.githubusercontent.com/84775580/190916259-30adc7d4-3bd0-431a-9205-e342277984aa.png)

### Has pandemic influenced the animals' outcomes? 
Yes, it did, in March, 2020 there is visible drop in the counts of outcome what is back to high by summer 2021.
<br> Also there are observable drops in outtakes in winters in general. So people are more wiilling to adopt in summer.

![pandemic](https://user-images.githubusercontent.com/84775580/190916333-0859d5a8-08c3-41da-9471-c113bd6e5c42.png)

### Is there difference between the outcome types of different types of animals? 
Both cats and dogs are adopted equaly, but cats are twice more transfered than dogs and very little being returned to owner (4.3%) while dogs are equaly transfered or returned to owner (around 23-25%). Also both types are euthanasied equally. Also they have the same rate of RTO-adopt. What is this? Is it return-to-owner adopt? So what is the difference with just Return-to-Owner outcome? 
<br>The highest rates of euthanasia have birds and other animals. All other types of animals besides dogs and cats are equally lost (around 4%), birds are commonly transfered or RTO - aroun 30%, livestock is mostly RTO - close to 50%.

![outcomes types](https://user-images.githubusercontent.com/84775580/190916407-0837863e-6f25-43ca-a314-2b0cf4070eab.png)

### What machine learning models have been used? 

![image](https://user-images.githubusercontent.com/84775580/190917903-bd67e18a-1860-4bf4-95d2-64bbc8dca6e9.png)

Correlation matrix has shown no correlations between variables, so, I decided to logistic regression because I can classify outcomes by 2 types: Adoption&RTO-Adoption (animal went to a human) and all other outcomes which mean that animal didn't find home. 
<br> Clusterization with KNN - also possible as I know the number of clusters.

<br> To build the models I modified data from nominal variables written as words to written with numbers. 

### Logistic regression.
Predictors were: 'Name', 'Intake Type', 'Animal Type','Sex upon Outcome', 'Age (6 fructions)', 'Days in shelter', 'Color'
<br> Accuracy of Logistic regression classifier on training set: 0.74
<br> Accuracy of Logistic regression classifier on test set: 0.74

### KNN-clasifier.
The best accuracy is achived with parameters:
It is model with 9 neighbours with:
* target: animal is adopted (1), animal is not adopted(0)
* features: 'Name', 'Intake Type', 'Animal Type', 'Age (6 fructions)', 'Days in shelter'.
<br> The accuracy is 78%. 

### Results of ML models.
Accuracy of 78% is not high. Although maybe not bad if considered that the data was nominal and the outcome is strongly dependant on chance (humans' preferences, for example).
