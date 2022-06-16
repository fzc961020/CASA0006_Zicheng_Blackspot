# Comments on Zicheng's CASA0006 work

Huanfa Chen

Last update: 2022-06-14

1. Contribution needs to be clarified and more references are needed. It seems this paper is quite similar to Tanprasert, T. et al. (2020). Need to clarify the contribution and a more thorough literature review is needed.

2. The classification of traffic accident

| **Severity**      | **Definition**                                               |
| ----------------- | ------------------------------------------------------------ |
| Fatal  accident   | An  accident in which at least one person is killed; other casualties (if any)  may have serious or slightly injuries. |
| Serious  accident | One  in which at least one person is seriously injured but no person is killed. |
| Slight  accident  | One  in which at least one person is slightly injured but no person is killed or  seriously injured. |


3. The classification of junctions (three classes, depending on the number of accidents in the buffer of the junction)

   1. **references??**
   2. **the severity of the accidents are not considered in this classification? Why?**
   
   
4. There are two classifications of junctions. The second attempt is more reasonable than the first one.

In the first attempt, the classifier is trained based on the accident count, street view and POI info of only juncitons with accidents around. 

The junctions are reclassified as three types:'0' -- with only 1 accident, '1' -- with 2 accidents, '2'-- with 3 or more accidents. 

**INPUT VARIABLE**: on this basis, 8 street view feature proportions, 6 POI counts and the longitude and latitude info are selected as the independent variables. 



**Second attempt** (incorporating junctions with no accidents) (It looks like classification is better than the first one)

To increase the accuracy of model, another random forest classifier is trained based on all the road juncitons in Camden. The difference of the model lies on that juncitons are reclassified as :'0' -- with 0 accident, '1' -- with 1 or 2 accidents, '2'-- with 3 or more accidents. Junctions with no accidents are joined as a new class. The seleciton of independent variables keeps the same.

 