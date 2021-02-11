# Azure Model Deployment Project

## Project Overview
The objective of the project is to demonstrate skills in configuring, deploying and consuming a cloud-based machine learning model in Microsoft Azure using AutoML. For the purpose of this project I worked with the Bank Marketing Dataset (https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv). For training the model, I used Azure autoML capability. The best model was identified, deployed and consumed. I also created and published a pipeline using Azure SDK libraries. 

## Architectural Diagram

![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/Architecture%20Diagram%20Project%202.png?raw=false)

## Key Steps

To meet the project objectives the following steps are required with an exception of the first authentication step:

1. Authentication
2. Automated ML Experiment
3. Deploy the best model
4. Enable logging
5. Swagger Documentation
6. Consume model endpoints
7. Create and publish a pipeline

### Step 1. Authentication

Because I used the virtual machines provided in the lab, authentication was already take care off and thus I was not required to do this step.

### Step 2. Create and run the automated machine learning experiment

The very first step performed is to go to Automate ML 'author' section and create an autoML experiment. For the we have to select a dataset. Here the bank marketing dataset is selected.
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/01%20-%20AutoML%20-%20select%20dataset.JPG?raw=false)

Next step in creating an autoML run is to configure the run. Here, I created a new experiment. An experiment name, target column and the compute cluster are entered in their respective fields. A new compute cluster is created by clicking on the 'create a new compute'. Details provided in the next screenshot.
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/02%20-%20create%20new%20experiment.JPG?raw=false)

A new compute cluster is created as shown below. Please note, after creating this compute cluster I modified it again to set the maximum number of nodes to 5. That screenshot is also included.
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/03%20-%20create%20new%20compute%20cluster%20(A).JPG?raw=false)

Compute cluster modified to have 5 maximum nodes.
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/03%20-%20create%20new%20compute%20cluster%20(B).JPG?raw=false)

Compute cluster provided when creating the AutoML run:
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/04%20-%20create%20new%20experiment%20(B).JPG?raw=false)

This screenshot shows the additional configuration done while setting up the autoML run.
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/05%20-%20Additional%20Configuration.JPG?raw=false)

The dataset is now registered:
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/06%20-%20Registered%20dataset.JPG?raw=false)

The autoML run is now complete. The screenshot shows that the VotingEnsemble was the best model with accuracy of 0.91866:
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/07%20-%20Experiment%20is%20complete.JPG?raw=false)

### Step 3. Deploy the model
Go to the models tab of the autoML run and select the topmost model on the list. It is the best model. In this case it is VotingEnsemble:
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/08%20-%20Best%20Model%20is%20VotingEnsemble.JPG?raw=false)
      
The next step is to deploy this model. When deploying, I ensured that the compute type was Azure Compute Instance (ACI) and that the 'enable authentication' flag was checked.
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/09%20-%20Deploy%20the%20model%20%2B%20ACI%20%2B%20enable%20authentication.JPG?raw=false)

The model deployment is successfully triggered.
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/10%20-%20Model%20deployment%20is%20triggered.JPG?raw=false)

Prior to deploying a model the RESTful endpoint and the swagger URI are null.
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/11%20-%20Endpoint%20before%20deployment.JPG?raw=false)

After the deployment, the endpoint status is 'Healthy' and the RESTful endpoint is populated. Also, the Swagger URI are populated with the link to the swagger.json file.
      ![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/12%20-%20Endpoint%20after%20deployment.JPG?raw=false)

### Step 4. Enable Application Insights / Logging

Download the config.json file and save it in the working directory .
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/13%20-%20Download%20config%20file.JPG?raw=false)

Config.json file is in the same working directory (starter_files) as logs.py file
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/14%20-%20Config%20file%20in%20the%20same%20directory.JPG?raw=false)

Logs are running
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/15%20-%20Logs%20are%20running%20(A).JPG?raw=false)

![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/15%20-%20Logs%20are%20running%20(B).JPG?raw=false)

The application insights is enabled and an application insights URL is generated
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/16%20-%20Application%20insights%20enabled.JPG?raw=false)

### Step 5. Swagger documentation

After running the swagger.sh in gitbash, it initiates the swagger-ui container. The localhost will display the swagger-ui container.
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/17%20-%20Swagger%20running%20on%20localhost.JPG?raw=false)

Run the serve.py in git using python command.
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/18%20-%20Logs%20running%20(python%20serve.py).JPG?raw=false)

Swagger is running the deployed model.
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/19%20-%20Swagger%20documentation.JPG?raw=false)

More details on the input payload for executing the real-time machine learning service.
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/20%20-%20More%20swagger%20documentation.JPG?raw=false)

### Step 6. Consume the model enpoints

To consume the model, the endpoint.py file is run in the git bash. The output is displayed below.
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/21%20-%20Endpoint.py%20showing%20result.JPG?raw=false)

### Step 7. Create and publish a pipeline

Create and run a pipeline for the deployed VotingEnsemble model.
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/22%20-%20Pipeline%20is%20running.JPG?raw=false)

Pipeline run is complete.
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/23%20-%20pipeline%20complete%20(A).JPG?raw=false)

Run the Restful endpoint pipeline. It is evident that the run was active and the REST endpoint is populated.
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/24%20-%20Pipeline%20endpoint%20%2B%20Bank%20Marketing%20dataset%20%2B%20status%20is%20active.JPG?raw=false)

The completed run is shown in the screenshot below.
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/23%20-%20Pipeline%20complete%20(B).JPG?raw=false)

The pictorial representation of the RESTful endpoint run is shown below.
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/23%20-%20Run%20complete.JPG?raw=false)

The run shows the VotingEnsemble model accuracy of 0.94795
![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/25%20-%20With%20AutoML%20(accuracy%200.94795).JPG?raw=false)

![alt text](https://github.com/garimasharma4/AzureML-Project2/blob/master/starter_files/screenshots/26%20-%20Final%20screen.JPG?raw=false)

## Screen Recording
Here is the link to the screencast recording: https://drive.google.com/file/d/1Awbl1MwVmkqfXtpu_XRZDo5WQvPddMvl/view

## Future Suggestions
Similar to the previous project, I have the following suggestions for future improvement:
1. The foremost improvement that can be done is the explanatory data analysis (EDA) part. The given dataset can be cleaned to improve the data quality.
2. We can increase the search space for the hyperparameters (include different parameters) and the number of runs.
