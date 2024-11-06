# Azure Policy & Policy Definition: Setting Up for Compliance and Control

## Overview

Azure Policy lets you create, assign, and manage policies to enforce specific rules and ensure your resources meet organizational standards. By setting up Azure Policies and Policy Definitions, you can automate compliance checks, standardize resource configurations, and visualize the overall compliance of your Azure environment. This guide provides a step-by-step approach to assign a basic policy and create custom policy definitions.

## Why Use Azure Policy?

- **Enforce Compliance**: Ensure that resources follow your organizational guidelines.
- **Standardize Deployments**: Define configurations like allowed locations for consistency.
- **Automate Monitoring**: Visualize compliance statuses and identify non-compliant resources quickly.

---

## Getting Started: Assigning a Policy in Azure Portal

### 1. Go to the **Azure Portal** 
Log into the [Azure Portal](https://portal.azure.com) to get started.

### 2. Search for **Policy**
In the search bar at the top, type "Policy" and select it from the dropdown to access the Policy dashboard.

![image](https://github.com/user-attachments/assets/f63d1ebc-af2c-4e85-977d-ad44721d651e)


### 3. Assign a New Policy
- Under **Policy**, go to **Compliance** > **Assign Policy**.

![image](https://github.com/user-attachments/assets/f93cbf12-c711-46f3-a069-ee91e2868fc3)

- Choose the scope for which you want to assign the policy.
  
### 4. Select the Policy Definition
- Select a policy definition, such as **Allowed Locations**.

  ![image](https://github.com/user-attachments/assets/a3b7790c-0c6f-45c0-8e11-165b9e8612c8)

  ![image](https://github.com/user-attachments/assets/03da8249-80bc-49d5-b277-0ffea0bc0d7d)


- This policy restricts resource deployment to specified Azure regions.

### 5. Configure Policy Details
- Enter an **Assignment Name** to label this policy (e.g., "Allowed Locations Policy").
- Click **Next** to continue.

### 6. Define Allowed Locations
- Select your desired locations from the dropdown list, specifying where resources can be deployed.

  ![image](https://github.com/user-attachments/assets/ea93ce2b-0a04-4526-9f18-46be3e8058c7)

- Click **Next** > **Review + Create** > **Create**.

### 7. View Compliance Overview
Once created, go to the **Overview** page to see a compliance summary displayed as graphs and pie charts, reflecting the policy's effect across your resources.

![image](https://github.com/user-attachments/assets/f7d284ea-9577-45c5-ab70-e694d1acc467)

![image](https://github.com/user-attachments/assets/e1e62c84-c325-4066-9a4f-df3efd3dfd2b)

![image](https://github.com/user-attachments/assets/fc8ebd7f-c84a-49de-a711-bd5d5961a527)


---

## Creating a Custom Policy Definition

### 1. Go to **Definitions**
Under the **Policy** dashboard, navigate to **Definitions** to create a new custom policy.

### 2. Create a Policy Definition
- Click **+ Policy Definition** to start defining a custom policy.

  ![image](https://github.com/user-attachments/assets/1de47e56-ff1e-49cf-8398-097e89ee2b7c)


### 3. Enter Definition Details
- **Definition Location**: Choose the scope of the policy (e.g., a specific subscription).

  ![image](https://github.com/user-attachments/assets/2e647791-4cd3-48f3-b532-586be1f4aa6c)

- **Category**: Select a category, or use an existing one from the dropdown for easier organization.

  ![image](https://github.com/user-attachments/assets/d672d250-4f1a-4610-a814-5507121cd156)


### 4. Save the Policy Definition
After entering the necessary details, click **Save**. The new policy definition will now appear in the **Definitions** list.

### 5. Review the Custom Policy
View the policy details, including assignment status, scope, and compliance metrics under the **Definitions** page to ensure everything is configured correctly.

---

## Conclusion

Following these steps helps you enforce organizational standards using Azure Policy and Policy Definitions. With these policies in place, you can easily monitor resource compliance, automate corrective actions, and maintain governance across your Azure environment.

---

### Additional Resources
- [Azure Policy Documentation](https://docs.microsoft.com/azure/governance/policy/overview)
- [Azure Policy Samples](https://docs.microsoft.com/azure/governance/policy/samples/)
-Demo video[Azure Policy & Policy Definition: Setting Up for Compliance and Control]()

---

### Example Commands

For CLI or automation, refer to Azure CLI commands or PowerShell scripts in the official documentation.

