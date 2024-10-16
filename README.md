# Introduction

This project assesses the viability of including social vulnerability data in existing methods topredict hurricane damage levels.

The paper titled A case study and parametric analysis of predicting hurricane-induced building damage using data-driven machine learning approach by Steven Klepac, Arthriya Subgranon, and Maitane Olabarrieta at the University of Florida has been used as a guideline for thisproject. Their approach was to combine building, hazard, and geospatial data from HurricanesHarvey, Irma, Michael, and Laura to evaluate the effectiveness of various machine learningmodels to predict hurricane damage. Their methods were replicated in this project and theresults were compared to the effects of adding social vulnerability data to the training data.

Analysis of both methods shows only marginal improvements when social vulnerability data isincluded in the training data. Further tuning of the model and different data inputs are stillrequired to improve the prediction method in a meaningful way

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

The final dataset is not uploaded to Github to protect the intellectual property of the original researchers.

# Methods

A classification and confusion report were both used to evaluate the model. The model including social vulnerability data (labeled as “Results With Sovi”) shows a 0.01 point increase in accuracy from 0.72 to 0.73. The f-1 score in classes 0 and 3 improve by 0.02 points both, while it remains the same in class 1. These changes may indicate that the inclusion of social vulnerability data helps make more accurate predictions, but the gains are small.
	
One reason this may be is because of the scale between the two datasets. In the base study, the input data is at the level of a building. The social vulnerability data is at the level of a census tract, which can contain hundreds of buildings. This study may indicate that to continue to improve these models, granular data at the level of the building is necessary. 
