# Image Classification with Azure Custom Vision

## Introduction

Image classification is a fundamental task in computer vision, where the goal is to assign a label or category to an image based on its content. It involves training machine learning models to recognize patterns in images and classify them into predefined categories. For example, in wildlife conservation, an image classification model can be used to identify different animal species from images captured by cameras in natural habitats. This helps researchers track and monitor animal populations.

In this guide, we’ll use Azure's Custom Vision service to train an image classification model to recognize animal species, such as elephants, giraffes, and lions, from images. Azure Custom Vision makes it easy to build, train, and deploy image classification models without deep expertise in machine learning. By the end of this tutorial, you’ll have a model that can accurately classify images into different categories based on the training data.

## Step 1: Set up the environment

Ensure you have an Azure subscription with admin access. If not, sign up at [Azure](https://azure.com).

## Step 2: Create an Azure AI Services Resource

1. Open [Azure Portal](https://portal.azure.com) and sign in with your Microsoft account.
2. Click the **+Create a resource** button, search for 'Azure AI Services' and select **Create Azure AI Services plan**.

   ![image](https://github.com/user-attachments/assets/f1bcc6e9-8f7f-4d13-a721-a2ea1f79cf15)

4. Set the following configuration:
   - **Subscription**: Your Azure subscription.
   - **Resource group**: Select or create a resource group with a unique name.
   - **Region**: East US.
   - **Name**: Give your resource a unique name.
   - **Pricing Tier**: Select Standard S0.
5. Review and create the resource, then wait for it to be deployed.

Once the deployment completes, go to the newly created resource.  
Go to the **Keys and Endpoint** page. You’ll need the endpoint and keys to connect from your application.

![image](https://github.com/user-attachments/assets/be2ae57e-2d94-4a2e-8425-45d9c626e49a)


## Step 3: Create a Custom Vision Project

To train an object detection model, use the Custom Vision portal.

1. Download and extract the training images from [this link](https://aka.ms/animal-images) (a zipped folder containing subfolders named `elephant`, `giraffe`, and `lion`).
2. Open the [Custom Vision portal](https://customvision.ai) and sign in using your Microsoft account associated with Azure.
3. Create a new project with the following settings:
   - **Project Name**: Animal Identification
   - **Description**: Classify animal images.
   - **Resource**: Select the Azure AI Services resource created earlier.
   - **Project Type**: Classification.
   - **Classification Type**: Multiclass (Single tag per image).
   - **Domain**: General [A2].

     ![image](https://github.com/user-attachments/assets/bd464588-b618-416e-940c-5b6a5952f0e2)

     ![image](https://github.com/user-attachments/assets/574bb099-ef75-4fab-9a44-190dfeeb8078)



## Step 4: Upload Training Images

1. Upload images for the classes `elephant`, `giraffe`, and `lion`.
2. In the Custom Vision portal, click **Add images** and upload all files in the "elephant" folder, tagging them with `elephant`.

   ![image](https://github.com/user-attachments/assets/da0a1588-4d99-4e90-91f2-0f7428f79164)

   ![image](https://github.com/user-attachments/assets/a7f3c50c-0da1-43ca-b276-babe1a7aff97)


4. Repeat this for the `giraffe` and `lion` images, tagging them with `giraffe` and `lion` respectively.
   
Once all images are uploaded, you should have 17 images for each class.

![image](https://github.com/user-attachments/assets/77cf7a36-4638-4349-932f-36368f627c1a)


## Step 5: Train the Model

1. Click the **Train** button at the top of the project page and select **Quick Training**.

    ![image](https://github.com/user-attachments/assets/0fe84cd6-0274-41fb-8ee8-4a29a594deb0)

    ![image](https://github.com/user-attachments/assets/3550492f-900a-420c-8b38-cf5e42767dc6)


3. Wait for the training to complete. This may take a few minutes.

## Step 6: Test the Model

1. After training completes, review the Precision, Recall, and Average Precision (AP) metrics to assess the model’s accuracy.

    ![image](https://github.com/user-attachments/assets/edb8fbe6-34a4-4808-ace7-0d17462bf77b)

3. Click **Quick Test** to try an image classification test.

    ![image](https://github.com/user-attachments/assets/99654114-c1bc-41be-97c3-2760222e7a3a)

4. Enter the URL: [https://aka.ms/giraffe](https://aka.ms/giraffe) in the **Image URL** box and click the test button.

    ![image](https://github.com/user-attachments/assets/bd4247cf-aedb-4f54-80b9-a6baf1c8df9f)

5. The model should predict the class `giraffe` with the highest probability.

    ![image](https://github.com/user-attachments/assets/bed9778e-8fdd-423a-94c6-96d368a81eb6)


## Step 7: Publish the Model

Once satisfied with the model's performance, click **Publish** to make it available for use in applications. Set the following:
- **Model Name**: animals
- **Prediction Resource**: Select the Azure AI Services or Custom Vision prediction resource.

After publishing, copy the **Prediction URL** and **Prediction Key**. You'll need these values to make requests from a client application.

![image](https://github.com/user-attachments/assets/a92e9117-21f3-4cb5-aaae-3cef5462d1f3)


## Step 8: Prepare the Client Application

1. Open the **Azure Cloud Shell** by selecting the Cloud Shell button (top-right of the portal).

   ![image](https://github.com/user-attachments/assets/3fa516a8-7695-4f2f-89b8-fa720f59ebda)

3. Choose **PowerShell** as the shell type. If it’s your first time, you may be prompted to set up storage for Cloud Shell.

   ![image](https://github.com/user-attachments/assets/281b55fd-754d-4554-ac25-d4ac948196f4)

   ![image](https://github.com/user-attachments/assets/51267b8a-62d9-4218-bccc-c6cf76f6f6d5)

    ![image](https://github.com/user-attachments/assets/eb04f274-db00-4dd6-add1-a15bd250980a)



4. In the Cloud Shell, run the following to download the sample files:
   ```bash
   rm -r ai-900 -f
   git clone https://github.com/MicrosoftLearning/AI-900-AIFundamentals ai-900
   ```
5. Change to the directory with the downloaded files:
   ```bash
   cd ai-900
   ```

## Step 9: Update the Client Application with Prediction Details

1. Open the PowerShell script file (`classify-image.ps1`) for editing:
   ```bash
   code classify-image.ps1
   ```

   ![image](https://github.com/user-attachments/assets/f2cef6c4-b21c-48b2-a300-30271378605f)


3. In the editor, find the lines where `$predictionUrl` and `$predictionKey` are specified.
4. Replace the placeholders with the actual values from your Custom Vision project (Prediction URL and Prediction Key).

Example:
```powershell
$predictionUrl = "https://<your-prediction-url>"
$predictionKey = "<your-prediction-key>"
```
4. Save and close the editor.

## Step 10: Run the Client Application

1. Back in the Cloud Shell, run the following command to classify the first image (giraffe):

    ![image](https://github.com/user-attachments/assets/84d6c2a8-fdce-4195-b0f8-8bbb5a87b22a)

   ```bash
   ./classify-image.ps1 1
   ```
   The prediction should return `giraffe` for the first image.
   
3. Run the same script to classify the second image (elephant):

    ![image](https://github.com/user-attachments/assets/b9866724-a9fb-4422-ace2-13b2d140a8a9)

   ```bash
   ./classify-image.ps1 2
   ```
   The prediction should return `elephant` for the second image.
   
4. Finally, classify the third image (lion):

   ![image](https://github.com/user-attachments/assets/ff4bfac9-36d6-4e7b-abf5-7441cc5dca5d)


   ```bash
   ./classify-image.ps1 3
   ```
   The prediction should return `lion` for the third image.

## Step 11: Conclusion

If all images are classified correctly, your image classification model is successfully trained, tested, and deployed!  
You can now use this model in real-world applications to classify images of animals and support conservation efforts.

## Additional Resources
- Click here for demo video [Image Classification with Azure Custom Vision](https://www.linkedin.com/posts/reya-josephine-a871a827b_azureai-imageclassification-customvision-activity-7273766195768496129-enGK?utm_source=share&utm_medium=member_desktop)


