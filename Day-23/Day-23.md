# Guide: Explore Automated Machine Learning in Azure ML  

This guide walks you through using Azure Machine Learning's automated machine learning feature to train, evaluate, deploy, and test a machine learning model.  

## Prerequisites  
- An active Azure subscription with administrative access.  
- Download the dataset from [this link](https://aka.ms/bike-rentals) to your local machine.  

---

## Step 1: Create an Azure Machine Learning Workspace  

1. **Sign into the Azure Portal**  
   Go to [Azure Portal](https://portal.azure.com) and log in using your Microsoft credentials.  

2. **Create a Machine Learning Resource**  
   - Select **+ Create a resource** and search for `Machine Learning`. 

     ![image](https://github.com/user-attachments/assets/d523832f-127c-4d51-adf0-02cc0f40c223)
 
   - Configure the following settings:  
     - **Subscription**: Select your Azure subscription.  
     - **Resource group**: Create or select an existing resource group.  
     - **Name**: Provide a unique name for your workspace.  
     - **Region**: Select the closest geographical region.  
     - **Storage account, Key vault, Application insights**: Note that these will be created automatically.  
   - Click **Review + create** and then **Create**.  
   - Wait for the resource to deploy, then navigate to the workspace.  
     
     ![image](https://github.com/user-attachments/assets/6726bf3e-2e79-4103-a3e5-17677ab2659b)


3. **Launch Azure Machine Learning Studio**  
   - In the deployed workspace, click **Launch studio** or visit [Azure Machine Learning Studio](https://ml.azure.com).  
     
     ![image](https://github.com/user-attachments/assets/83eb6495-81d7-42d2-b855-3a760e677d03)

   - Close any displayed messages.  

---

## Step 2: Enable Preview Features  

1. In Azure Machine Learning Studio, click on the **Manage preview features** button (🕫).  
2. Enable the following feature:  
   - **Guided experience for submitting training jobs with serverless compute**  

---

## Step 3: Use Automated Machine Learning to Train a Model  

### **Create and Configure a Dataset**  

1. **Navigate to Automated ML**  
   - In Azure Machine Learning Studio, go to the **Automated ML** page under the **Authoring** section.  

2. **Create a New Automated ML Job**  
   - Click **+ New Automated ML Job** and configure the following settings:

     ![image](https://github.com/user-attachments/assets/2ed8a83b-f013-4700-8a95-e13a27eac023)


#### Basic Settings  
   - **Job name**: `bike-automl`  
   - **Experiment name**: `bike-rental`  
   - **Description**: `Automated machine learning for bike rental prediction`  

#### Task Type & Data  
   - **Task type**: Regression  
   - **Dataset**: Create a new dataset using the following steps:  

### Create Dataset from Local File  
   1. Select **From local files**.  
   2. Upload the dataset file (`bike-rentals.csv`) that you downloaded earlier.  
      > **Download your dataset using the URL**
      ```https://aka.ms/bike-rentals```
   3. Configure the dataset with these settings:  
      - **Name**: `bike-rentals`  
      - **Description**: `Historic bike rental data`  
      - **Type**: Tabular  
      - **File format**: Delimited  
      - **Delimiter**: Comma  
      - **Encoding**: UTF-8  
      - **Column headers**: Only first file has headers  
      - **Skip rows**: None  

   4. Review and confirm the schema. Include all columns except `Path`.  

3. **Task Settings**  
   - **Dataset**: Select the `bike-rentals` dataset.  
   - **Target column**: `Rentals`  
   - **Primary metric**: Normalized root mean squared error  
   - **Allowed models**: Restrict to `RandomForest` and `LightGBM`.  
   - **Limits**:  
     - Max trials: 3  
     - Max concurrent trials: 3  
     - Max nodes: 3  
     - Metric score threshold: `0.85`  
     - Timeout: `15 minutes`  
     - Iteration timeout: `15 minutes`  
   - **Enable early termination**: Checked  

4. **Validation and Test**  
   - Validation type: Train-validation split  
   - Percentage of validation data: 10%  
   - Test dataset: None  

5. **Compute Settings**  
   - **Compute type**: Serverless  
   - **Virtual machine type**: CPU  
   - **Virtual machine tier**: Dedicated  
   - **Virtual machine size**: Standard_DS3_V2  
   - **Number of instances**: 1  

6. **Submit Job**  
   - Click **Submit** to start the training job.  

---

Enjoy building powerful models with **Automated Machine Learning in Azure ML**!   
