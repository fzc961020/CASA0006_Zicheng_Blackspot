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
1. Based on a series of attempts, I have given up the idea of smoothing Street View features using other socio-economic data. My attempts include: 
** (A) Constructing scatterplots, correlation matrices and simple regression model to test the association between streetview features and other social contextual info. ** (B) Apply different combinations of independnet variables (space syntax measures, street view features and POI, singly, or two or three of them) in the regression model and check the importance score of it.
