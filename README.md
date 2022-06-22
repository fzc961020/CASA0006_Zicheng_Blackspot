### CASA0006_Zicheng_Blackspot

#### 0622 Update
Hi Huanfa, I have done a space syntax analysis on the Camden road network, and added the relevant results to the RF classifier. For the second classifier (for all the junctions), the accuracy score have raised to 72% from 65%.

The indicators I selected are Normalised Angular Choice(NACH) and Normalised Angular Integration(NAIN). The former is an improved betweeness centrality for road network, and the latter is an improved closeness centrality. The indicators are intitally calculated based on road segments. Then mean values are calculated and assigned to the connected junctions.

I have added two extra sections to the original notebook to show the analysis resultes and uploaded the notebook as '0622_Update.ipynb'.


