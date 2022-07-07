# CASA0006_Zicheng_Blackspot

## 0622 Update
1. Conducted a space syntax analysis on the Camden road network
2. Added the space syntax indicators to the RF classifier. For the RF classifier that involves all the junctions, the accuracy score have increased to 72% (compared with 65~68% accuracy of the RF model without space syntax indicators)

The space syntax indicators included are Normalised Angular Choice (NACH) and Normalised Angular Integration (NAIN). The former is an improved betweenness centrality for road network, and the latter is an improved closeness centrality. The indicators are initially calculated based on road segments. Then mean values are calculated and assigned to the connected junctions.

The updated notebook is '0622_Update.ipynb'.

## 0624 Comments

1. Created a folder of drafts that includes the draft template (**Draft_junction_blackspot_v1.docx**).
2. For Zicheng: please start the writing of the Methods and Case study section. Please also review more papers for this topic.


## 0707 Update
1. Have Given up the idea of smoothing street View features using other environmental features.
A series of attempts have been made to explore the association between street view and other environmental features, including: 

* (A) Constructing correlation matrices and simple regression model with street view features and other environmental features.
Result: There is only poor correlation tested. The R2 score of regression model is around 0.2-0.3 between building(street view) and other variables.

* (B) Apply different combinations of independnet variables (use space syntax measures, street view features and POI independently, and two or three of them together) in the RF models，and check the importance scores of them.
Result: Space syntax measures often show a higher importance score than street view features. The accuracy score of RF model using only space syntax measures is higher than that of model using only street view features.  
According to the results above, it could not be a good idea to only focus on the performance of street view features.

2. Use SMOTE method to oversample the minor classification in the dataset.
A basic finding this week is that, fewer the junction types, better the model performance. My RF model in the original report has three junction classification (by accident count), and the model shows poor performance in classifying junctions with more accidents(recall below 0.5). With SMOTE method, the overall accuracy of RF model has risen to 0.85 and the recall of minority can be increased to 0.9+

3.Reclassify junctions with number and severity of accidents
 **class 0**:  accident count = 0  **class 1**:  slight count >0  **class 2**:  serious count >2 and fatal count >0 


