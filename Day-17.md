# Face Recognition with Azure Face API

This guide walks you through using the Azure Face API to detect human faces in images. You’ll create a Face API resource, configure a sample application, and test face detection using the Azure Cloud Shell.

## Prerequisites

To complete this lab, you will need an Azure subscription with administrative access.

## Overview

Imagine Northwind Traders wants to identify where customers are standing in a store to better assist them. Using the Face API, we can detect faces and draw bounding boxes around them in images. This guide will demonstrate how to test this capability using a command-line application in Azure Cloud Shell.

---

## Step 1: Create a Face API Resource

### Instructions:

1. Log in to the [Azure portal](https://portal.azure.com) with your Microsoft account.
2. Click on the “+ Create a resource” button, search for **Face**, and select it.
  ![image](https://github.com/user-attachments/assets/4a42bfd1-9ae6-4e03-9fa7-ed515fff32aa)


3. Configure the Face resource with the following settings:
   - **Subscription:** Select your Azure subscription.
   - **Resource group:** Create or select a resource group with a unique name.
   - **Region:** Choose any available region.
   - **Name:** Provide a unique name.
   - **Pricing tier:** Choose **Free F0**.
4. Click **Review + Create**, then **Create** the resource.
5. After deployment, navigate to the resource’s **Keys and Endpoint** page to retrieve the endpoint URL and access keys. These will be needed to connect to the API.
   

---

## Step 2: Open Cloud Shell

1. In the Azure portal, click on the **Cloud Shell** button “[>_]” located at the top of the page.
   
   ![image](https://github.com/user-attachments/assets/a21919d3-d14e-43da-aac8-e1d83ca7f0fc)

2. When prompted, select **PowerShell** as the shell type. If you don’t see this option, skip this step.
3. If required, create storage for the Cloud Shell by ensuring your subscription is specified and selecting **Create storage**. Wait for the storage to initialize.

   ![image](https://github.com/user-attachments/assets/2cd09b81-8092-4ccb-9896-386d9a069e94)

4. Confirm that the shell is set to PowerShell. If it’s set to Bash, switch to PowerShell using the drop-down menu on the top left of the Cloud Shell pane.
   
   ![image](https://github.com/user-attachments/assets/92a24267-1791-4a87-bd27-9fbda23e2c03)
   
   ![image](https://github.com/user-attachments/assets/68ab5d69-e67c-46a5-a3fc-2c32446f63e9)



---

## Step 3: Clone the Sample Application

1. In the PowerShell shell, run the following command to clone the sample application repository:

   ```powershell
   git clone https://github.com/MicrosoftLearning/AI-900-AIFundamentals ai-900
   ```

2. After the repository is cloned, run the following command to open the code editor:

   ```powershell
   code .
   ```
   ![image](https://github.com/user-attachments/assets/da42bb51-896d-4d20-88d7-9db55a9cb2a7)


3. In the **Files** pane on the left, expand the `ai-900` folder and open the file `find-faces.ps1`. This file contains the code to interact with the Face API.

   ![image](https://github.com/user-attachments/assets/4d55bbca-df1f-4a4b-8999-8399203a2339)


---

## Step 4: Configure the Application

1. In the code editor, locate and replace the placeholder values `YOUR_KEY` and `YOUR_ENDPOINT` with the actual key and endpoint from the **Keys and Endpoint** page of your Face resource.
2. Your updated code should look like this:

   ```powershell
   $key="<YOUR_ACTUAL_KEY>"
   $endpoint="<YOUR_ACTUAL_ENDPOINT>"
   ```

3. Save your changes by clicking the **...** menu in the top-right corner of the editor and selecting **Save**. Then close the editor.

---

## Step 5: Analyze Images with the Face Service

### Analyze the First Image:

1. Run the following commands to navigate to the `ai-900` directory and analyze the first image:
   
   ![image](https://github.com/user-attachments/assets/9c0976a6-5e63-4056-a914-b6d06ef164ff)


   ```powershell
   cd ai-900
   ./find-faces.ps1 store-camera-1.jpg
   ```
2. Review the output, which includes the coordinates of the detected face’s bounding box (top-left corner, width, and height).

   ![image](https://github.com/user-attachments/assets/5b6f8a43-6ee9-4dcc-93be-e75657c60660)
   
   ![image](https://github.com/user-attachments/assets/b00d031a-e971-4cc0-9f9d-7bf05a334d1e)



### Analyze the Second Image:

1. Run the following command to analyze the second image:
   
   ![image](https://github.com/user-attachments/assets/13625519-41c6-4d73-a815-3dc9e1757806)


   ```powershell
   ./find-faces.ps1 store-camera-2.jpg
   ```

2. Review the results for this image.
   
   ![image](https://github.com/user-attachments/assets/e8fdce3e-c21b-452d-8f53-0bc81066a041)
   
   ![image](https://github.com/user-attachments/assets/1b9b892c-b42e-4f21-9f3d-01c2b80b2424)



### Analyze the Third Image:

1. Run the following command to analyze the third image:
   
   ![image](https://github.com/user-attachments/assets/32e719aa-45d2-4acf-910e-4ef08391e18c)


   ```powershell
   ./find-faces.ps1 store-camera-3.jpg
   ```

2. Review the output for the third image.

    ![image](https://github.com/user-attachments/assets/b81e7b6d-461b-487d-9191-2fff6d9dbeb3)

    ![image](https://github.com/user-attachments/assets/25e1cd7e-6377-40d7-a447-207573ec92f6)



---

## Step 6: Learn More

This sample application demonstrates just a fraction of the Face API’s capabilities. To explore additional features, visit the [Face API page](https://azure.microsoft.com/services/cognitive-services/face/).

---

## Responsible AI

Note that Face service capabilities involving personally identifiable information are restricted to ensure ethical usage. Learn more about these safeguards on the [Responsible AI blog](https://azure.microsoft.com/blog/responsible-ai-investments-and-safeguards-for-facial-recognition/).

---

## Next Steps

Experiment with different images and explore advanced features of the Face API for deeper insights!

## Additional Resources
- Click here for demo video [Face Recognition with Azure Face API](https://www.linkedin.com/posts/reya-josephine-a871a827b_azureai-facerecognition-machinelearning-activity-7275217619685666816-RNrR?utm_source=share&utm_medium=member_desktop)

