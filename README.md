# Parkinson's Disease Prediction

## Purpose

The purpose of this project is to create a model to predict a diagnosis of Parkinson's disease (PD) based on Multidimensionsal 
Voice Program (MDVP) recordings.  PD diagnosis is currently based on two of four clinical observations of an individual along with family history.  These four 
clinical observations include:
* slowness of movement
* shaking or tremor
* stiffness or rigidity of the arms, legs, or trunk, and 
* trouble with balance and/or falling <br/><br/>

It may be possible to include voice recordings when diagnosing PD to support a positive diagnosis.  Sometimes PD can take time to diagnosis in order for symptoms to 
progress to a point that are clearly indicative of PD.  This project looks at the potential to include a voice recording in the diagnosing process. 

## Data

This data was collected my Max Little at the University of Oxford and is housed in the **UCI** Machine Learning Repository.
https://archive.ics.uci.edu/ml/datasets/parkinsons. This data set contains MDVP measurements  on various voice measurements and whether Parkinsons 
Disease was diagnosed. There are 31 people in the study with, 23 of whom were diagnosed with PD, and there are 195 total voice recordings.  

<img width="939" alt="Screen Shot 2022-01-17 at 11 07 33 AM" src="https://user-images.githubusercontent.com/62402303/149812198-85c804af-0cab-4aa4-88c2-5ed94ad2f9de.png">

# Visuals
<img width="559" alt="Screen Shot 2022-01-17 at 11 11 55 AM" src="https://user-images.githubusercontent.com/62402303/149812602-e86dbca3-7b92-410f-b733-ee86e2096132.png">

This visual shows that there is a linear relationship between the two voice measures, PPE and spread1. Also shown on the diagram is whether each point was a positive Parkinson's diagnosis or not. The higher the PPE and spread1, the more likely a positive diagnosis and alternately, the lower PPE and lower spread, the less likely a diagnosis of Parkinson's.

<img width="641" alt="Screen Shot 2022-01-17 at 11 31 06 AM" src="https://user-images.githubusercontent.com/62402303/149814981-afbfd469-60fb-4b56-8b0a-875d5b35ac8a.png">

The visual above shows boxplots for spread2 and PPE.  Univariate analysis shows potential for outliers in some variables but due to the limitation of a small data set and the observation of the potential importance of the outliers in some of the variables for classification purposes, outliers were not removed in final model selection.  

# Model Selection

<img width="536" alt="Screen Shot 2022-01-17 at 11 36 01 AM" src="https://user-images.githubusercontent.com/62402303/149815559-a12d4b93-e17e-415e-8c90-e13a627dccaf.png">

The Light Gradient Boosting Machine (LGBM) Optimized model was chosen as the best model for predicting a diagnosis of Parkinson's Disease from Multi-Dimensional Voice Program (MDVP) data.<br/><br/>
* Overall, averaging the six samples of MDVP data for each individual did not show significant changes to model accuracy. For this reason, those models created from unaveraged data were used during the final model evaluations.
* Although K-Nearest Neighbors (KNN) models had higher testing accuracies, the optimal n_neighbors was equal to one making the model extremely overfit. The results of the overfitting was seen when the KNN Optimized model scored a 77% accuracy when run on additional data that was separate data from which the model was created. KNN also scored the lowest accuracy of all models on additional testing data (77%).
* The LGBM Optimized was chosen over the eXtreme Gradent Boosting Machine (XGBM) Optimized because although their accuracy scores both on the validation model and when run on additional data were the same, the LGBM Optimized predicted fewer false negatives. LGBM Optimized had a 1% chance of predicting false negatives and the XGBM Optimized had a 3.6% chance at predicting a false negative. In predicting Parkinson's Disease, false negatives lead to individuals not getting the correct diagnosis of PD, preventing treatment which is an undesirable outcome.
* The data set used for modeling in this project was small and thus limited the ability to create models with higher accuracies. However, with accuracies on additional data that were in the mid 80% range, the ease and non-invasive nature of collection using MDVP data does show promise in predicting a diagnosis of Parkinson's disease and further analysis is warrented.

Confusion matrix for LGBM Optimized model (false negatives = two)<br/><br/>
<img width="305" alt="Screen Shot 2022-01-17 at 11 37 38 AM" src="https://user-images.githubusercontent.com/62402303/149815818-d708984f-f98f-4875-bb4c-7081c1a74ef9.png">

Confusion matrix for XGBM Optimized model (false negatives = seven)<br/><br/>
<img width="306" alt="Screen Shot 2022-01-17 at 11 39 22 AM" src="https://user-images.githubusercontent.com/62402303/149816011-63bf19e4-aaef-4598-8292-e48711906143.png">

# Recommendations
* The data set used for modeling in this project was small and thus limited the ability to create models with higher accuracies. However, with accuracies on additional data that were in the mid 80% range, the ease and non-invasive nature of collection using MDVP data does show promise in predicting a diagnosis of Parkinson's disease and further analysis is warrented.
* The model accuracy could be improved with additional data including more data from non-PD diagnosed individuals.
* More research could be done regarding modeling MDVP data at various stages in the progression of the disease (time variable) and the likelihood of a PD diagnosis.
* Modeling could be done on MDVP parameters along with clinical symptoms and family history to predict PD.


# Acknowledgments
* 'Exploiting Nonlinear Recurrence and Fractal Scaling Properties for Voice Disorder Detection', Little MA, McSharry PE, Roberts SJ, Costello DAE, Moroz IM. BioMedical Engineering OnLine 2007, 6:23 (26 June 2007) https://archive.ics.uci.edu/ml/datasets/parkinson
* https://raw.githubusercontent.com/pqrst/ParkinsonsDiseaseDataAnalysis/master/parkinsons_updrs.csv
* http://aiish.ac.in/images/pdf/jaiish09.pdf
* https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5434464/
* https://www.hopkinsmedicine.org/health/treatment-tests-and-therapies/how-parkinson-disease-is-diagnosed
* https://www.parkinson.org/Understanding-Parkinsons/Diagnosis

