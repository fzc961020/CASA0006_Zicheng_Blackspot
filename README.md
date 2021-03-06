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
1. Have given up the idea of smoothing street View features using other environmental features.
A series of attempts have been made to explore the association between street view and other environmental features, including: 

* (A) Constructing correlation matrices and simple regression model with street view features and other environmental features.

Result: There is only poor correlation tested. The R2 score of regression model is around 0.2-0.3 between building(street view) and other variables.

* (B) Apply different combinations of independnet variables (use space syntax measures, street view features and POI independently, and two or three of them together) in the RF models，and check the importance scores of them.

Result: Space syntax measures often show a higher importance score than street view features. The accuracy score of RF model using only space syntax measures is higher than that of model using only street view features.  

According to the results above, it could not be a good idea to only focus on the performance of street view features. There are other features playing a more important role than street view.

2. Use SMOTE method to oversample the minor classification in the dataset.
A basic finding this week is that, fewer the junction types, better the model performance. The RF model in the original report has three junction types (by accident count), and the model shows poor performance in classifying junctions with more accidents(recall below 0.5). With SMOTE method, the overall accuracy of RF model and the recall of minority can be increased significantly.Any suggestion about the use of oversampling methods？

3.Reclassify junctions with number and severity of accidents
 There are four classification methods tested in the updataed notebook
 * Method a. **class 0**:  accident count = 0  **class 1**:  0< accident count <=2  **class 2**:  accident count >2   （The original method, with a potential accuracy socre to 0.72)
* Method b. **class 0**:  accident count = 0  **class 1**:  accident count >0    (Simplify the classification for a higher accuracy socre）
* Method c. **class 0**:  accident count = 0  **class 1**:  0< slight accident <=2  **class 2**:  serious accident >0 or fatal accident >0   (use both accident count and severity for classification)
* Method d. **class 0**:  accident count = 0  **class 1**:  slight accident >3 or serious accident >0 a or fatal accident >0   (use both accident count and severity)

Method c and d are updated threshold methods for junction classification.

4.The selection of hyperparameters and the feature importance analysis
The selection of best RF model and the interpretion of feature imporatance can be critical paper in this paper. However, there seems no stable rank of feature importance as i changes the model's hyperparameters. Besides, I am afraid i haven't found the best hyperparameter combination with the current GridSearchCV settings. Could you provide any suggestions or strategies for model selection and interpretation?


