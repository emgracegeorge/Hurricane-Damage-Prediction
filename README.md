# Introduction

This project assesses the viability including social vulnerability data in existing methods to predict hurricane damage levels. Accurately predicting hurricane damage risk of a given area is essential for human safety and can be useful for insurance assessments. Machine learning provides an opportunity for this to be done quickly and accurately, to update residents in the event of an approaching storm.

Two models were trained and evaluated: one with only physical data and one with both physical and social vulnerablility data. The results show marginal improvement with the inclusion of social vulnerability, but more tuning or refining of the data is still required.

# Data

This project used two datasets: the first containing building, geographical information, and a damage rating and the second from the CDC/ATSDR Social Vulnerability Index (https://www.atsdr.cdc.gov/placeandhealth/svi/data_documentation_download.html) containing social vulnerability data. 

The first dataset contains the following features from hurricanes Michael (2018), Laura (2020), Harvey (2017), and Irma (2017):
damage_rating: a 0-3 rating given to a building after a hurricane
design_exceeded_7-16: the difference between peak gust values and wind speed design code in a given zip code
age
roof_shape_1: primary roof shape of the building
dist_to_coast_m
density_100m
density_500m
surge_depth_ft

From the SOVI dataset, RPL_THEMES is the feature that was chosen. This is an overall social vulnerability number given to a certain zip code from sub-themes on socioeconomic status, household characteristics, racial and ethnic minority status, and housing and transportation type. The overall theme number was shown to provide the highest accuracy result when compared to any of the sub-themes.

# Methods

The Random Forest Model was used for both test cases (with social vulnerability data and without). The effectiveness of each model was evaluated through a classification report and confusion matrix.
