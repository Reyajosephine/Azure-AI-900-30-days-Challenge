# Object Detection with Azure AI Services - Traffic Safety

Object detection is a key area of computer vision that trains models to identify and locate specific objects within images. Unlike simple image classification, object detection also provides the coordinates of objects, enabling answers to questions like: *"What objects are in this image, and where are they located?"*

For instance, object detection can enhance road safety by monitoring pedestrians and cyclists at traffic intersections, allowing for dynamic traffic management.

Microsoft Azure's Custom Vision service simplifies creating and deploying custom object detection models. Let’s explore object detection step by step.

---

## Prerequisites
- Active Azure subscription with administrative access.

---

## Steps

### 1. Create an Azure AI Services Resource
1. Log in to the [Azure portal](https://portal.azure.com).
2. Click **+ Create a resource** and search for **Azure AI services**.
3. Select **Create an Azure AI services plan**.

![Uploading image.png…]()

4. Set up the resource:
   - **Subscription**: Select your subscription.
   - **Resource group**: Create or use an existing group.
   - **Region**: East US.
   - **Name**: Enter a unique name.
   - **Pricing tier**: Standard S0.
   - **Terms**: Accept the terms.
5. Click **Review + Create** and then **Create**.
6. After deployment, note the **Keys and Endpoint** from the resource’s overview page.

   ![image](https://github.com/user-attachments/assets/1f2f3dbd-2607-4a86-945c-adc3e9d4f6d4)


   ![image](https://github.com/user-attachments/assets/4b296967-f10b-4030-9133-95cc5b7846b3)



---

### 2. Create a Custom Vision Project
1. Visit the [Custom Vision portal](https://customvision.ai) and sign in.
2. Create a new project:
   - **Name**: Traffic Safety.
   - **Description**: Object detection for road safety.
   - **Resource**: Select the AI resource created earlier.
   - **Project Type**: Object Detection.
   - **Domain**: General [A1].
     
     ![image](https://github.com/user-attachments/assets/ab203d1b-6359-44d6-adc0-0ba0f37694db)

     ![image](https://github.com/user-attachments/assets/98c8452d-2f75-4ad9-b6ce-56069c66d598)


3. Wait for the project to initialize.

---

### 3. Add and Tag Images
1. Download and extract the [training images](https://aka.ms/traffic-images).
2. Upload images to the Custom Vision portal using **Add images**.
   
   ![image](https://github.com/user-attachments/assets/c9ec7517-4312-4cd7-98eb-57bd18e15100)

   ![image](https://github.com/user-attachments/assets/c2e85fea-d9f9-4126-b43c-74e626f25c17)


3. Tag objects (e.g., "Cyclist" or "Pedestrian") for each image by drawing bounding boxes around them.
   
   ![image](https://github.com/user-attachments/assets/d9d38fe4-17b7-488e-aab5-6a0e99ee586c)

   
4. Verify all images are tagged under the **Tagged** section.

---

### 4. Train and Test the Model
1. Click **Train** and choose **Quick Training**.
   
   ![image](https://github.com/user-attachments/assets/fef4cb19-a770-49c7-87c6-f31e8ab987e5)

2. Review training metrics like **Precision**, **Recall**, and **mAP**.

   ![image](https://github.com/user-attachments/assets/93f475a8-b1de-48b5-86dc-4019a194358c)

3. Test the model:
   - Click **Quick Test**.
     
     ![image](https://github.com/user-attachments/assets/e5082e82-bda0-4a7e-9cfe-ff7d52c184ca)

   - Enter the URL `https://aka.ms/pedestrian-cyclist`.
   - Observe predictions and adjust the **Threshold Value** slider to filter results.

---

### 5. Publish the Model
1. Click **Publish** and configure:
   - **Model name**: traffic-safety.
   - **Prediction resource**: Select your Azure resource.
2. Copy the **Prediction URL** and **Prediction Key** for use in the next step.
   
   ![image](https://github.com/user-attachments/assets/74adaa7c-167e-4b3e-a8b4-a6b5087daa82)


---

### 6. Set Up the Client Application
1. Open Azure Cloud Shell ([>_]).
   
   ![image](https://github.com/user-attachments/assets/29bc9667-3104-42cd-afc0-981740f8f08b)

2. Choose **PowerShell** if prompted.
3. Run the following commands to set up the application:
   ```powershell
   rm -r ai-900 -f
   git clone https://github.com/MicrosoftLearning/AI-900-AIFundamentals ai-900
   cd ai-900
   code detect-objects.ps1
   ```
4. Replace placeholders in `detect-objects.ps1` with your Prediction URL and Key:
   
   ![image](https://github.com/user-attachments/assets/c12a46da-5bc6-4b9f-93bc-07e667022682)

   ```powershell
   $predictionUrl="https..."
   $predictionKey ="1a2b3c4d5e6f7g8h9i0j...."
   ```
5. Save and close the file.

---

### 7. Test the Client Application
1. Analyze an image:
   
   ![image](https://github.com/user-attachments/assets/231052bf-de57-4cba-9207-ce772b97bfdf)

   ```powershell
   ./detect-objects.ps1 1
   ```
2. Test another image:
   
   ![image](https://github.com/user-attachments/assets/5893ca67-bf43-4f20-8b32-89f1e73d5fe8)

   ```powershell
   ./detect-objects.ps1 2
   ```
3. Review results to ensure accurate detection of cyclists and pedestrians.

---

By following these steps, you’ve successfully explored object detection using Azure Custom Vision. 🎉
