# Training and Testing a Linear Regression Model in Azure Machine Learning Studio

## Introduction
This README provides a step-by-step guide for setting up and running a linear regression model in **Azure Machine Learning Studio** using **Automated ML**. Follow along to create a resource group, set up a Machine Learning workspace, prepare data, and configure an Automated ML job to train and evaluate a model. This guide is beginner-friendly and designed to make the process smooth and straightforward.

---

## Prerequisites

- An Azure account (free or paid)
- Azure Machine Learning Studio access

---

## Steps

### 1. Create a Resource Group

1. Go to the [Azure portal](https://portal.azure.com).
2. In the search bar, type **Resource Groups** and select it.
3. Click **Create**.

![image](https://github.com/user-attachments/assets/de4a2a7d-39ab-48f8-bc9b-4fd2ba82ddcf)

4. Choose your **Subscription**.
5. Enter a **Resource Group Name**.
6. Select a **Region**.

![image](https://github.com/user-attachments/assets/e764d828-32f9-4cb3-a9ed-7b9336ba2cd8)

7. Click **Review + Create** and then **Create**.

![image](https://github.com/user-attachments/assets/a4744d48-efd9-4d35-a030-350ba9358c6f)


---

### 2. Create an Azure Machine Learning Workspace

1. In the Azure portal, go to **All Services** from the menu.

![image](https://github.com/user-attachments/assets/bc8196d1-5aff-4b1c-a057-ffb59de1c8ae)

2. Search for **Machine Learning** and select **Azure Machine Learning**.

![image](https://github.com/user-attachments/assets/3b4c51c9-56e4-4408-8ce1-efda14081aee)

3. Click **Create** and then select **New Workspace**.

![image](https://github.com/user-attachments/assets/c63cfa4c-5c89-4d6b-9e44-8f4449d43e03)

4. Choose the **Resource Group** you created in the previous step.
5. Enter a **Workspace Name**.
6. Select your **Region**.

![image](https://github.com/user-attachments/assets/47665e2a-33f4-4577-b566-e569645a144c)

7. Click **Review + Create**, then **Create**.

![image](https://github.com/user-attachments/assets/b73d931f-9982-4553-808f-43eee3f897ea)


---

### 3. Access Azure Machine Learning Studio

1. Once the workspace is deployed, click **go to resource**.
2. Click **Launch Studio** to open **Azure Machine Learning Studio**.

![image](https://github.com/user-attachments/assets/852b037c-fef3-4395-9552-53ad4118dede)



---

### 4. Create a Data Asset

To add data for model training:

1. In Machine Learning Studio, click **New** > **Data Asset**.

![image](https://github.com/user-attachments/assets/4da0590b-cebe-47b0-bea3-abe09754006c)

2. Enter a **Name** for your data asset and set **Type** to **Tabular**.
3. Click **Next**.
4. Choose **From Web Files** and paste the raw CSV URL (ensure the URL ends with `.csv`).[Sample dataset](https://raw.githubusercontent.com/paiml/wine-ratings/refs/heads/main/wine-ratings.csv)

![image](https://github.com/user-attachments/assets/1f687912-d7a2-4a8e-a373-936a37ad759d)

![image](https://github.com/user-attachments/assets/f777b7e8-1045-4a09-ade1-00a17a49a273)

5. Click **Next** twice.
6. Toggle off any unwanted columns.
7. Click **Next**, review the details, and then click **Create**.

---

### 5. Start Automated Machine Learning (ML) Job

To initiate an Automated ML job for training and testing:

1. In Machine Learning Studio, go to **Automated ML** from the menu.

![image](https://github.com/user-attachments/assets/7307ea6a-353d-4c75-ab76-fd7839bcdbf3)

2. Click **New Automated ML Job**.

![image](https://github.com/user-attachments/assets/731cf8ea-a41d-47a5-acca-a6f0666f6374)

3. Enter the **Job Name** and select an **Experiment Name** (Description is optional).
4. Click **Next**.

#### Job Configurations

1. Enter the **Target Column** for your model.
2. Set **Validation Type** to **Automatic**.
3. Set **Test Data** to **Train-Test Split**.

#### Compute Configuration

1. Select **Compute Type** as **Compute Cluster**.

![image](https://github.com/user-attachments/assets/3e3a09fe-585a-46c6-9ce1-1c1769c48c24)

2. Choose **CPU** or **GPU**, then select the **Location** and **Subscription**.

![image](https://github.com/user-attachments/assets/58c9fc31-7210-49b7-9ee1-2f03c702abe9)

3. Enter a **Compute Name**.
4. Enable **SSH access** if needed.
5. Click **Create**.

#### Final Step

1. Click **Next** to review and confirm settings.
2. Click **Submit the training job**.

![image](https://github.com/user-attachments/assets/f75a1778-473d-416a-8238-2d4f8e2b8c2d)


---

### 6. Review Training Results

Once the training is complete, you can view:
- **Model performance metrics**
- **Data visualizations**
- **Graphs and detailed performance insights**

![image](https://github.com/user-attachments/assets/13f799ff-13ee-416f-bb75-3dffb76814dc)

![image](https://github.com/user-attachments/assets/e6469d3f-9c08-4633-a83b-329ee3e630df)

![image](https://github.com/user-attachments/assets/92fc2fdb-965a-4f7a-973a-75a6b098f6ad)

![image](https://github.com/user-attachments/assets/a456b25a-5e05-4865-b086-1033c23072cf)

![image](https://github.com/user-attachments/assets/8b953d90-94cb-45bf-8a9b-0a9e2927331c)



These metrics help you understand how well the model performed and provide insights for further tuning or deployment.

## Demo video
Click here for demo video [Training and Testing a Linear Regression Model in Azure Machine Learning Studio](https://www.linkedin.com/posts/reya-josephine-a871a827b_azureml-machinelearning-datascience-activity-7259242935752286209-qa8m?utm_source=share&utm_medium=member_desktop)

---

## Conclusion

This guide covers the essential steps to create, train, and evaluate a linear regression model using Azure Machine Learning Studio’s Automated ML feature. With this setup, you have a foundation for developing and testing models at scale. For more advanced configurations, explore the additional features within Azure ML Studio.

---

Happy Training!
