# Guide to Create VMs from Snapshots in Azure

This guide will walk you through the steps to take a snapshot of an existing Virtual Machine (VM) and then create a new VM using that snapshot in the Azure Portal.

## Prerequisites
- An active Azure subscription.
- An existing Virtual Machine that you want to capture.

## Steps to Capture VM and Create a New VM

1. **Log in to the Azure Portal**
   - Go to [Azure Portal](https://portal.azure.com/).
   - Enter your credentials to log in.

2. **Search for Virtual Machines**
   - In the top search bar, type **"Virtual Machines"** and select it from the drop-down menu.

    ![image](https://github.com/user-attachments/assets/da25c746-c718-4d43-888f-dd7182a4b3f2)


3. **Select the Existing VM**
   - Click on the VM that you want to capture from the list of existing VMs.

     ![image](https://github.com/user-attachments/assets/f193b5c6-0901-479b-a842-7bd72d30ff3e)


4. **Access VM Overview**
   - Once in the VM's dashboard, go to the **Overview** tab.

5. **Capture the VM**
   - Click on **Capture** from the top menu.

     ![image](https://github.com/user-attachments/assets/0ab1b657-2520-4677-b63b-5dd20caa69b9)

   - In the capture dialog, fill in the following details:
     - **Gallery details**: Select the appropriate gallery or create a new one.

       ![image](https://github.com/user-attachments/assets/86acecb6-7352-4dff-a7a7-bd32b6609866)

     - **VM Image Definition**: Provide a name for the image definition.
     - **Version Number**: Assign a version number (e.g., 1.0).
     - **End of Life Date**: Specify an end-of-life date for the image if needed.
     - **Replica Count**: Set the number of replicas you want for the image.

6. **Review and Create Image**
   - Click on **Review + create** to review your details.
   - If everything looks good, click on **Create** to capture the image.
   - Wait for the deployment to finish.

7. **Open the VM Image Version**
   - Once deployed, click **go to resource**.

8. **Add a New VM**
   - Click on **Add VM** or **Create VM** from the image details page.

     ![image](https://github.com/user-attachments/assets/97a63d30-7999-4469-891c-31461d98da15)

   - Fill in the VM details such as:
     - **VM Name**: Enter a name for your new VM.
     - **Zone**: Select the availability zone (if applicable).
     - **Size**: Choose the desired VM size.
   - Select **Standard SSD** for the disk type under the **Disks** tab.

9. **Review and Create New VM**
   - Click on **Review + create** to check all the configurations.
   - Click on **Create** to finalize the new VM deployment.

     ![image](https://github.com/user-attachments/assets/12ccd7ec-0f3f-41b2-b30a-af52dd2506d9)

   - Wait for the deployment to complete.

10. **Check the New VM Resource**
    - Once deployed, click on **go to resource** to check the status of your new VM.

## Demo video
-Click here for demo video [Guide to Create VMs from Snapshots in Azure](https://www.linkedin.com/posts/reya-josephine-a871a827b_azure-virtualmachines-snapshots-activity-7259632142173798400-vGu0?utm_source=share&utm_medium=member_desktop)

## Additional Resources
- For more detailed instructions, refer to the official [Azure Virtual Machines Documentation](https://docs.microsoft.com/en-us/azure/virtual-machines/).
- Check out my prevoius guide for steps to create a VM [Azure Virtual Network and Virtual Machine Setup Guide](https://github.com/Reyajosephine/Azure-30-days-Challenge/blob/main/Day-1.md)

Happy cloud computing! 🌥️
