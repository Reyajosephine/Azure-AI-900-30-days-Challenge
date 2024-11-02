# Hosting a Static Website on Azure Blob Storage

## Introduction

Want to share your website with the world? Hosting a static site, made up of HTML, CSS, and JavaScript, on **Azure Blob Storage** is a quick, affordable solution! Whether it’s a personal portfolio, product landing page, or small business site, Azure Blob Storage lets you host your site with ease. Let’s walk through how to set it up.

---

## Steps to Get Your Static Website Online

### **Step 1:** Log into Azure
   - Head over to the [Azure portal](https://portal.azure.com) and sign in.

### **Step 2:** Create a Storage Account
1. On the Azure homepage, select **"Create a resource"**.

![image](https://github.com/user-attachments/assets/069f4d78-c18d-4a74-b28f-75df066e18e2)

2. Type in **"Storage account"** and select it from the list.

![image](https://github.com/user-attachments/assets/ac7b02d6-08dc-45c7-bde8-64b7a478c52e)

3. Click **"Create"** to start the setup.

![image](https://github.com/user-attachments/assets/11da3c74-bf89-4c82-8503-7ac706c0a04b)


### **Step 3:** Configure Your Storage Account
1. **Subscription**: Choose your **Subscription**.
2. **Resource Group**: Either select an existing **Resource Group** or create a new one.

![image](https://github.com/user-attachments/assets/2b623fc3-ccc0-4992-bc0f-4f048b650d4b)

4. **Storage Account Name**: Enter a unique **name** for your storage account (all lowercase).

![image](https://github.com/user-attachments/assets/4452a2b5-c123-4e43-b158-016f855d5329)

5. **Region**: Pick a **Region** close to where most visitors will be for faster loading.
6. **Performance**: “Standard” works great for most static sites.
7. **Redundancy**: Choose **Locally-redundant storage (LRS)** for cost savings, or another option if you need higher redundancy.

   After filling everything in, hit **"Review + Create"**, then **"Create"** and let Azure deploy the account.

![image](https://github.com/user-attachments/assets/793a6e42-0937-4159-8d21-b45647024746)


### **Step 4:** Enable Static Website Hosting
1. Click **Go to resource**.

![image](https://github.com/user-attachments/assets/d828f8a7-50e6-4432-8306-ea3c3952d9cc)

2. In your new storage account, go to **Data Management** and find **Static website**.

![image](https://github.com/user-attachments/assets/60f91af2-9ff8-4094-9f76-57efb444fdd1)

  
3. Switch **Static website** to **Enabled**.
4. Set **Index document name** to `index.html` (or whatever your main HTML file is).
5. (Optional) Add a custom **404.html** file for broken links.
6. Click **Save**.

![image](https://github.com/user-attachments/assets/17a16301-6832-4a02-a5ae-f07d5a9444a5)


### **Step 5:** Upload Your Website Files
1. Go to **Data storage** > **Containers** in your storage account.
2. Open the **$web** container (this was created automatically when we enabled website hosting).

![image](https://github.com/user-attachments/assets/1b4ddc29-66fa-4d5e-bf15-820f410ecd23)

3. Click **Upload** and select all your website files (HTML, CSS, JavaScript, images).

### **Step 6:** Access Your Website
1. Go back to the **Static website** settings in your storage account.
2. Copy the **Primary endpoint** URL.
3. Paste it into your browser, and voilà—your site is live!

---

## Tips
- **Public Access**: Make sure the **$web** container has public access enabled so visitors can view your site.
- **Organize Files**: Use folders to keep things organized, like putting images or stylesheets in separate subfolders.

That’s it! Your static website is now online via Azure Blob Storage. If you want faster load times globally, you can look into Azure CDN integration later. Happy hosting!
**Click here for Demo Video** [Hosting a Static Website on Azure Blob Storage](https://www.linkedin.com/posts/reya-josephine-a871a827b_azure-cloudcomputing-staticweb-activity-7258189056616890368-d53z?utm_source=share&utm_medium=member_desktop)
