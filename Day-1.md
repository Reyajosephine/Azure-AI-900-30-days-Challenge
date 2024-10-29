# Azure Virtual Network and Virtual Machine Setup Guide

## Introduction

In Azure, a **Virtual Network (VNet)** is a secure, isolated network that enables you to connect Azure resources to each other. It’s like your own private network in the cloud, where you can define IP address ranges, create subnets, and set up security rules.

A **subnet** is a segment within your VNet that helps organize and secure your resources. By dividing your VNet into subnets, you can control traffic flow and apply security policies more effectively.

A **Virtual Machine (VM)** is a software emulation of a physical computer. In Azure, VMs allow you to run applications and services as if they were running on a physical server, but with the added benefits of scalability, flexibility, and cost-effectiveness.

This guide will help you set up a VNet, create a subnet, and deploy a VM, so you can start leveraging Azure's powerful cloud capabilities. Let’s get started!

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Task 1: Create a Virtual Network and Set Up a Subnet](#task-1-create-a-virtual-network-and-set-up-a-subnet)
3. [Task 2: Create a Virtual Machine on the Subnet](#task-2-create-a-virtual-machine-on-the-subnet)
4. [Connect to Your Virtual Machine](#connect-to-your-virtual-machine)

## Prerequisites

Before we jump in, make sure you have:

- An active Azure account. If you haven’t signed up yet, head over to [Azure's free account page](https://azure.microsoft.com/free/) and get started!

---

## Task 1: Create a Virtual Network and Set Up a Subnet

1. **Navigate to Virtual Networks**:
   - Open the Azure portal and look for the **menu bar** on the left. 
   - Click on **"Virtual networks"**.

2. **Create a New Virtual Network**:
   - Hit the **"Create"** button to start crafting your VNet.
     ![Screenshot 2024-10-29 203049](https://github.com/user-attachments/assets/592661da-1c23-4e91-be38-e108b0d6ea20)


3. **Configure Your Virtual Network**:
   - **Select Subscription**: Pick your Azure subscription from the dropdown.
   - **Select or Create Resource Group**: Choose an existing resource group or create a new one to keep things organized.
   - **Instance Details**:
     - **Name**: Give your virtual network a catchy name (e.g., `MyVNet`).
     - **Region**: Choose a region that’s convenient for you (e.g., `South India`).
       ![Screenshot 2024-10-29 203620](https://github.com/user-attachments/assets/4e476ff5-0170-4a99-a995-6eea4e7880fb)


4. **Set Up IP Addresses**:
   - Head to the **"IP Addresses"** tab.
   - Click on **"Create New IP Address"** to define your address space (try something like `10.0.0.0/16`).
     ![Screenshot 2024-10-29 203634](https://github.com/user-attachments/assets/3539fb82-45bb-4d12-8fbc-ca02b23b2f71)


5. **Create a Subnet**:
   - Under the **"Subnets"** section, click on **"Add subnet"**.
     - **Name**: Pick a name for your subnet (e.g., `MySubnet`).
     - **Address Range**: Set the address range for your subnet (e.g., `10.0.0.0/24`).
   - Click **"Add"** to create your new subnet.

6. **Review and Create**:
   - Now, click on **"Review + create"**. 
   - After checking everything, hit **"Create"** to deploy your virtual network.
     ![Screenshot 2024-10-29 203658](https://github.com/user-attachments/assets/3dc5af41-3f4f-4df0-b48d-cdf8c4fcd01a)


7. **View Your Virtual Network**:
   - Once the deployment is completed, navigate back to **"Virtual networks"**.
![Screenshot 2024-10-29 203731](https://github.com/user-attachments/assets/e7ee4eb8-7777-46e1-852c-2553dec80874)

   - Click on your VNet to explore its details and subnets. You can add more subnets if you wish!

---

## Task 2: Create a Virtual Machine on the Subnet

1. **Search for Virtual Machines**:
   - In the Azure portal, use the search bar at the top and type **"Virtual Machines"**.
   - Click on **"Virtual Machines"** from the search results.

2. **Create a New Virtual Machine**:
   - Click on **"Create"** and select **"Azure Virtual Machine"**. 
![Screenshot 2024-10-29 204730](https://github.com/user-attachments/assets/d96cd096-e7e5-4807-bb50-1a9cc51c33fc)


3. **Fill in the Required Information**:
   - **Select Subscription**: Choose the same subscription you used before.
   - **Select or Create Resource Group**: Pick your resource group again.
   - **Virtual Machine Name**: Give your VM a friendly name (e.g., `MyVM`).
   - **Region**: Select the same region as your virtual network.
   - **Image**: Choose the OS for your VM (e.g., `Windows Server 2022` or `Ubuntu 20.04`).
   - **VM Architecture**: Stick with the default `x64`.
   - **Size**: Select a size based on what you’ll be doing (e.g., `Standard_DS1_v2`).

4. **Admin Account**:
   - Under the **"Admin Account"** section:
     - **Authentication Type**: Choose **"Password"**.
     - **Username**: Create a username for your VM (e.g., `adminUser`).
     - **Password**: Enter a strong password and confirm it.

5. **Configure Disks**:
   - In the **"Disks"** tab:
     - Choose **"Standard SSD"** as your OS disk type.
![Screenshot 2024-10-29 204747](https://github.com/user-attachments/assets/22461244-b54d-421a-b60d-b0e6aeda14c6)

     - Leave the rest as it is,you can even customise the other specifications.

6. **Networking**:
   - Under the **"Networking"** section:
     - **Virtual Network**: Select your VNet (`MyVNet`).
     - **Subnet**: Choose the subnet you just created (`MySubnet`).
     - You can adjust public IP and NSG settings as needed.
![Screenshot 2024-10-29 204916](https://github.com/user-attachments/assets/c660447f-6118-4b52-986e-62f31e903a83)


7. **Review and Create**:
   - Click **"Review + create"**.
   - After a quick validation check, hit **"Create"** to deploy your VM. 


---

## Connect to Your Virtual Machine

1. **Navigate to the Dashboard**:
   - Once the VM deployment is done, head back to the **"Virtual Machines"** section.

2. **Connect to Your Virtual Machine**:
   - Click on your new VM.
   - Hit the **"Connect"** button at the top.
   - Choose **"RDP"** if you’re on a Windows VM.

3. **Download the RDP File**:
   - Click on **"Download RDP File"**. This will save a connection file to your computer.
     ![Screenshot 2024-10-29 205613](https://github.com/user-attachments/assets/d7a5c3eb-c7e1-47a6-acf9-9eb02af17e36)


4. **Open the RDP File**:
   - Find the downloaded RDP file and double-click it to open.


5. **Enter Your Credentials**:
   - When prompted, enter the username and password you set up earlier.
   - Click **"OK"**.

6. **Confirm the Connection**:
   - If a security warning pops up, click **"Yes"** to proceed.

7. **Voila! Your Virtual Machine is Ready to Go**:
   - Congratulations! Your VM is now open and ready for action!

---
## Check out the demo VM

https://www.linkedin.com/posts/reya-josephine-a871a827b_azure-cloudcomputing-learningjourney-activity-7257066999334281216-4yX_?utm_source=share&utm_medium=member_desktop

And that’s it! You’ve successfully created a Virtual Network and a Virtual Machine in Azure. If you have any questions or run into issues, feel free to ask. Happy cloud computing! ☁️
