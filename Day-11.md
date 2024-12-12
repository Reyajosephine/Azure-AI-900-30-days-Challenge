# Setting Up an Azure AI Services Resource and Testing the Computer Vision Service

## Step 1: Create an Azure AI Services Resource

### Instructions
1. **Open the Azure Portal**
   - Go to [Azure Portal](https://portal.azure.com) and sign in with your Microsoft account.

2. **Create a New Resource**
   - Click on **`+ Create a resource`**.
     
   - Search for **Azure AI services**.
   - Select **`Create an Azure AI services plan`**.

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

   - Open the `analyze-image.ps1` file.
   - Replace the placeholder values with your endpoint and key:
     ![image](https://github.com/user-attachments/assets/dae7521c-7933-4161-956f-218f9479782f)

     ```powershell
     $key="YOUR_KEY"
     $endpoint="YOUR_ENDPOINT"
     ```

4. **Save Changes**
   - Use the `...` menu at the top right of the editor to save the file.

---

## Step 4: Run the Application

### Instructions
1. **Navigate to the Folder**
   ```powershell
   cd ai-900
   ```

2. **Analyze Images**
   - To analyze the first image:
     ![image](https://github.com/user-attachments/assets/eda0a74d-12bc-415c-b99e-c4445c091714)

   - Enter the following command.  
     ```powershell
     ./analyze-image.ps1 store-camera-1.jpg
     ```
   - To analyze the second image:
     ![image](https://github.com/user-attachments/assets/032ac8c1-e293-4b31-838e-ac9498211c5c)
  
   - Enter the following command.

     ```powershell
     ./analyze-image.ps1 store-camera-2.jpg
     ```
   - To analyze the third image:
     ![image](https://github.com/user-attachments/assets/abe7282c-46c6-4ad0-b4dc-1703b168d5e5)
  
   - Enter the following command.

     ```powershell
     ./analyze-image.ps1 store-camera-3.jpg
     ```

3. **Review Results**
   - The output includes:
     - Suggested captions.
     - Identified objects.
     - Relevant tags for each image.

---

## Additional Resources
- Click here for demo video [Setting Up an Azure AI Services Resource and Testing the Computer Vision Service](https://www.linkedin.com/posts/reya-josephine-a871a827b_azureai-computervision-cloudcomputing-activity-7273005873591894018-NGZT?utm_source=share&utm_medium=member_desktop)

