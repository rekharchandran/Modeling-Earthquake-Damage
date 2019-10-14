# Modeling-Earthquake-Damage
## Richter's Predictor: Modeling Earthquake Damage

### Overview
Based on aspects of building location and construction, our goal is to predict the level of damage to buildings caused by the 2015 Gorkha earthquake in Nepal.The data mainly consists of information on the buildings' structure and their legal ownership. Each row in the dataset represents a specific building in the region that was hit by Gorkha earthquake.

 How artificial intelligence and predictive analysis can help in faster damage recovery from earthquake

### General Overview of the data

Data collected from DrivenData.org competition website

#### Data Source: https://www.drivendata.org/competitions/57/nepal-earthquake/

Inhouse data was collected through surveys by the Central Bureau of Statistics that work under the National Planning Commission Secretariat of Nepal. It is rumoured that this survey is one of the largest post-disaster datasets ever collected, containing valuable information on earthquake impacts, household conditions, and socio-economic-demographic statistics. 


### Problem description
 Predict the ordinal variable damage_grade, which represents a level of damage to the building that was hit by the earthquake. There are 3 grades of the damage:

1 represents low damage
2 represents a medium amount of damage
3 represents almost complete destruction

### Features
The dataset mainly consists of information on the buildings' structure and their legal ownership. Each row in the dataset represents a specific building in the region that was hit by Gorkha earthquake.

There are 39 columns in this dataset including structual information such as the number of floors (before the earthquake), age of the building, and type of foundation, as well as legal information such as ownership status, building use, and the number of families who live there. Each building is identified by a unique (random) building_id, which you can use as an index.

### Description

##### geo_level_1_id, geo_level_2_id, geo_level_3_id (type: int): 
geographic region in which building exists, from largest (level 1) to most specific sub-region (level 3). Possible values: 
##### level 1: 
0-30, level 2: 0-1427, level 3: 0-12567.
##### count_floors_pre_eq (type: int): 
number of floors in the building before the earthquake.
##### age (type: int): 
age of the building in years.
##### area_percentage (type: int): 
normalized area of the building footprint.
##### height_percentage (type: int): 
normalized height of the building footprint.
##### land_surface_condition (type: categorical): 
surface condition of the land where the building was built. Possible values: n, o, t.
##### foundation_type (type: categorical): 
type of foundation used while building. Possible values: h, i, r, u, w.
##### roof_type (type: categorical): 
type of roof used while building. Possible values: n, q, x.
##### ground_floor_type (type: categorical): 
type of the ground floor. Possible values: f, m, v, x, z.
##### other_floor_type (type: categorical):
type of constructions used in higher than the ground floors (except of roof). Possible values: j, q, s, x.
##### position (type: categorical):
position of the building. Possible values: j, o, s, t.
##### plan_configuration (type: categorical): 
building plan configuration. Possible values: a, c, d, f, m, n, o, q, s, u.
##### has_superstructure_adobe_mud (type: binary): 
flag variable that indicates if the superstructure was made of Adobe/Mud.
##### has_superstructure_mud_mortar_stone (type: binary): 
flag variable that indicates if the superstructure was made of Mud Mortar - Stone.
##### has_superstructure_stone_flag (type: binary): 
flag variable that indicates if the superstructure was made of Stone.
##### has_superstructure_cement_mortar_stone (type: binary): 
flag variable that indicates if the superstructure was made of Cement Mortar - Stone.
##### has_superstructure_mud_mortar_brick (type: binary): 
flag variable that indicates if the superstructure was made of Mud Mortar - Brick.
##### has_superstructure_cement_mortar_brick (type: binary): 
flag variable that indicates if the superstructure was made of Cement Mortar - Brick.
##### has_superstructure_timber (type: binary): 
flag variable that indicates if the superstructure was made of Timber.
###### has_superstructure_bamboo (type: binary): 
flag variable that indicates if the superstructure was made of Bamboo.
##### has_superstructure_rc_non_engineered (type: binary): 
flag variable that indicates if the superstructure was made of non-engineered reinforced concrete.
##### has_superstructure_rc_engineered (type: binary): 
flag variable that indicates if the superstructure was made of engineered reinforced concrete.
##### has_superstructure_other (type: binary): 
flag variable that indicates if the superstructure was made of any other material.
##### legal_ownership_status (type: categorical): 
legal ownership status of the land where building was built. Possible values: a, r, v, w.
##### count_families (type: int): 
number of families that live in the building.
##### has_secondary_use (type: binary): 
flag variable that indicates if the building was used for any secondary purpose.
##### has_secondary_use_agriculture (type: binary): 
flag variable that indicates if the building was used for agricultural purposes.
##### has_secondary_use_hotel (type: binary):
flag variable that indicates if the building was used as a hotel.
##### has_secondary_use_rental (type: binary): 
flag variable that indicates if the building was used for rental purposes.
##### has_secondary_use_institution (type: binary): 
flag variable that indicates if the building was used as a location of any institution.
##### has_secondary_use_school (type: binary):
flag variable that indicates if the building was used as a school.
##### has_secondary_use_industry (type: binary): 
flag variable that indicates if the building was used for industrial purposes.
##### has_secondary_use_health_post (type: binary):
flag variable that indicates if the building was used as a health post.
##### has_secondary_use_gov_office (type: binary): 
flag variable that indicates if the building was used fas a government office.
##### has_secondary_use_use_police (type: binary): 
flag variable that indicates if the building was used as a police station.
has_secondary_use_other (type: binary): flag variable that indicates if the building was secondarily used for other purposes.

### Our Target
We are predicting the level of damage from 1 to 3(Low,Medium,High). The level of damage is an ordinal variable meaning that ordering is important. 
This can be viewd as a classification or Regression Problem


### performance metrics

To measure the performance of our algorithms, we have used the F1 score which balances the precision and recall of a classifier

F1 - performance on a binary classifier

But since we have three possible labels we used a variant called the micro averaged F1 score.

In Python, we can easily calculate this loss using sklearn.metrics.f1_score with the keyword argument average='micro'

### Modelling

Model                         Micro avg./f1 scor
Logistic Regression                 0.59
KNN                                 0.63
Linear SVM                          0.63
Decision Tree                       0.64
Random Forest                       0.72
Catboost                            0.73
Deep Neural Network                 0.57
(Tensorflow)

### Feature Impotrances

No     Featureindex                           Importances

1       geo_level_3_id                            26.67
2       geo_level_2_id                            20.12
3       Age                                         8.8
4       geo_level_2_id                              8.6
5       ground_floor_type_v                         5.20
6       roof_type_x                                 3.8
7       count_floors_pre_eq                         3.23
8       has_super_structure_mud_mortar_stone        3.21
9       foundation_type_i                           3.17
10      height_percentage                           2.71

 ### Conclusion
This modelling proves that seismic damage prediction using Machine Learning models is possible. 
Nevertheless, limitations concerning the prediction accuracy are present.




