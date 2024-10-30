# Azure Virtual Machine & Network Setup Guide

## Introduction

In Azure, a **Network Interface Card (NIC)** is essential for connecting your Virtual Machine (VM) to your network. It enables communication with other resources in a Virtual Network (VNet). Adding multiple NICs to a VM is useful if you want to connect it to different network segments or route traffic for specific needs.

A **Subnet** is a subdivision within a Virtual Network, allowing you to organize and secure your resources. Setting up private and public subnets can help control access, enabling certain resources to remain isolated from external access while others are accessible from the internet.

This guide will walk you through creating a VM, attaching additional NICs, and setting up private and public subnets to optimize your Azure environment. Let’s dive in!

---

## Steps

### 1. Create a Virtual Machine

To create a Virtual Machine, follow the detailed steps provided in the [VM Creation Guide](https://github.com/Reyajosephine/Azure-30-days-Challenge/blob/main/Day-1.md). This file outlines all setup instructions for your VM.

---

### 2. Attach Additional Network Interface Cards (NICs)

1. **Set Up Your VM Network Configuration**:
   - Complete the VM setup as described in the [VM Creation Guide](https://github.com/Reyajosephine/Azure-30-days-Challenge/blob/main/Day-1.md).

2. **Attach Additional NICs**:
   - In your VM's **Network settings**, select **"Attach network interface"**.
     ![image](https://github.com/user-attachments/assets/3b359596-6fe3-4f27-a7e3-5e8ef3910c4c)


   - **Sample Configuration**:
     - **NIC Name**: `MySecondNIC`
     - **IP Configuration**: `10.0.1.4` (assuming your VM's main NIC is on `10.0.0.4`)
     - **Subnet**: `PublicSubnet` (for internet-facing NIC)
     - **VNet**: `MyVNet`

   - Click **"Create"** to attach the NIC. Your VM will now be connected to both its original NIC and the new NIC, each with its own IP and subnet.
   - You can find your NIC by searching for **"NIC"** on the search bar.
    ![image](https://github.com/user-attachments/assets/2835d6eb-7fbd-4d05-bfd0-659a1d2d19fc)


---

### 🛠️ Steps to Create Private and Public Subnets in a VNet

1. **Navigate to the VNet**:
   - On the Azure portal’s home page, go to **Virtual Networks**, find and open your VNet (e.g., `MyVNet`).
     ![image](https://github.com/user-attachments/assets/324af620-8ec5-4202-9849-51b847a49165)


2. **Add Subnets**:
   - In **Settings** → **Subnets**, you can add both private and public subnets.
     ![image](https://github.com/user-attachments/assets/c23b5734-c8ac-4769-926d-c1b6643b805f)


   - **Sample Configurations**:

     - **Private Subnet**:
       - **Name**: `PrivateSubnet`
       - **Address Range**: `10.0.1.0/24`
       - **Assign Public IP**: **No**
       - **VNet**: `MyVNet`
     
     - **Public Subnet**:
       - **Name**: `PublicSubnet`
       - **Address Range**: `10.0.2.0/24`
       - **Assign Public IP**: **Yes**
       - **VNet**: `MyVNet`
    ![image](https://github.com/user-attachments/assets/d3c4fa88-4152-4b78-9662-fb20dfe689c5)


   - Click **"Create"** for each subnet. This creates one subnet (`PrivateSubnet`) isolated from the internet and one (`PublicSubnet`) with internet access.
    ![image](https://github.com/user-attachments/assets/8bf75251-1aff-45ca-a783-8c12ebbf23d1)


---

This setup lets your VM access both internal resources via the private subnet and external resources via the public subnet, enabling you to securely manage and expand your Azure network configuration.

For more details, refer back to the [VM Creation Guide](https://github.com/Reyajosephine/Azure-30-days-Challenge/blob/main/Day-1.md).
