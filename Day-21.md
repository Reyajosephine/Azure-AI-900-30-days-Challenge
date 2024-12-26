# Conversational Language Understanding with Azure Language Service

This guide walks you through exploring Conversational Language Understanding with Azure's Language Service. By the end of this tutorial, you'll build and test a simple home automation model that understands natural language commands.

---

## Prerequisites

- An **Azure subscription** with administrative access.

---

## Steps

### 1. Create a Language Service Resource

1. Sign in to the [Azure Portal](https://portal.azure.com).
2. Click **+ Create a resource**.
3. Search for **Language service** and create it with the following:
   - **Subscription**: Your Azure subscription.
   - **Resource group**: Create or select a unique resource group.
   - **Region**: East US 2.
   - **Name**: Enter a unique name.
   - **Pricing tier**: S (1K Calls per minute).
   - Check the Responsible AI Notice box.
4. Click **Review + Create** and complete the deployment.

---

### 2. Create a Conversational Language Understanding App

1. Go to [Language Studio](https://language.azure.com) and sign in.
2. Select your **Azure directory**, **subscription**, and the **Language resource** you just created.
   - If prompted to switch resources, go to **Settings (⚙)** > **Resources** and select your resource.
3. Click **Create new > Conversational language understanding** and provide the following:
   - **Name**: Unique project name.
   - **Description**: Simple home automation.
   - **Primary Language**: English.
   - Disable multiple languages.

     ![image](https://github.com/user-attachments/assets/2caa2168-16e4-430d-b4bc-f4c613e610ff)

4. Complete the setup and note your project name.

---

### 3. Define Intents, Utterances, and Entities

#### Create the `switch_on` Intent
1. Go to **Schema definition** and click **Add** > Intent.

   ![image](https://github.com/user-attachments/assets/c63edfc8-447a-4f12-aa5f-500f477d6173)

   ![image](https://github.com/user-attachments/assets/ed8ea837-9085-495c-a23c-0b99c41154c2)

   ![image](https://github.com/user-attachments/assets/9aad131a-a3de-4f5f-b7a9-4557f8c479e4)



3. Name the intent `switch_on` and add the following utterances:
   - Turn the light on
   - Switch on the fan
   - Put the fan on
   - Put the light on
   - Switch on the light
   - Turn the fan on
4. Add an **Entity** named `device` (type: List).

   ![image](https://github.com/user-attachments/assets/1b82e216-138c-4bf8-baa8-b8a183253177)

   ![image](https://github.com/user-attachments/assets/e66b6ff8-bd53-46b7-9bd6-46cd5685dc62)


6. Highlight words like "fan" and "light" in the utterances and tag them as `device`.
   
   ![image](https://github.com/user-attachments/assets/593b1709-c57c-462f-bd75-3b6bc500032f)

7. Repeat for all the utterances and click **save changes.**

   ![image](https://github.com/user-attachments/assets/8efd2f4e-f267-4aba-9d6c-b96fed20f9a5)



#### Create the `switch_off` Intent
1. Add another intent named `switch_off`.

   ![image](https://github.com/user-attachments/assets/9b2f81be-9ac8-4256-8df2-797f0afad2aa)

2. Add the following utterances:
   - Turn the light off
   - Switch off the fan
   - Put the fan off
   - Put the light off
   - Switch the fan off
3. Highlight words like "fan" and "light" in the utterances and tag them as `device`.

---

### 4. Train the Model

1. Navigate to **Training jobs** in Language Studio.
2. Start a training job with:
   - **Train a new model**: Select and name your model.
   - **Training mode**: Standard training (free).
   - **Data Splitting**: Automatically split testing data.
3. Click **Train** and wait for it to complete.

---

### 5. Deploy the Model

1. Go to **Deploying a model** in Language Studio.
2. Add a deployment with:
   - **Deployment name**: Unique name.
   - **Trained model**: Assign your trained model.
3. Note your **deployment name**.

### 6. Testing the Model

1. When the model is deployed, click Testing deployments on the left-hand side of the page, and then select your deployed model under Deployment name.

2. Enter the following text, and then select *Run the test*:

*switch the light on*

   ![image](https://github.com/user-attachments/assets/4947a528-5fe9-4354-abfa-d87f1f83d216)


---

### 6. Access Cloud Shell in Azure Portal

#### Launching Cloud Shell
1. Leave the **Language Studio** tab open and switch to the **Azure portal** tab.
2. Click the **[>_] (Cloud Shell)** button at the top-right of the Azure portal (next to the search bar).

   ![image](https://github.com/user-attachments/assets/ef4ff230-7066-4d74-87f7-860f687d15be)

3. If prompted, select **PowerShell** as your preferred shell type.  
4. If you are prompted to create storage for the Cloud Shell:
   - Ensure your subscription is specified.
   - Click **Create storage** and wait for it to finish provisioning.

     ![image](https://github.com/user-attachments/assets/59caf128-da9d-4a09-86fc-0fbe3dc02234)

#### Switching to PowerShell (if necessary)
- If the Cloud Shell opens in **Bash**, use the drop-down menu at the top-left of the Cloud Shell pane to switch to **PowerShell**.

  ![image](https://github.com/user-attachments/assets/034e753a-f499-4013-aa1e-a4f4240c7412)

  ![image](https://github.com/user-attachments/assets/7e6ba5a6-2d1e-4e1f-9d4b-178dd0edfa52)



#### Waiting for Initialization
- Wait for PowerShell to initialize. You should see a prompt like:
  ```powershell
  PS Azure:\>
  ```

---

### 7. Run the Client Application in Cloud Shell

1. Clone the project repository:
   ```bash
   git clone https://github.com/MicrosoftLearning/AI-900-AIFundamentals ai-900
   cd ai-900
   code .
   ```
2. Edit the `understand.ps1` file:

   ![image](https://github.com/user-attachments/assets/8b5cb153-21c7-4c15-bd89-1e95ebdd1169)

   - Replace placeholders with the following:
     - `YOUR_ENDPOINT` → Your model's endpoint.
     - `YOUR_KEY` → Your model's key.
     - `YOUR_PROJECT_NAME` → Your project's name.
     - `YOUR_DEPLOYMENT_NAME` → Your deployment's name.
       
       ![image](https://github.com/user-attachments/assets/dd5d8352-4d37-48ea-875a-02758e2c9aaf)

3. Save the changes and close the editor.
4. Test the app:
   ```bash
   ./understand.ps1 "Turn on the light"
   ./understand.ps1 "Switch the fan off"
   ```
   ![image](https://github.com/user-attachments/assets/2e258e03-fd4e-42a4-83b5-569b7b1729a9)


---

### Learn More

Visit the [Conversational Language Understanding page](https://learn.microsoft.com/en-us/azure/cognitive-services/language-service/conversational-language-understanding/) to explore advanced features. 

--- 
