# Hypoxia_Classifier

## N.B ##

The following is a project I conducted with my colleagues (tagged in the repo) as part of our university course's AI Lab course. For this project, we were tasked with building the best possible classifier for identifying hypoxic cells. We worked with several datasets. However, as we are not able to share the data due to an NDA, for simplicity we will just illustrate our work with one dataset which we well refer to in the code as df_2. 

At some point, you may notice we started working with a dataset called df_2_norm. This is because, although we pre-processsed the data (in order to illustrate the steps one would need to take to obtain the normalized dataset), we were also provided this normalized, pre-processed dataset. 

Finally, as we are unable to share the data, we will skip the conclusion in the report (we ended up with a very accurate classifier). 

## Introduction ##
<p>Hypoxia, a state of reduced oxygen in the tumour environment, is known to promote cancer progression and resistance to treatment. Thus, it is imperative to be able to identify hypoxic cells and their genetic markers, to implement targeted treatments. The goal of this project is to identify patterns and biomarkers linked to hypoxic cells and build a classifier that can identify whether a cell is hypoxic or normal.</p>

<p>Our first goal will be to pre-process the datasets, making sure that we have a high-quality, consistent data set that can be used to train a model. Next, we will conduct exploratory data analysis, to give us a better understanding of the data we are working with. After this, we will use unsupervised learning techniques (PCA and clustering) to uncover patterns and correlations between the hypoxic cells and the normal cells. Finally, we will train models on the data to build a robust classifier able to differentiate between normal and hypoxic cells.</p>

## Data Collection & Pre-Processing ##

<p>In this study, we analyzed four datasets. Each dataset underwent thorough preprocessing to ensure data quality. To understand the data distribution, we used violin plots which revealed significant skewness. Applying a log2 transformation helped reduce this skewness and stabilize variance.</p>

## Exploratory Data Analysis (EDA) ##
<p>We conducted exploratory data analysis to delve into the structure and content of the datasets. This included checking the dimensions, data types, and value distributions. Correlation analysis was essential in identifying patterns and redundancies within the data. Using hierarchical clustering and elbow plots, we determined the optimal number of clusters, which confirmed the presence of distinct groups within each dataset.</p>

## Dimensionality Reduction ##
<p>To handle the high dimensionality of the gene expression data, we employed Principal Component Analysis (PCA). This technique reduced the number of features while retaining most of the variance. We selected the number of principal components based on explained variance and elbow plots, ensuring that the reduced datasets were still representative.</p>

## Model Training and Evaluation ##
<p>We trained three types of models: Logistic Regression, XGBoost classifiers, and an MLP. Logistic Regression models were optimized using GridSearchCV to find the best regularization parameters. XGBoost models were trained with specific hyperparameters to maximize performance. We evaluated the models using accuracy.</p>

<p>We developed an MLP model for each dataset using PyTorch. After splitting the datasets into training and testing sets (while maintaining class balance), we defined an MLP architecture with multiple hidden layers, ReLU activation, and dropout for regularization. We trained the models using the Adam optimizer and monitored their performance through accuracy, precision, and recall.</p>



