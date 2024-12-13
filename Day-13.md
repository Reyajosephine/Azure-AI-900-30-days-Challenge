# Azure Machine Learning Designer - Classification with Diabetes Dataset

This project demonstrates classification using Azure Machine Learning Designer, utilizing the **Diabetes dataset**. Follow the steps below to set up the environment, load the dataset, normalize the data, and create the classification pipeline.

## Prerequisites

- An [Azure account](https://azure.microsoft.com/free/) with an active subscription.
- Administrative access to the subscription.

---

## Step 1: Create an Azure Machine Learning Workspace

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **+ Create a resource**, search for **Machine Learning**, and create a new Azure Machine Learning resource using the following settings:
   
   ![image](https://github.com/user-attachments/assets/563d30fe-bcb1-444d-9190-fa4cc648e6d0)

   ![image](https://github.com/user-attachments/assets/09e7e37e-5154-447c-92da-56c875b7ea77)


   - **Subscription**: Your Azure subscription.
   - **Resource group**: Create or select an existing resource group.
   - **Workspace name**: A unique name for your workspace.
   - **Region**: The closest geographical region.
   - **Storage account, Key vault, Application insights**: Use default settings.
   - **Container registry**: None (auto-created during the first deployment).
3. Click **Review + create**, then **Create**.
4. Once created, navigate to the workspace and select **Launch studio** (or go to [Azure ML Studio](https://ml.azure.com) and sign in).
![image](https://github.com/user-attachments/assets/08125847-7966-4d76-923d-26fe9391b9e9)


---

## Step 2: Create a Compute Cluster

1. In Azure ML Studio, go to **Manage > Compute > Compute clusters**.
2. Click **+ New** and configure the cluster:
   - **Location**: Same as your workspace.
   - **Virtual machine size**: `Standard_DS11_v2`.
   - **Compute name**: A unique name for the cluster.
   - **Minimum nodes**: 0
   - **Maximum nodes**: 1
   - **Idle seconds before scale down**: 120
3. Select **Create** and wait for the cluster to initialize.

---

## Step 3: Create a Dataset

### Option 1: Using a Local File

1. In Azure ML Studio, go to **Assets > Data > + Create**.
2. Configure the dataset:
   - **Name**: `diabetes-data`.
   - **Dataset type**: Tabular.
   - **Data source**: Local files.
   - **Upload file**: Browse and upload your local file containing the Diabetes dataset (e.g., `diabetes.csv`).
   - **File format**: Delimited, **Delimiter**: Comma.
   - **Encoding**: UTF-8.
   - **Column headers**: Only first file has headers.
   - **Skip rows**: None.
3. Click **Create**, then explore the dataset to ensure it contains columns like `Pregnancies`, `Glucose`, `BloodPressure`, `Insulin`, `BMI`, `Age`, and `Outcome`.

### Option 2: Using a Web File

1. In Azure ML Studio, go to **Assets > Data > + Create**.
2. Configure the dataset:
   - **Name**: `diabetes-data`.
   - **Dataset type**: Tabular.
   - **Data source**: Web files.
   - **Web URL**: Provide the URL of your dataset (e.g., `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-azure-ml.es-es/4042fb24ff900f05e9d57aea61b9773fb98df8da/Labs/10/test-data/diabetes-test.csv`).
   - **File format**: Delimited, **Delimiter**: Comma.
   - **Encoding**: UTF-8.
   - **Column headers**: Only first file has headers.
   - **Skip rows**: None.
3. Click **Create**, then explore the dataset to ensure it contains columns like `Pregnancies`, `Glucose`, `BloodPressure`, `Insulin`, `BMI`, `Age`, and `Outcome`.

> **Note:** You can download the dataset from this [link](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-azure-ml.es-es/4042fb24ff900f05e9d57aea61b9773fb98df8da/Labs/10/test-data/diabetes-test.csv).

---

## Step 3: Build the Pipeline

1. In Azure ML Studio, go to **Authoring > Designer > + New pipeline**.
2. Rename the pipeline to **Diabetes Classification**.
3. Click on **Data** on the top left and find your dataset (`diabetes-data`) using the search bar.
4. Drag the dataset onto the canvas.

### Add Data Transformations

1.**Normalize**:
   - Search for **Normalize Data** in the components pane and drag it onto the canvas.
   - Connect the dataset to the **Normalize Data** module.
   - Configure the normalization parameters:(**Right click on the component**)
     - **Edit Columns**:
       - **Columns to transform**: Select **Column names** from dropdown and then enter the column name **Diabetes**.

>**Note**:The variables are case sensitive. Ensure the entered name is correct.

   - Connect the output of **Normalize Data** to the subsequent modules in the pipeline.

2. **Split Data**:
   - Click on components on the top left and search for **Split Data**.
   - Drag the **Split Data** module onto the canvas.
   - Right click on the component and change the fraction of row to **0.7**.
   - Connect the dataset to the **Split Data** module.

3. **Train Model**:
   - Click on components on the top left and search for **Train Model**.
   - Drag the **Train Model** module onto the canvas.
   - Right click train model and then **Edit columns**.
   - Enter the name **Diabetic**.
   - Connect the training output of the **Split Data** module to the dataset input of the **Train Model** module.

4. **Two-Class Logistic Regression**:
   - Click on components on the top left and search for **Two-Class Logistic Regression**.
   - Drag the **Two-Class Logistic Regression** module onto the canvas.
   - Connect the **Two-Class Logistic Regression** module to the **Train Model** module.

5. **Score Model**:
   - Click on components on the top left and search for **Score Model**.
   - Drag the **Score Model** module onto the canvas.
   - Connect the testing output of the **Split Data** module to the second input of the **Score Model** module.
   - Connect the output of the **Train Model** module to the first input of the **Score Model** module.

6. **Evaluate Model**:
   - Click on components on the top left and search for **Evaluate Model**.
   - Drag the **Evaluate Model** module onto the canvas.
   - Connect the output of the **Score Model** module to the **Evaluate Model** module.

### Pipeline Overview

Refer to the image for connections:

![Screenshot 2024-12-13 185527](https://github.com/user-attachments/assets/6a0b23b0-88e9-49f6-aae2-c651e28ca749)



---

## Step 6: Run the Pipeline

1. Select **Configure & Submit**.
2. Configure the pipeline job:
   - **Experiment name**: `diabetes-classification`.
   - **Compute type**: Select your compute cluster.
3. Click **Review + Submit** and wait for the pipeline to complete.
4. Monitor the job status in **Assets > Jobs**.

---

## Step 7: View Evaluation Results

1. Once the pipeline job is completed, go to **Assets > Jobs**.
2. Click on the completed job to open the details.
3. In the job details, you'll see a list of all the modules involved in the pipeline.
4. **Right-click** on the **Evaluate Model** module.
5. Select **Preview Data** > **Evaluation Results** to view the results of the model evaluation.
6. You will see metrics like accuracy, precision, recall, and the confusion matrix.
   
![image](https://github.com/user-attachments/assets/75e04d99-dfca-40ae-b548-2852d066214f)


---

Now you have the evaluation results from your classification pipeline! Let me know if you need further assistance in interpreting the results or tweaking the pipeline.

## Additional Resources
- Click here for demo video [Azure Machine Learning Designer - Classification with Diabetes Dataset](https://www.linkedin.com/posts/reya-josephine-a871a827b_azuremachinelearning-machinelearning-datascience-activity-7273407897621995520-Qx0v?utm_source=share&utm_medium=member_desktop)
