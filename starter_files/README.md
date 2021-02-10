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

## Screen Recording
Here is the link to the screencast recording: ![alt text](https://drive.google.com/file/d/1Awbl1MwVmkqfXtpu_XRZDo5WQvPddMvl/view?raw=false)

## Standout Suggestions
Similar to the previous project, I have the following suggestions for future improvement:
1. The foremost improvement that can be done is the explanatory data analysis (EDA) part. The given dataset can be cleaned to improve the data quality.
2. We can increase the search space for the hyperparameters (include different parameters) and the number of runs.
