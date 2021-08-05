# Phase_3_Project
 
**Authors**: Manav Kahlon, Anthony Conte, Sanjit Varma, Ben Bowman
  
## Overview
- [Business Problem](#Business-Problem)
- [Data](#Data)
   - [Well Data](#Well-Data)
- [Methods](#Methods)
- [EDA Results: Notable Features](#EDA-Results-Notable-Features) 
- [Modeling Results](#Modeling-Results)
- [Conclusions](#Conclusions)
- [For More Information](#For-More-Information)
- [Repository Structure](#Repositroy-Structure)
  

## Business Problem

 
## Data

   
    
    
## Methods
  
    
## EDA Results Notable Features
 
 
## Modeling Results
We run five different classifiers and perform a GridSearch on each. Our metrics for selecting the best model are based on the business problem at hand. We are interested in overall model accuracy, but we want to focus on wells that need repair or are non-functional. Therefore we pay close attention to how well the models predict the ‘needs-repair’ and ‘non-functioning’ wells (we are less concerned with false positives since there is less harm in misidentifying a working well than in missing a faulty one). We create a new metric which is the sum of the recalls of ‘needs-repair’ and ‘non-functioning’ wells as a guide for selecting models. Here are the model performances:

![image](https://user-images.githubusercontent.com/82840623/128359296-db6abdb2-7439-474f-9518-51776178d79c.png)


The default Support Vector Classifier does best with our custom metric, identifying nearly 70% of the ‘needs-repair’ wells (in the test data) and 68% of the non-functioning ones (even though, compared to other models, it has a lower overall accuracy due to weaker performance identifying functional wells).

The tuned Random Forest model also does well, predicting 56% of ‘needs-repair’ wells and 76% of the non-functioning wells, making it slightly less predictive than the SVC model. It does have the advantage, however, of higher overall accuracy due to its better predictions of functioning wells.
  
    
## Conclusions
We recommend the SVC model due to its superior ability to identify the two well types that require servicing. We are willing to trade some false positives for this benefit. This recommendation would change, however, if the Government signals that visiting functional wells (when expecting to repair or replace one) is too inefficient and costly. In that case, we would be more concerned with false positives and recommend the Random Forest model.

    
    
## For More Information
Please review our full analysis in [our Jupyter Notebook](./Notebook.ipynb) or our [Presentation](./Presentation.pdf).    
    
## Repositroy Structure
 ```
├── data                                <- Sourced from an external source
├── images                              <- Images that were used in the presentation                                            
├── gitignore                           <- python files to ignore 
├── Notebook.ipynb                      <- The steps taken to acheive our endgoal
├── Presentation.pdf                    <- PDF of our project presentation                        
└── README.md                           <- The README.md

```
