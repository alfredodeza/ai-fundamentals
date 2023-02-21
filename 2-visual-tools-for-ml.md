# Explore Visual Tools for ML

[Learning Path](https://learn.microsoft.com/training/paths/create-no-code-predictive-models-azure-machine-learning/?WT.mc_id=academic-0000-alfredodeza)

## Use Automated ML in Azure ML Studio

[Learning Module](https://learn.microsoft.com/training/modules/use-automated-machine-learning/?WT.mc_id=academic-0000-alfredodeza)

Definition: A way to predict unknown values with a model using math.

Types:

**Supervised**
Requires a dataset with known labels

- Regression: Predicts a value like price
- Classification:  Provides a binary (yes/no, 1/0) value

**Unsupervised**
No known labels in the dataset

- Clustering: Create labels based on grouping items with similar information

### Azure ML Studio

Definition: An Azure service that automates common ML tasks like training, deploying. Provides specialized cloud-compute to scale workloads

Offers a portal to interact with its features

### Azure ML Workspace

Definition: A requirement to use Azure ML Studio. Allows to manage data, compute resources, code, models.

### Azure ML Compute

Definition: Provides different compute resources types to work with ML

Compute types offered:

- **Compute instances**: A workstation-like compute to work with models and data
- **Compute Clusters**: Scalable VM clusters, on-demand workloads
- **Inference Clusters**: For deploying ML models and provide predictions
- **Attached Compute**: Links to existing compute resources in Azure

### Azure Automated ML (AutoML)

Definition: Automatically tries different algorithms to train a model allowing you to choose which model is best

* Easier for beginners (no extensive Data Science knowledge needed)
* Operations are called _jobs_

Process:

1. *Prepare data*: Identify features, clean, transform data.
1. *Train model*: Split data (train and validation) and then train the model using the _training_ data set
1. *Evaluate performance*: Compare results to known labels
1. *Deploy*: Use the model as an application like a service


*Prepare data*
Data for model training is called a dataset. You can create datasets in Azure

*Train model*
AutoML supports supervised ML models. It has to use known labels. Supervised training includes: Classification, Regression, and Time Series Forecasting

*Evaluate performance*

Happens after the "best" model is generated with the _exit criteria_. Use the **Residual Histogram** to show frequency of residual value ranges, and **Predicted vs. True** for correlatiton of values.


*Deploy*

Use Azure Container Instance (ACI) or Azure Kubernetes Service (AKS) cluster. AKS is recommended for production.

## Create a Regression model with Azure ML Designer

[Learning Module](https://learn.microsoft.com/training/modules/create-regression-model-azure-machine-learning-designer/?WT.mc_id=academic-0000-alfredodeza)

### Regression ML scenarios

Definition: Predicts a numeric result or outcome from variables (a.k.a features). E.g. A PC with N GB of RAM and X type of CPU processor can get a price prediction.

Type of ML: Supervised

Training involves both the features and the known values for the label

Examples:

- Predict home prices from house features
- Crop yield in farms from weather and soil quality
- Ad click-through from data from past campaigns

### Azure ML Designer

Definiton: A visual UI with drag-and-drop elements to perform common ML actions like train, test, and deploy ML models.

ML Designer projects are known as pipelines

### Azure ML Pipelines

Definition: Steps to organize, manage, and reuse complex workflows across projects and users. It starts with the dataset. Results are stored in  your workspace.

### Azure ML Pipeline component

Definition: A single step in an ML pipeline, like a programming function (building bloc)

### Azure ML Datasets

Definition: Register data assets in Azure from local files, datastores, web files, or Open Datasets.

### Azure ML Jobs

Definition: A task for a compute target with tracking for runs and workflows. All runs are recorded and can be viewed in the UI.

### Steps for regression

1. Prepare data: Cleaning, pre-processing
1. Train model: Data split in training and validation sets. Training happens with the training dataset. Validation is for testing performance
1. Evaluate: Check predictions against known labels
1. Deploy: Get the model into a server for real-time (live) inference pipeline

### Model Training with Azure ML Designer

| Step | Dataset |
| - | - |
| Type of task (Linear Regression)| |
| Train Model | Split data with training dataset |
| Score Model | Split data with validation dataset |

### Performance Evaluation

- Mean Absolute Error (MAE): Average of predicted and true values
- Root Mean Squared Error (RMSE): Square root of the difference of predicted and true values
- Relative Squared Error (RSE): A value between 0 and 1 from the square of the difference between predicted and true values
- Relative Absolute Error (RAE): A value between 0 and 1 from the absolute differences between predicted and true values
- Coefficient of Determination (R2): Variance predicted between predicted and true values. Closer to 1 means better model performance


### Deploy a prediction service

You must convert your training pipeline into a real-time inference pipeline. The process removes training components and adds a web service to handle requests.

After pipeline creation:

- Deploy it as an endpoint, wait for it to get in a healthy state
- Test it after deployment with sample data in JSON format
- Use credentials to consume the endpoint using authentication

## Create a classification model with Azure ML Designer

[Learning Module](https://learn.microsoft.com/training/modules/create-classification-model-azure-machine-learning-designer/?WT.mc_id=academic-0000-alfredodeza)

### Classification ML scenarios

Definition: Classification can predict a category (or class) for an item. Applies to binary and multi-class scenarios.

Type of ML: Supervised

Training also involves features and known values for the label.

Examples:

- Predict if a patient will become sick given clinical data
- Predict text sentiment (positive, neutral, negative)

### Steps for classification

1. Prepare data: Cleaning, pre-processing
1. Train model: Data split in training and validation sets. Training happens with the training dataset. Validation is for testing performance
1. Evaluate: Check predictions against known labels
1. Deploy: Get the model into a server for real-time (live) inference pipeline

### Confusion Matrix

Helps visualize true positives (both 1's) true negatives (both 0's) and false positives and negatives. Binary classification predicts one of two values.

| 	     | Actual 1 | Actual 0 |
| - | - | - |
|Predicted 1 | 869 | 377 |
|Predicted 0 | 400 | 2377 |

Metrics:

- **Accuracy**: Ratio of correct predictions (true positives + true negatives)
- **Precision**: Fraction of cases that are true positives
- **Recall**: True positives divided by the number of true positives plus flase negatives
- **F1 Score**: Overall metric from combining precision and recall

### ROC curve and AUC Metric

ROC definition: Plotting the True Positive Rate against the False Positive Rate for every threshold value between 0 and 1.

AUC definition: Is the Area Under the Curve. For a ROC plot, the highes the area the better the model.

## Create a clustering model with Azure ML Designer

[Learning Module](https://learn.microsoft.com/training/modules/create-clustering-model-azure-machine-learning-designer/?WT.mc_id=academic-0000-alfredodeza)


### Clustering ML scenarios

Definition: Groups similar items into clusters based on their features.

Type of ML: Unsupervised

Examples:

- Grouping of wines given their flavor characteristics
- Grouping of dishes given their ingredients and preparation type


### Training and Steps for clustering

1. Prepare data: Cleaning, pre-processing
1. Train model: Data split in training and validation sets. Training happens with the training dataset. Validation is for testing performance
1. Evaluate: Check predictions against known labels
1. Deploy: Get the model into a server for real-time (live) inference pipeline


| Step | Dataset |
| - | - |
| Type of task (K-means clustering)| |
| Train clustering Model | Split data with training dataset |
| Assign data to clusters | Split data with validation dataset |

### Evaluate performance

- Average Distance to Other Center: Average of each point to centroids in all other clusters
- Average Distance to Cluster Center: Average from centroid of the cluster
- Number of Points: Total number of points in the cluster
- Maximal Distance to Cluster Center: Maximum distances between each point and the centroid of that point
