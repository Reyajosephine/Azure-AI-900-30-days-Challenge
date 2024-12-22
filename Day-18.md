# Optical Character Recognition (OCR) with Azure AI Vision  

This project demonstrates how to perform Optical Character Recognition (OCR) using Azure AI Vision and Microsoft's Read API. Follow the steps to configure and test a simple command-line application in Azure Cloud Shell to analyze text in images.  

---

## Prerequisites  
- An active Azure subscription with administrative access.  

---

## Overview  
Optical Character Recognition (OCR) involves detecting and interpreting text within images. This lab uses the Read API, which is optimized for both printed and handwritten text in documents.  

---

## Steps to Complete  

### 1. Create an Azure AI Services Resource  

1. Open the [Azure Portal](https://portal.azure.com) and sign in with your Microsoft account.  
2. Click the **+ Create a resource** button.  
3. Search for **Azure AI Services** and select **Create an Azure AI Services Plan**.  
4. Configure the resource with the following settings:  
   - **Subscription:** Your Azure subscription.  
   - **Resource group:** Select or create a new resource group.  
   - **Region:** Choose any available region.  
   - **Name:** Enter a unique name for your resource.  
   - **Pricing tier:** Select **Standard S0**.  
5. Acknowledge the terms and click **Review + Create**.  
6. Once the deployment completes, navigate to the deployed resource.  
7. Open the **Keys and Endpoint** page, and note the **endpoint** and **keys** for use in the application.  

---

### 2. Open Cloud Shell  

1. In the Azure Portal, click the **Cloud Shell** button ( [>_] icon) located at the top-right of the page. 
   
   ![image](https://github.com/user-attachments/assets/d5bac81f-e022-4ba6-b53d-02be82c8e38b)
 
2. Select **PowerShell** as the shell type if prompted.  
   
   ![image](https://github.com/user-attachments/assets/589a344b-dcc1-497f-a633-437665111267)
 
3. If required, create storage for Cloud Shell by clicking **Create storage**.  
4. Wait for the PowerShell environment to initialize.  

   ![image](https://github.com/user-attachments/assets/29d3cc5c-b571-4dd9-b9da-9718385ed2b3)

   ![image](https://github.com/user-attachments/assets/20434023-f64e-4afa-9585-05e8512fee4f)



---

### 3. Configure the Sample Application  

1. Clone the sample repository to your Cloud Shell by running:  
   ```bash
   git clone https://github.com/MicrosoftLearning/AI-900-AIFundamentals ai-900
   ```  
   > **Tip:** If this repository was already cloned in another lab, skip this step.  

2. Open the code editor by running:  
   ```bash
   code .
   ```  
   ![image](https://github.com/user-attachments/assets/83731c9b-462b-46cf-bba1-aa04c383e258)


3. In the **Files** pane, expand the `ai-900` folder and open the `ocr.ps1` file.
   
   ![image](https://github.com/user-attachments/assets/fd3d4dd8-52e6-42b0-9129-d200c339c334)
  

4. Replace the `YOUR_KEY` and `YOUR_ENDPOINT` placeholders with the values copied from your Azure resource:  
   ```powershell
   $key="1a2b3c4d5e6f7g8h9i0j...."    
   $endpoint="https://<your-resource-name>.cognitiveservices.azure.com/"
   ```  

5. Save the changes by clicking the **...** menu in the editor and selecting **Save**.  

---

### 4. Run the Application  

1. Navigate to the application folder:  
   ```bash
   cd ai-900
   ```  

2. Analyze an image with text (e.g., an advertisement):
   
   ![image](https://github.com/user-attachments/assets/452620f6-aa3b-4ae6-bf28-eb934e7e801e)

  
   ```bash
   ./ocr.ps1 advert.jpg
   ```  

3. Review the detected text, which is structured into regions, lines, and words along with bounding box coordinates.  

4. Test another image (e.g., a typed letter):

   ![image](https://github.com/user-attachments/assets/ca702741-5231-4443-9271-f2c6222a0087)

   ```bash
   ./ocr.ps1 letter.jpg
   ```  

---

## Learn More  
To explore additional OCR capabilities of Azure AI Vision, visit the official [OCR Documentation](https://learn.microsoft.com/en-us/azure/cognitive-services/computer-vision/overview-ocr).  

## Additional Resources
- Click here for demo video [Optical Character Recognition (OCR) with Azure AI Vision](https://www.linkedin.com/posts/reya-josephine-a871a827b_azureai-opticalcharacterrecognition-machinelearning-activity-7276283527694823424-FuQ9?utm_source=share&utm_medium=member_desktop)

