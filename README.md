# Parkinson's Disease Prediction

## Purpose

The purpose of this project is to create a model to predict a diagnosis of Parkinson's disease (PD) based on Multidimensionsal 
Voice Program (MDVP) recordings.  PD diagnosis is currently based on two of four clinical observations of an individual along with family history.  These four 
clinical observations include:
* slowness of movement
* shaking or tremor
* stiffness or rigidity of the arms, legs, or trunk, and 
* trouble with balance and/or falling
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


# Acknowledgments
* 'Exploiting Nonlinear Recurrence and Fractal Scaling Properties for Voice Disorder Detection', Little MA, McSharry PE, Roberts SJ, Costello DAE, Moroz IM. BioMedical Engineering OnLine 2007, 6:23 (26 June 2007)
* http://aiish.ac.in/images/pdf/jaiish09.pdf
* https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5434464/
* https://www.hopkinsmedicine.org/health/treatment-tests-and-therapies/how-parkinson-disease-is-diagnosed
* https://www.parkinson.org/Understanding-Parkinsons/Diagnosis

