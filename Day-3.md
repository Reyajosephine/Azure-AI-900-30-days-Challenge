# Multiple VMs and Network Security Group (NSG) Setup in Azure

## Overview

This guide will walk you through:
1. Setting up multiple Virtual Machines (VMs) in Azure.
2. Attaching these VMs to a shared Virtual Network (VNet).
3. Configuring a Network Security Group (NSG) to allow ping connectivity between VMs, enabling you to test priority-based security rules.

### What is a Network Security Group (NSG)?

A Network Security Group (NSG) in Azure is a security layer that controls inbound and outbound traffic to resources within a virtual network. By defining custom security rules in an NSG, you can manage traffic flows to and from your VMs, ensuring that only authorized network communication takes place. This guide will show you how to set up NSG rules to allow communication among multiple VMs, giving you control over the network priority and traffic flow.

---

### Create Multiple VMs in Azure

1. **Log into the Azure portal**: [https://portal.azure.com](https://portal.azure.com).
2. **Go to Virtual Machines**:
   - Select **Create VM** and configure the details as outlined in the [VM setup guide](https://github.com/Reyajosephine/Azure-30-days-Challenge/blob/main/Day-1.md).
   - Repeat the process to create multiple VMs in the same Virtual Network for ease of communication.
   
### Set Up a Network Security Group (NSG)

1. **Navigate to Network Security Groups** in the Azure portal.
   ![Screenshot 2024-10-31 223433](https://github.com/user-attachments/assets/3be21e80-7a10-453c-90dd-44ad316d078a)

2. Click on **+Create** to create a new NSG:
   ![Screenshot 2024-10-31 223507](https://github.com/user-attachments/assets/556b97f1-2167-42e4-b4bf-ba58209892f7)

   - Fill in the **Name** and **Resource Group**, then select **Create**.
     ![Screenshot 2024-10-31 223636](https://github.com/user-attachments/assets/25772c3e-3ce7-44ef-bfed-315a81dda955)


### Configure NSG Rules for Ping Connectivity

1. **Open the newly created NSG** and go to **Inbound security rules**.
   ![Screenshot 2024-10-31 223808](https://github.com/user-attachments/assets/c017e85a-9a8c-4d2d-a176-057b70088b5a)
   ![Screenshot 2024-10-31 223852](https://github.com/user-attachments/assets/b3c070ad-9390-4eb6-b82e-5a9d8ab097b1)


3. **Add a New Inbound Rule**:
   ![Screenshot 2024-10-31 223927](https://github.com/user-attachments/assets/e32dcc02-ee1e-40cb-884e-578f5e93fa5a)

   - Set **Source** to "Virtual network" to include traffic within the VNet.
   - Set **Destination** to "Virtual network" to target the same network.
   - Set **Protocol** to "ICMP" (this allows ping traffic).
   - Use "*" for **Source port ranges** and **Destination port ranges** to allow all ports.
   - Set the **Priority** (for example, `100`). Note: Lower priority numbers are processed first.
    
4. Click **Add** to apply the rule.

5. **Repeat for Outbound Rules**:
   - Go to **Outbound security rules** in the NSG.
    ![Screenshot 2024-10-31 224013](https://github.com/user-attachments/assets/89f55126-710e-4cfc-8976-f2c3abe1a298)

   - Follow the same steps as above to allow outbound ICMP traffic, enabling VM-to-VM pings.

### Testing VM Connectivity with NSG Priority Rules

1. To observe how rule priority works, try adding additional rules with varied **Priority** values.
   - Higher-priority (lower-numbered) rules override lower-priority (higher-numbered) ones.
2. Test connectivity by pinging between VMs to verify that only the desired traffic is permitted based on your rules.

---

### Important Notes
- Ensure that the VMs are in the same Virtual Network to allow NSG rules to apply effectively.
- Attach the NSG to the specific subnet in the Virtual Network where the VMs are located for maximum connectivity.

Using this setup, your VMs should now be able to securely communicate within the network, with traffic controlled by your NSG rules.
For more details, refer back to the [VM Creation Guide](https://github.com/Reyajosephine/Azure-30-days-Challenge/blob/main/Day-1.md). Click here for Demo video [Multiple VMs and Network Security Group (NSG) Setup in Azure](https://www.linkedin.com/posts/reya-josephine-a871a827b_azure-networksecurity-cloudcomputing-activity-7257805409367793666-Q1qD?utm_source=share&utm_medium=member_desktop)
