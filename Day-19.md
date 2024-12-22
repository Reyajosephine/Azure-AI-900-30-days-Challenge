# Explore Form Recognition with Azure AI  

Form recognition is an advanced OCR (Optical Character Recognition) technique used to extract information from forms like invoices or receipts, maintaining a semantic understanding of the fields. With Azure's Form Recognizer service, you can extract both text and its structure, enabling automation for tasks like data entry.  

This guide walks through using the Azure Form Recognizer service via a simple command-line application in Azure Cloud Shell.  

## Prerequisites  
- An Azure subscription with administrative access.  

---

## Step 1: Create an Azure AI Services Resource  

1. Sign in to the [Azure portal](https://portal.azure.com).  
2. Click on **+Create a resource**, search for **Azure AI services**, and select **Create**.  
3. Configure the resource with the following settings:  
   - **Subscription**: Your Azure subscription.  
   - **Resource group**: Select or create a unique resource group.  
   - **Region**: Choose any available region.  
   - **Name**: Enter a unique name.  
   - **Pricing tier**: Standard S0.  
   - **Terms**: Check the box to acknowledge the terms.  
4. Click **Review + Create** and wait for deployment to complete.  
5. Once deployed, navigate to the resource, and open the **Keys and Endpoint** page. Copy the **endpoint** and **keys** for later use.  

---

## Step 2: Run Azure Cloud Shell  

1. In the Azure portal, click the **Cloud Shell** button ( [>_] ) at the top of the page.  

   ![image](https://github.com/user-attachments/assets/5b0b58b2-a2d3-41fc-982b-94dda980fe48)


2. If prompted, select **PowerShell** as the shell type.  

   ![image](https://github.com/user-attachments/assets/2fee3b96-9aa7-4c98-8a1c-7e45aefa08d6)

3. If required, create storage for the Cloud Shell and wait for it to initialize.  
4. Confirm the shell type in the top left of the Cloud Shell pane is set to **PowerShell**. Switch from Bash if necessary.  

   ![image](https://github.com/user-attachments/assets/c4b954c7-428e-44d8-a157-140d2b525308)

   ![image](https://github.com/user-attachments/assets/12c6750a-d65d-40dc-9d52-37bfa91990bc)



---

## Step 3: Clone the Sample Application  

1. In the Cloud Shell, run the following command to download the sample application:  
   ```powershell
   git clone https://github.com/MicrosoftLearning/AI-900-AIFundamentals ai-900
   ```  
   > **Note**: If you’ve already cloned this repository, skip this step.  

2. To view the files in the repository, run:  
   ```powershell
   code .
   ```
   ![image](https://github.com/user-attachments/assets/4676f30f-3923-4e90-aef3-74365a7cb1d4)

   This opens the code editor in the Cloud Shell.  

---

## Step 4: Configure the Application  

1. In the **Files** pane, expand the `ai-900` folder and select **form-recognizer.ps1**.  

   ![image](https://github.com/user-attachments/assets/79baf54e-f73a-4f82-a51f-e4161d3ca23b)

2. Replace the placeholders `YOUR_KEY` and `YOUR_ENDPOINT` with the values from the **Keys and Endpoint** page of your Azure resource:  
   ```powershell
   $key="YOUR_KEY_HERE"
   $endpoint="YOUR_ENDPOINT_HERE"
   ```  
3. Save the changes:  
   - Click the **...** button in the editor.  
   - Select **Save**.  
4. Close the editor by selecting **Close Editor** from the menu.  

---

## Step 5: Analyze a Receipt  

1. In the PowerShell pane, navigate to the `ai-900` folder:  
   ```powershell
   cd ai-900
   ```  
2. Run the script to analyze a sample receipt image: 

   ![image](https://github.com/user-attachments/assets/d12f8854-5344-4849-8883-c131506c0f23)
 
   ```powershell
   ./form-recognizer.ps1
   ```  
3. Review the returned results, which include:  
   - Merchant address and phone number.  
   - Transaction date and time.  
   - Line items, subtotal, tax, and total amounts.  

     ![image](https://github.com/user-attachments/assets/ca8653b6-a9f8-40b7-889f-cb7b79bb774f)


---

## Learn More  

Explore the full capabilities of the Form Recognizer service by visiting the [Form Recognizer page](https://azure.microsoft.com/en-us/services/form-recognizer/).  

---
