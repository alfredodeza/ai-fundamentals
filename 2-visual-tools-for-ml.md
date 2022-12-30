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

## Create a classification model with Azure ML Designer

[Learning Module](https://learn.microsoft.com/training/modules/create-classification-model-azure-machine-learning-designer/?WT.mc_id=academic-0000-alfredodeza)

## Create a clustering model with Azure ML Designer

[Learning Module](https://learn.microsoft.com/training/modules/create-clustering-model-azure-machine-learning-designer/?WT.mc_id=academic-0000-alfredodeza)

