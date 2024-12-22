# Setting Up an Azure AI Services Resource and Testing the Text Analytics Service

## Introduction

**Azure Text Analytics** is a powerful AI service that provides advanced natural language processing (NLP) capabilities. It enables developers to extract key insights from unstructured text, such as sentiment analysis, key phrase extraction, named entity recognition, and language detection. By leveraging these features, businesses can gain actionable insights from customer feedback, social media, or any text-based data.

This guide will walk you through setting up the **Azure AI Services resource** for Text Analytics and testing its capabilities using the sample application provided by Microsoft. Whether you're analyzing customer sentiments or identifying important information from documents, this step-by-step process will help you get started with ease.

---

## Step 1: Create an Azure AI Services Resource

### Instructions

1. **Open the Azure Portal**
   - Go to [Azure Portal](https://portal.azure.com) and sign in with your Microsoft account.

2. **Create a New Resource**
   - Click on **`+ Create a resource`**.
   - Search for **Azure AI services**.
   - Select **`Create an Azure AI services plan`**.
     ![Screenshot 2024-12-14 001319](https://github.com/user-attachments/assets/81227285-5244-4aa5-8a53-2e75504ea6f7)


3. **Configure the Resource**
   - Use the following settings:
     - **Subscription**: Select your Azure subscription.
     - **Resource group**: Create a new one or select an existing one.
     - **Region**: Choose an available region.
     - **Name**: Enter a unique name for the resource.
     - **Pricing tier**: Select **Standard S0**.
     - Check the acknowledgment box to agree to the terms.

4. **Deploy the Resource**
   - Click **`Review + Create`**, then **`Create`** to deploy the resource.

5. **Access Keys and Endpoint**
   - After deployment, navigate to the resource.
     ![Screenshot 2024-12-14 001433](https://github.com/user-attachments/assets/9d63bd55-8002-4e67-a7e1-3c243e846a18)

   - Go to the **Keys and Endpoint** section.
       ![image](https://github.com/user-attachments/assets/e09d168b-e691-4f72-bcd6-a60c1c583e09)
     
   - Note down the **Endpoint URL** and **Key** values.

---

## Step 2: Open Azure Cloud Shell

### Instructions

1. **Launch Cloud Shell**
   - In the Azure portal, click on the **Cloud Shell** button (`[>_]`) at the top-right of the page.
      ![image](https://github.com/user-attachments/assets/450ad6e7-e6d5-42d7-8cce-d1b3ec1e072d)


2. **Choose PowerShell**
   - If prompted, select **PowerShell** as the shell type.
      ![image](https://github.com/user-attachments/assets/27a59eaa-9bbf-4c3f-b998-94afe30ba95a)

3. **Set Up Cloud Shell Storage**
   - If required, follow the prompts to create a storage account for Cloud Shell.
      ![image](https://github.com/user-attachments/assets/64d1616a-1e9f-489f-a3e8-0d5c5a92ffe9)

4. **Confirm Shell Type**
   - Ensure the shell is set to **PowerShell**. If it is set to **Bash**, switch to PowerShell using the dropdown menu.
      ![image](https://github.com/user-attachments/assets/68ee9d63-41e2-440c-8b44-ba8ae96655c7)
     
     ![image](https://github.com/user-attachments/assets/01d223c2-cbf8-45e1-9db9-b1aaa0d288cf)

---

## Step 3: Clone the Sample Application Repository

### Instructions

1. **Clone the Repository**
   ```powershell
   git clone https://github.com/MicrosoftLearning/AI-900-AIFundamentals ai-900
   ```
   - This command clones the repository into a folder named `ai-900`.
     

2. **Open the Code Editor**
   ```powershell
   code .
   ```
   - This opens the Cloud Shell editor.

3. **Edit the Code**
   - Expand the `ai-900` folder in the **Files** pane.
      ![image](https://github.com/user-attachments/assets/8fbc90b3-87e5-475f-b08d-68c75836fbdb)

   - Open the `analyze-text.ps1` file.
     ![image](https://github.com/user-attachments/assets/6ba09c6d-bf83-4b4e-8c4e-676620a50b0f)

   - Replace the placeholder values with your endpoint and key:
     ```powershell
     $key="YOUR_KEY"
     $endpoint="YOUR_ENDPOINT"
     ```
     ![image](https://github.com/user-attachments/assets/64693a25-23e3-40dc-a28a-693dcba9c274)


4. **Save Changes**
   - Use the `...` menu at the top right of the editor to save the file.

---

## Step 4: Run the Application

### Instructions

1. **Navigate to the Folder**
   ```powershell
   cd ai-900
   ```

2. **Analyze Text**
   - To analyze the sample text:
     ```powershell
     ./analyze-text.ps1 "The food was amazing and the service was excellent."
     ```

3. You will now run the client application to **analyze text reviews**. Use the following commands in Cloud Shell:

- For **Review 1**:

   ```bash
   ./analyze-text.ps1 review1.txt
   ```

- For **Review 2**:

   ```bash
   ./analyze-text.ps1 review2.txt
   ```

- For **Review 3**:

   ```bash
   ./analyze-text.ps1 review3.txt
   ```

- For **Review 4**:

   ```bash
   ./analyze-text.ps1 review4.txt
   ```

## Step 8: Review the Outputs

The application will analyze each review and return several pieces of information:

- **Detected Language**: The language of the review.
- **Key Phrases**: Important phrases extracted from the review.
- **Sentiment**: The sentiment (positive or negative) of the review.
- **Named Entities**: Entities such as locations or people mentioned in the review.

  ![image](https://github.com/user-attachments/assets/752e5531-8946-4ee5-b26e-459b541529ab)

  ![image](https://github.com/user-attachments/assets/c86e0e43-1c89-4d31-9f96-ca95ce3222f9)


## Conclusion

You have successfully set up and used Azure's Language service to analyze text reviews. The Language service can be extended to various other text analysis tasks such as sentiment analysis, language detection, and key phrase extraction.

Feel free to modify the sample code and integrate it into your own applications!

## Additional Resources
- Click here for demo video [Azure Machine Learning Designer - Classification with Diabetes Dataset](https://www.linkedin.com/posts/reya-josephine-a871a827b_azureai-textanalytics-ai-activity-7273645404347363328-_7d1?utm_source=share&utm_medium=member_desktop)
