# How to Deploy the Text-Embedding-3-Large Model in Azure OpenAI Studio

## Overview
Text embedding models are powerful tools that turn text into high-dimensional vectors, capturing the essence of the content in a way that machines can understand. These embeddings are super useful in applications like search, document clustering, and recommendation engines. Azure OpenAI Studio provides a straightforward platform to deploy and manage these models, allowing you to scale intelligent solutions quickly and efficiently.

This guide will walk you through deploying **Text-Embedding-3-Large** in Azure OpenAI Studio with a step-by-step approach.

---

## Step-by-Step Guide

1. **Access Azure OpenAI Studio**
   - Start by logging into the [Azure AI studio Portal](https://oai.azure.com/portal).

2. **Open the Model Catalog**
   - In the Studio, find **Model Catalog** on the menu. This is where all available models are listed.

     ![Screenshot 2024-11-03 235414](https://github.com/user-attachments/assets/5d5178c6-272c-4a34-bb32-f085180882c0)


3. **Select the Text Embedding Model**
   - Look for **text-embedding-3-large** in the catalog and click on it.

     ![image](https://github.com/user-attachments/assets/69f0c6f5-8d1c-46ff-827b-c0a0d13c233f)


4. **Start Deployment**
   - Hit **Deploy** to initiate the model deployment process.

     ![Screenshot 2024-11-03 235535](https://github.com/user-attachments/assets/34419450-adff-4c9f-8c13-2240a2a30b52)


5. **Create a New Deployment Hub**
   - Choose **Create a new hub** when prompted. This sets up a new environment to run your model.

     ![Screenshot 2024-11-03 235600](https://github.com/user-attachments/assets/4f09f1b2-a8bc-4834-80a8-3e90d86f00bb)


6. **Enter Deployment Hub Details**
   - You’ll be asked for a few details:
     - **Hub Name**: Create a unique name for your hub.
     - **Subscription**: Select your Azure subscription.
     - **Resource Group**: Pick an existing resource group, or set up a new one.
     - **Location**: Choose the region where you’d like to deploy.

       ![Screenshot 2024-11-03 235640](https://github.com/user-attachments/assets/4e94deeb-490c-49ac-8158-667d02576862)


7. **Confirm and Launch**
   - Click **Next**, then **Create**.
     
     ![Screenshot 2024-11-03 235713](https://github.com/user-attachments/assets/af77750f-816d-496a-94cf-185dc8b9c734)

     ![Screenshot 2024-11-03 235744](https://github.com/user-attachments/assets/15430a94-0a65-44fa-9e88-f863664aef88)


   - Azure will validate the setup. Wait for confirmation that the deployment is ready to go.

8. **Navigate to Deployments**
   - Once you’re set up, go to **Deployments** from the menu.

     ![Screenshot 2024-11-03 235834](https://github.com/user-attachments/assets/9c320851-65cb-4bf6-96cc-cfb3190ebf17)


9. **Deploy the Model**
   - Click **Deploy Model** at the top left of the screen.

     ![Screenshot 2024-11-03 235914](https://github.com/user-attachments/assets/06528671-da27-49c8-9b15-5cb2c547bf5f)

   - Choose **Deploy Base Model** to work with the core version of the embedding model.

     ![Screenshot 2024-11-03 235938](https://github.com/user-attachments/assets/508b4ad0-67e5-42f9-abbc-b3ee2e698491)


10. **Select and Confirm**
    - Choose **text-embedding-3-large** from the list.

      ![Screenshot 2024-11-04 000005](https://github.com/user-attachments/assets/9ffc314d-8b90-4d5c-a045-fce6acee0d6e)

    - Confirm your selection to start the deployment.

      ![Screenshot 2024-11-04 000033](https://github.com/user-attachments/assets/95f9ec8d-32dd-4234-b343-0b8b8b74acf0)


11. **Check Model Status and Metrics**
    - After deployment, you can monitor your model’s details and performance stats in the Azure OpenAI Studio dashboard.
      
      ![Screenshot 2024-11-04 000103](https://github.com/user-attachments/assets/067538c7-0ea3-4138-a965-4f38f67ae269)

      ![Screenshot 2024-11-04 000150](https://github.com/user-attachments/assets/8d7fa2a5-dbcf-46d3-bf28-3c2078ce6d98)

## Demo video
Click here for demo video [How to Deploy the Text-Embedding-3-Large Model in Azure OpenAI Studio](https://www.linkedin.com/posts/reya-josephine-a871a827b_azureopenai-textembedding-azureai-activity-7258914832442097664-wCmR?utm_source=share&utm_medium=member_desktop)

---

## Final Steps

And there you have it! With **Text-Embedding-3-Large** now deployed in Azure OpenAI Studio, you're ready to start generating embeddings that power smarter search, recommendations, and other text-based AI applications. From here, you can explore additional configurations, track performance, or integrate the model directly into your workflows. Happy deploying!
