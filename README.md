# Hypoxia_Classifier

## Pre-Introduction ##

The following is a project I conducted with my colleagues @Matteo-03, @markostamenovic
## Introduction ##
<p>Hypoxia, a state of reduced oxygen in the tumour environment, is known to promote cancer progression and resistance to treatment. Thus, it is imperative to be able to identify hypoxic cells and their genetic markers, to implement targeted treatments. The goal of this project is to identify patterns and biomarkers linked to hypoxic cells and build a classifier that can identify whether a cell is hypoxic or normal.</p>

<p>Our first goal will be to pre-process the datasets, making sure that we have a high-quality, consistent data set that can be used to train a model. Next, we will conduct exploratory data analysis, to give us a better understanding of the data we are working with. After this, we will use unsupervised learning techniques (PCA and clustering) to uncover patterns and correlations between the hypoxic cells and the normal cells. Finally, we will train models on the data to build a robust classifier able to differentiate between normal and hypoxic cells.</p>

**N.B.** 
*As the data used for this project is classified, we have used placeholders where specific genetic markers were mentioned (e.g. Feature 1, Feature 2, etc.).*

## Data collection & pre-processing 

<p>In this study, we analyzed four datasets, which, for the purposes of not disclosing private information we will call Dataset_1, Dateset_2, Dataset_3, and Dataset_4. Each dataset underwent thorough preprocessing to ensure data quality. To understand the data distribution, we used violin plots which revealed significant skewness. Applying a log2 transformation helped reduce this skewness and stabilize variance.</p>

<h2>Exploratory Data Analysis (EDA)</h2>
<p>We conducted exploratory data analysis to delve into the structure and content of the datasets. This included checking the dimensions, data types, and value distributions. Correlation analysis was essential in identifying patterns and redundancies within the data. Using hierarchical clustering and elbow plots, we determined the optimal number of clusters, which confirmed the presence of distinct groups within each dataset.</p>

<h2>Dimensionality Reduction</h2>
<p>To handle the high dimensionality of the gene expression data, we employed Principal Component Analysis (PCA). This technique reduced the number of features while retaining most of the variance. We selected the number of principal components based on explained variance and elbow plots, ensuring that the reduced datasets were still representative.</p>

<h2>Model Training and Evaluation</h2>
<p>We trained three types of models: K-means clustering, Logistic Regression, and XGBoost classifiers. For K-means, we identified clusters based on the results of hierarchical clustering. Logistic Regression models were optimized using GridSearchCV to find the best regularization parameters. XGBoost models were trained with specific hyperparameters to maximize performance. We evaluated the models using accuracy.</p>

<h2>Multilayer Perceptron (MLP) Training</h2>
<p>We developed an MLP model for each dataset using PyTorch. After splitting the datasets into training and testing sets (while maintaining class balance), we defined an MLP architecture with multiple hidden layers, ReLU activation, and dropout for regularization. We trained the models using the Adam optimizer and monitored their performance through accuracy, precision, and recall.</p>

<h2>Predictions</h2>
<p>For making predictions on test data, we utilized the trained models. We applied PCA to the test datasets where necessary and used the trained models to generate predictions. The results were saved as CSV files for further analysis.</p>
