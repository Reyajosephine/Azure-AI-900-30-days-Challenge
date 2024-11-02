# Building a Custom Q 'n' A Chatbot with Language Service in Azure

## Introduction
Azure Language Service enables you to create a custom Q 'n' A chatbot that can intelligently answers user questions based on a knowledge base of information you provide. This chatbot can be integrated across platforms like Microsoft Teams, websites, and more, making it a versatile addition to any service needing quick, automatic responses.

---

## Step-by-Step Guide

### Step 1: Create the Language Resource
1. **Log in to the Azure Portal**: [https://portal.azure.com](https://portal.azure.com)
2. **Create a New Resource**:
   - In the portal dashboard, click on **"Create a resource"**.
   - Search for **"Language resource"** and select it and click **"Create**".

     ![image](https://github.com/user-attachments/assets/423b35c2-7e75-4981-8906-b1c12c08fd84)

     ![image](https://github.com/user-attachments/assets/a0bbb6f3-bb81-4093-be1b-2ea5c3dc1cac)


   - Choose **"Custom Question Answer"** from the options.

     ![image](https://github.com/user-attachments/assets/41981e8c-27c1-4cde-ba0e-70cac2f39990)

   -Click **"Continue to create your resource"**.


3. **Configure the Resource**:
   - **Subscription**: Choose your subscription.
   - **Resource Group**: Select an existing group or create a new one.
     
     ![image](https://github.com/user-attachments/assets/b4ebbdfe-5301-46af-8cf1-5d2b566a3f15)

   - **Region**: Choose the region closest to your target users.
   - **Name**: Enter a unique name for your chatbot.
   - **Pricing Tier**: Select **Free F0** for testing purposes.

     ![image](https://github.com/user-attachments/assets/1adacc95-d895-40fc-addd-586db4538eef)

   - **Acknowledgment**: Tick the checkbox to agree to terms.

     ![image](https://github.com/user-attachments/assets/59b52031-004c-4a6a-a50d-bf13823de0d4)


4. Click **"Review + Create"**, then **"Create"** to deploy the resource.

### Step 2: Retrieve Resource Key
1. Once deployed, **Go to the Resource**.
2. Click on the newly created language resource.

![image](https://github.com/user-attachments/assets/9c0e1bf0-c67a-4937-ba7f-51efb0be2971)

3. Under **Resource Management**, click on **Keys and Endpoint** to view your **Resource Key**.


### Step 3: Set Up in Language Studio
1. In the Language Resource, go to **Overview** and click on **Get Started with Language Studio**.

![image](https://github.com/user-attachments/assets/8212135f-d628-42f3-a6ce-20abc17dc388)

2. **Sign In**: Enter your Azure credentials.
3. **Configure Language Studio**:
   - Choose your **Subscription**.
   - Select your **Language Service resource** from the dropdown.
   - Click **Done**.
   
    ![image](https://github.com/user-attachments/assets/cfc32999-a393-45a3-8d94-8e3c6349fa5e)


### Step 4: Create the Custom QnA Project
1. **Start New Project**: Click on **Create New** > **Custom QnA**.

![image](https://github.com/user-attachments/assets/a614c514-7ff7-4ee4-9dda-6f86d4957a99)

2. **Configure Project**:
   - Select a **Language**.
   - Click **Next**.
   - **Enter Project Name**.
   - **Description** (optional).
   - **Default Answer**: Enter a fallback answer, e.g., "Answer not found".

3. Click **Next** and then **Create Project**.
 
![image](https://github.com/user-attachments/assets/5a918043-1828-4302-84e8-6b0d54405452)


### Step 5: Add Data Sources to the Knowledge Base
1. **Manage Sources**:
   - Once the project is created, go to **Manage Sources**.
   - Click **Add Source** > **Add File**.

    ![image](https://github.com/user-attachments/assets/31c89b84-e883-48c9-b28f-5e0f4951cbfb)

   - Select the relevant file and click **Add All**.

    ![image](https://github.com/user-attachments/assets/0001a688-aca9-469e-abbe-00763094db32)


2. **Edit the Knowledge Base**:
   - Go to **Edit Knowledge Base**.
   - Add and modify QnA pairs as needed.
   - Click **Save Changes**.

    ![image](https://github.com/user-attachments/assets/1481fa89-3692-478b-9001-3aef556d9ce4)


### Step 6: Deploy the Knowledge Base
1. In the Knowledge Base menu, select **Deploy Knowledge Base**.

![image](https://github.com/user-attachments/assets/053e5551-c6bf-4708-afec-0bebfe804c4e)

2. Wait for the deployment to complete.

### Step 7: Create and Configure the Chatbot
1. After deployment, click **Create a Bot**.

![image](https://github.com/user-attachments/assets/20aa0cf6-611d-4c54-874b-b27e00afa780)

2. **Configure Bot Settings**:
   - Fill out the required details.
   - Select **App Service Plan** as **Create New App Service Plan**.

    ![image](https://github.com/user-attachments/assets/0fdaee91-e41f-420f-86bb-79f51cadf025)

   - Enter the **Resource Key**:
     - Go to **Deploy Knowledge Base > Settings Icon (top right) > Resources > View Resource Key**.
      
      ![image](https://github.com/user-attachments/assets/b701d669-c704-4379-b18a-7b87392590d8)

     - Copy and paste this key into the required field.

3. Click **Review + Create** and then **Create**.

### Step 8: Customize Your Bot Profile
1. Go to the **Resource Group** and select your **chatbot**.

![image](https://github.com/user-attachments/assets/61bdf9c3-cae9-4b74-a18b-450affe3cc72)

![image](https://github.com/user-attachments/assets/2fa9a69d-c5b1-4e68-a8d9-db1568a23553)

2. In the bot’s menu, select **Settings** > **Bot Profile**.
3. Customize the bot’s **Name** and **Icon**.

### Step 9: Integrate the Bot with Microsoft Teams
1. Go to **Channels** in the bot’s settings menu.
2. Select **Microsoft Teams**, Tick the checkbox, click **Agree** and then **Apply**.

![image](https://github.com/user-attachments/assets/c9985de1-69cf-4fb5-b5ea-59d38ce9705c)

![image](https://github.com/user-attachments/assets/8a0c9cbd-b88e-4aa7-9e63-57327ad3ee4d)

![image](https://github.com/user-attachments/assets/61ebbff1-72d6-4933-bf12-1b5280691542)

### Step 10: Test Your Bot
1. In the bot's menu, click **Test in Web Chat**.

![image](https://github.com/user-attachments/assets/583e8b3c-4063-4332-bb5e-c08ce0b03ba7)

2. Ask a few questions:
   - If the answer exists in the knowledge base, it will display the response.
   - If not, it will display the default message, **"No answer found"**.

![image](https://github.com/user-attachments/assets/6689319f-a27e-47f3-8055-c443d6303a81)

## Demo video
Click here for Demo video:
[Building a Custom Q 'n' A Chatbot with Language Service in Azure](https://www.linkedin.com/posts/reya-josephine-a871a827b_azure-aichatbot-qnabot-activity-7258549542969630720-npFR?utm_source=share&utm_medium=member_desktop)


---

With this setup, your custom QnA chatbot is now ready to assist users, respond to queries, and provide seamless communication.
