# Azure Machine Learning Designer - Clustering with Seeds Dataset

This project demonstrates clustering using Azure Machine Learning Designer, utilizing the **Seeds dataset**. Follow the steps below to set up the environment, load the dataset, and create the clustering pipeline.

## Prerequisites

- An [Azure account](https://azure.microsoft.com/free/) with an active subscription.
- Administrative access to the subscription.

---

## Step 1: Create an Azure Machine Learning Workspace

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **+ Create a resource**, search for **Machine Learning**, and create a new Azure Machine Learning resource using the following settings:
   - **Subscription**: Your Azure subscription.
   - **Resource group**: Create or select an existing resource group.
   - **Workspace name**: A unique name for your workspace.
   - **Region**: The closest geographical region.
   - **Storage account, Key vault, Application insights**: Use default settings.
   - **Container registry**: None (auto-created during the first deployment).
3. Click **Review + create**, then **Create**.
4. Once created, navigate to the workspace and select **Launch studio** (or go to [Azure ML Studio](https://ml.azure.com) and sign in).

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

1. In Azure ML Studio, go to **Assets > Data > + Create**.
2. Configure the dataset:
   - **Name**: `seeds-data`
   - **Dataset type**: Tabular
   - **Data source**: Web Files or local files
   - **Web URL**: `https://raw.githubusercontent.com/MicrosoftDocs/ml-basics/master/data/seeds.csv` (or the URL of your dataset)
   - **File format**: Delimited, **Delimiter**: Comma
   - **Encoding**: UTF-8
   - **Column headers**: Only first file has headers
   - **Skip rows**: None
3. Click **Create**, then explore the dataset to ensure it contains columns like `Area`, `Perimeter`, `Compactness`, `Length`, `Width`, and `AsymmetryCoefficient`.

---

## Step 4: Build the Pipeline

1. In Azure ML Studio, go to **Authoring > Designer > + New pipeline**.
2. Rename the pipeline to **Train Seeds Clustering**.
3. Click on **Data** on the top left and find your dataset using the search bar.
3. Drag the dataset (`seeds-data`) onto the canvas.

   ![image](https://github.com/user-attachments/assets/981a21fc-157c-4d63-ad99-b17536760426)


### Add Data Transformations

1. **Normalize Data**: 
   - Click on components on the top left and serach for **Normalize Data**.
   - Drag the **Normalize Data** module onto the canvas.
     
     ![image](https://github.com/user-attachments/assets/0107253f-d4e1-46af-a7fd-f430b64e5047)

   - Right-click to go to **Edit Columns** and exclude the `species` column.
   - Save and connect the dataset output to the **Normalize Data** module.

2. **Split Data**: 
   - Click on components on the top left and serach for **Split Data**.
   - Drag the **Split Data** module onto the canvas and connect it to the normalized data.
   - Configure the split ratio (e.g., 70% training, 30% testing).

3. **Train Clustering Model**:
   - Click on components on the top left and serach for **Train Clustering Model**.
   - Search for **Train Clustering Model** and drag it onto the canvas.
   - Connect the **Split Data** output to the **Train Clustering Model** dataset input.
   - Right-click on the model and select all columns to train the clustering model.

4. **K-Means Clustering**: 
   - Click on components on the top left and serach for **K-Means Clustering**.
   - Drag the **K-Means Clustering** module onto the canvas and connect the **Train Clustering Model** to it.
   - Configure the model (e.g., select the number of clusters).

5. **Assign Data to Clusters**: 
   - Click on components on the top left and serach for **Assign Data to Clusters**.
   - Search for **Assign Data to Clusters** and connect it to the **Train Clustering Model** output.
   - Connect the second split dataset (`ResultDataset2`) to the **Assign Data to Clusters** module.

6. **Evaluate Model**: 
   - Click on components on the top left and serach for **Evaluate Model**.
   - Drag the **Evaluate Model** module to the canvas and connect the output of **Assign Data to Clusters** to it.

### Refer the image for connections
![Screenshot 2024-12-13 025439](https://github.com/user-attachments/assets/02eb10f1-6b5b-4dad-b21f-8b1039a1ac89)


---

## Step 5: Run the Pipeline

1. Select **Configure & Submit**.
2. Configure the pipeline job:
   - **Experiment name**: `mslearn-seeds-training`
   - **Compute type**: Select your compute cluster.
3. Click **Review + Submit** and wait for the pipeline to complete.
4. Monitor the job status in **Assets > Jobs**.

---

### View Evaluation Results

1. Once the pipeline job is completed, go to **Assets > Jobs**.
2. Click on the completed job to open the details.
3. In the job details, you'll see a list of all the modules involved in the pipeline.
4. **Right-click** on the **Evaluate Model** module.
5. Select **Preview Data** > **Evaluation Results** to view the results of the model evaluation.
6. You will see various metrics like accuracy, confusion matrix, and other relevant results depending on the evaluation configuration.

![image](https://github.com/user-attachments/assets/cafd5214-3c7c-47c2-9f0b-c783fadcc5c7)


---

Now you have the evaluation results from your clustering pipeline! Let me know if you need further assistance in interpreting the results or tweaking the pipeline.
