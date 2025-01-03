# Azure Custom Question Answering and Bot Creation Guide

This guide will walk you through the process of creating a custom question-answering knowledge base and deploying it as a bot using Azure services.

---

## **Step 1: Create a Custom Question Answering Knowledge Base**

### **1. Open the Azure Portal**
1. Navigate to the [Azure Portal](https://portal.azure.com).
2. Sign in using your Microsoft account.

### **2. Create a Language Service Resource**
1. Click the **＋Create a resource** button.

   ![image](https://github.com/user-attachments/assets/3049e99d-3547-4895-90a6-e1771e033f5f)

2. Search for **Language service** and select it.
3. Click **Create** and configure with the following:

   ![image](https://github.com/user-attachments/assets/32d2faaa-208c-45a9-b1ee-89bfbfb309d9)

   - **Default Features**: Keep default.
   - **Custom Features**: Select **Custom question answering**.

     ![image](https://github.com/user-attachments/assets/0b3a2876-436d-4ea1-9afb-86cfc23bdabe)


4. On the **Create Language** page, provide the following:
   - **Subscription**: Your Azure subscription.
   - **Resource group**: Create a new one or use an existing one.
   - **Name**: A unique name for the Language resource.
   - **Pricing tier**: `S (1K Calls per minute)`.
   - **Azure search region**: Any available location.
   - **Azure search pricing tier**: `Free F (3 Indexes)` (or `Standard S (50 Indexes)` if unavailable).

5. Check the **Responsible AI Notice** box.
6. Click **Review + Create**, then **Create**.
7. Wait for deployment to complete.

---

## **Step 2: Access Language Studio**

### **1. Open Language Studio**
1. In a new tab, go to [Language Studio](https://language.azure.com).
2. Sign in with your Microsoft account.

### **2. Select Your Language Resource**
1. If prompted, select:
   - **Azure directory**: Your subscription’s directory.
   - **Azure subscription**: Your subscription.
   - **Language resource**: The one you just created.

     ![image](https://github.com/user-attachments/assets/d6eff3a4-48c0-4f06-834b-60cff6b7694f)

2. If not prompted:
   - Click the **⚙ Settings** button at the top.
   - Go to the **Resources** tab, select your resource, and click **Switch resource**.

---

## **Step 3: Create a New Question Answering Project**

### **1. Start a New Project**
1. In Language Studio, click **Create new** and select **Custom question answering**.

   ![image](https://github.com/user-attachments/assets/f5b97c8f-fbe8-4a0e-814d-64f363552c41)


### **2. Configure Project Settings**
1. On the **Choose language setting for resource** page, select:
   - **I want to select the language when I create a project in this resource**.
2. On the **Enter basic information** page, configure:
   - **Language resource**: Your resource.
   - **Azure search resource**: Your Azure search resource.
   - **Name**: `MargiesTravel`.
   - **Description**: A simple knowledge base.
   - **Source language**: English.
   - **Default answer when no answer is returned**: `No answer found`.

3. Click **Create project**.

---

## **Step 4: Add Content to the Knowledge Base**

### **1. Add a Source**
1. On the **Manage sources** page, click **＋Add source**.
2. Select **URLs**.
3. In the **Add URLs** box:
   - **URL name**: `MargiesKB`.
   - **URL**: `https://raw.githubusercontent.com/MicrosoftLearning/AI-900-AIFundamentals/main/data/qna/margies_faq.docx`.
   - **Classify file structure**: Auto-detect.
     
     ![image](https://github.com/user-attachments/assets/63e01d66-0f31-446e-b670-fb5545bf9ab2)

4. Click **Add all**.

### **2. Edit the Knowledge Base**
1. Click **Edit knowledge base** in the left panel.
2. Add a question pair:
   - **Questions**: `Hello`.
   - **Answer**: `Hello`.
   - **Source**: Editorial.
   - Add an alternate phrase: `Hi`.

     ![image](https://github.com/user-attachments/assets/4d5db2f2-be6a-4711-9fbc-f1911c1f79fa)

3. Save changes.

---

## **Step 5: Train and Test the Knowledge Base**

### **1. Train the Knowledge Base**
1. Click **Test** at the top of the page.

   ![image](https://github.com/user-attachments/assets/32348fa6-21d4-404c-9262-e652caa3d86f)


### **2. Test Responses**
1. Enter:
   - `Hi` → Response: `Hello`.
   - `I want to book a flight` → An appropriate FAQ response.
   - `How can I cancel a reservation?` → Matching FAQ response.

2. Test short and verbose answer options using the **Display short answer** checkbox.

   ![image](https://github.com/user-attachments/assets/6cb83bee-67a5-438e-9fd9-d02a46358090)


3. Close the test pane when finished.

---

## **Step 6: Create a Bot**

### **1. Deploy the Knowledge Base**
1. Click **Deploy knowledge base** in Language Studio.
2. Click **Deploy**, confirm, and wait for deployment.

   ![image](https://github.com/user-attachments/assets/2e3e5388-7c04-4587-8c87-121d9a745ce5)


### **2. Create a Web App Bot**
1. Click **Create a bot** to open the Azure portal.
2. Configure bot settings:
   - **Subscription**: Your subscription.
   - **Resource group**: Same as the Language resource.
   - **Bot handle**: A unique name.
   - **Pricing tier**: Free (F0).
   - **Language Resource Key**: Copy from the Language resource.
   - **Language project name**: `MargiesTravel`.
   - **App Service Plan**: Create new.
3. Click **Review + Create** and wait for deployment.

---

## **Step 7: Test the Bot**

1. In the Azure portal, go to your bot resource.
   
   ![image](https://github.com/user-attachments/assets/0c5d7c71-298a-4318-9f67-3e3db070f5de)

2. Click **Test in Web Chat** in the left-hand menu.
3. Test questions like:
   - `I need to cancel my hotel` → Correct FAQ response.
   - Other FAQs from the knowledge base.
     
     ![image](https://github.com/user-attachments/assets/36e2636b-0b56-4599-988c-beb8e9a91088)

     

---

## **Learn More**
- [Question Answering Documentation](https://learn.microsoft.com/en-us/azure/cognitive-services/language-service/question-answering/)
- [Azure Bot Service Documentation](https://learn.microsoft.com/en-us/azure/bot-service/)

---

Enjoy building intelligent FAQ bots with Azure!
