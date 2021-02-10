# Azure Model Deployment Project

## Project Overview
The objective of the project is to demonstrate skills in configuring, deploying and consuming a cloud-based machine learning model in Microsoft Azure using AutoML. For the purpose of this project I worked with the Bank Marketing Dataset (https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv).

## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. An architectural diagram is an image that helps visualize the flow of operations from start to finish. In this case, it has to be related to the completed project, with its various stages that are critical to the overall flow. For example, one stage for managing models could be "using Automated ML to determine the best model".

![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/Architecture%20Diagram%20Project%202.png?raw=false)

## Key Steps
*TODO*: Write a short discription of the key steps. Remeber to include all the screenshots required to demonstrate key steps.

To meet the project objectives the following steps are required with an exception of the first authentication step. Because I used the virtual machines provided in the lab, authentication was already take care off and thus I was not required to do this step:

1. Authentication
2. Automated ML Experiment
3. Deploy the best model
4. Enable logging
5. Swagger Documentation
6. Consume model endpoints
7. Create and publish a pipeline

Below are the detailed description of the steps taken to complete this project:

The very first step performed is to go to Automate ML 'author' section and create an autoML experiment. For the we have to select a dataset. Here the bank marketing dataset is selected.

![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/01%20-%20AutoML%20-%20select%20dataset.JPG?raw=false)


Next step in creating an autoML run is to configure the run. Here, I created a new experiment. An experiment name, target column and the compute cluster are entered in their respective fields. A new compute cluster is created by clicking on the 'create a new compute'. Details provided in the next screenshot.

![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/02%20-%20create%20new%20experiment.JPG?raw=false)


A new compute cluster is created as shown below. Please note, after creating this compute cluster I modified it again to set the maximum number of nodes to 5. That screenshot is included.

![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/03%20-%20create%20new%20compute%20cluster%20(A).JPG?raw=false)

Compute cluster modified to have 5 maximum nodes.

![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/03%20-%20create%20new%20compute%20cluster%20(B).JPG?raw=false)

Compute cluster provided when creating the AutoML run:

![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/04%20-%20create%20new%20experiment%20(B).JPG?raw=false)

This screenshot shows the additional configuration done while setting up the autoML run.

![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/05%20-%20Additional%20Configuration.JPG?raw=false)


![alt text](?raw=false)
![alt text](?raw=false)
![alt text](?raw=false)
![alt text](?raw=false)
![alt text](?raw=false)
![alt text](?raw=false)
![alt text](?raw=false)
![alt text](?raw=false)
![alt text](?raw=false)
![alt text](?raw=false)
![alt text](?raw=false)

## Screen Recording
Here is the link to the screencast recording: https://drive.google.com/file/d/1Awbl1MwVmkqfXtpu_XRZDo5WQvPddMvl/view

## Standout Suggestions
Similar to the previous project, I have the following suggestions for future improvement:
1. The foremost improvement that can be done is the explanatory data analysis (EDA) part. The given dataset can be cleaned to improve the data quality.
2. We can increase the search space for the hyperparameters (include different parameters) and the number of runs.
