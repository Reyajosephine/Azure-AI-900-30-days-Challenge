# Explore Speech with Azure AI  

This guide walks you through using the Azure AI Speech service to transcribe spoken language into text and synthesize text into speech. You will create a simple application to test this service.  

## Prerequisites  
- An Azure subscription with administrative access.  

## Scenario Overview  
We will build a basic command-line application that uses the Azure AI Speech service. This application will recognize and respond to spoken input. For example, when asked, "What time is it?", it will provide the current local time.  

---

## Steps to Complete  

### 1. Create an Azure AI Services Resource  

1. Sign in to the [Azure portal](https://portal.azure.com).  
2. Click **+ Create a resource**, search for **Azure AI services**, and select it.  
3. Click **Create** and configure it with the following details:  
   - **Subscription**: Select your subscription.  
   - **Resource group**: Choose an existing resource group or create a new one.  
   - **Region**: Select any available region.  
   - **Name**: Enter a unique name.  
   - **Pricing tier**: Choose **Standard S0**.  
   - Accept the terms and click **Review + Create**.  
4. Wait for the resource deployment to complete.  

### 2. Retrieve Keys and Endpoint  

1. Go to your newly created Azure AI services resource in the portal.  
2. In the **Overview** section, select **Manage keys**.  
3. Copy the **Key** and **Region** (location). These will be needed to connect your client application to the service.  

### 3. Run Cloud Shell  

1. Open the Cloud Shell in the Azure portal by clicking the **[>_]** button in the top-right corner of the page.

   ![image](https://github.com/user-attachments/assets/f1821d47-899d-4a5e-bba8-dbbabc205bcf)
  
2. Select **PowerShell** as the shell type (if prompted).

   ![image](https://github.com/user-attachments/assets/2d5f7a10-3edd-4eaa-882e-d812a4040ea2)

3. If storage needs to be created, confirm and wait for the setup to finish.  
4. Ensure the shell type is PowerShell. If it’s Bash, use the drop-down menu to switch to PowerShell.
   ![image](https://github.com/user-attachments/assets/9c7009b2-9d9b-4193-bff6-c26f8f3447f3)

   ![image](https://github.com/user-attachments/assets/fed630db-b7d5-4559-82e4-6bc0e73c1241)



---

### 4. Configure and Run the Client Application  

#### Clone the Sample Repository  

1. In the Cloud Shell, run the following command to download the sample application: 
   ```bash
   git clone https://github.com/MicrosoftLearning/AI-900-AIFundamentals ai-900
   ```  
   If you’ve already cloned the repository in another lab, skip this step.  

1. To view the files, enter:  
   ```bash
   code .
   ```
   ![image](https://github.com/user-attachments/assets/9e45affa-3b20-408c-b13f-eae7446f543d)


#### Update the Code  

1. In the editor, open `ai-900/speaking-clock.ps1`.  
2. Replace `YOUR_KEY` and `YOUR_LOCATION` in the script with the Key and Region/Location from your Azure AI services resource. The code should look like this:  

   ![image](https://github.com/user-attachments/assets/58703908-2199-4c23-9cc1-44da932befc4)

   ```powershell
   $key = "1a2b3c4d5e6f7g8h9i0j...."
   $region = "somelocation"
   ```  
3. Save your changes using the **…** menu at the top-right of the editor pane.  

---

#### Run the Application  

1. In the Cloud Shell, navigate to the application folder:  
   ```bash
   cd ai-900
   ```  
2. Run the script:  
   ```bash
   ./speaking-clock.ps1
   ```  
3. The application will process a pre-recorded input file, recognize the spoken words (“What time is it?”), and generate a response in an `output.wav` file.  

## Audio Files
   Download the audio files from below:
   -[Input Audio](https://github.com/Reyajosephine/Azure-AI-900-30-days-Challenge/blob/main/azure%20speech%20input.mp4)
   -[Output Audio](https://github.com/Reyajosephine/Azure-AI-900-30-days-Challenge/blob/main/azure%20speech%20output.mp4)
   

---

### Learn More  

This example demonstrates just a fraction of what the Azure AI Speech service can do. Explore the [Azure Speech Service documentation](https://learn.microsoft.com/en-us/azure/cognitive-services/speech-service/) for more capabilities.  
