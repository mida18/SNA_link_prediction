## Social Network Analysis - link prediction

## Task description
> This assignment is to predict whether a node pair (node1, node2) has hidden relation (i.e., hidden edge).   
> There are about 20,000 edges provided for reconstructing the social network and the training dataset. 
> (This is a directed network, so each node pair represents a directed edge. E.g., (361, 981) represents an edge from node 361 to node 981.)  
> The social network has about 5,000 hidden edges. These are the relationships that need to be predicted.
<br>

## Make features
> - Collect missing edges to obtain negative samples to provide training for binary classifiers.  
> - Train/validation/test cutting(Make sure that the ratio of positive and negative samples is equal when cutting to avoid training difficulties caused by sample imbalance).

|      Data        | Number for training |  Number for testing  |      All data      |  
|:----------------:|:-------------------:|:--------------------:|:------------------:|  
| validation data  |      #  22,910      |       #   5,728      |     #  28,638      |   
| train data       |      #  28,638      |       #  12,276      |     #  40,914      |  
| all data         |      #  40,914      |       #  10,231      |     #  51,145      |       

> - Extract features
>> * Jaccard’s_coefficient  
>> * Adamic / Adar_Index  
>> * Shortest path  
>> * Follow back  
>> * Page Rank  
>> * Katz centrality
>> * Hits ( hubs / authorities )
>> * The number of followers, followees and intersections of node 1 and node 2
>> * Cosine similarity between Node2vec vectors  
<br>

## Visualize
#### Feature importance
> Use RandomForestClassifier to complete model training to obtain feature importance scores as a reference for feature selection.  
![image](https://github.com/mida18/SNA_link_prediction/blob/main/Fig/feature_importance_RF.png)  
<br>
#### Discriminative abilities of features
> Observe the discriminative power that each feature can contribute to model prediction.  
![image](https://github.com/mida18/SNA_link_prediction/blob/main/Fig/discriminative_abilities_of_features.png)  
<br>
#### Dimension reduction
> PCA is used for dimensionality reduction, so that the sample distribution can be visualized to provide a reference for the selection of the classifier.  
> The red is the sample with link=1, and the blue is the sample with link=0.  
> As can be seen from the figure, this data set may belong to a non-linear separable state, so we can consider using a kernel-based classifier when choosing a model.
![image](https://github.com/mida18/SNA_link_prediction/blob/main/Fig/2D_pca.png)  
<br>

## Model training
> The training process is divided into three parts: validation, test and predict.  
> Models  
>> * RandomForest  
>> * kernel SVM  
> The final score on the Public Leaderboard is approximately between 89% and 91%.  
<br>

## For more detailed information, please refer to [report][https://github.com/mida18/SNA_link_prediction/blob/main/HW1_report.pdf]
