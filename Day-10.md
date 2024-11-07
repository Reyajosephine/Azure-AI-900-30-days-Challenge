# Setting Up Azure Alert Notifications with Action Groups and Alert Rules

In Azure, you can set up alerts to notify you about key events and resource changes. By creating **Action Groups** and **Alert Rules**, you can receive notifications via email, SMS, push, or voice. Here’s a quick guide on how to configure them in the Azure portal.

---

## Step 1: Create an Action Group

1. **Go to the Azure Portal** and navigate to **Monitor** from the left menu.
2. Under **Monitor**, select **Alerts**.
3. Click **Create > Action Group** to start setting up your notifications.

![image](https://github.com/user-attachments/assets/e5bd741a-0d3c-470d-82f5-e764fa820988)


4. **Configure Action Group Settings**:
   - Choose the **Subscription** and **Resource Group**.
   - Select the **Region** where you want this Action Group to be located.
   - Enter a **Name** and **Display Name** for the Action Group.

     ![image](https://github.com/user-attachments/assets/dce16b33-3a53-486a-bef2-8f19a2289b79)


5. **Add Notifications**:
   - Select the **Notification Type** you want to use (Email, SMS, Push, or Voice).
     
     ![image](https://github.com/user-attachments/assets/12b3194e-e4ef-4794-900d-aefd67b6cac2)

   - Enter the required details for each notification type and click **OK**.
   - Give your notification a **Name** to easily identify it later.

6. **Review + Create**:
   - Once all fields are filled in, click **Review + Create** and then **Create** to deploy your Action Group.

---

## Step 2: Create an Alert Rule

1. In the **Azure Portal**, go back to **Monitor** and select **Alerts**.
2. Click **Create > Alert Rule** to set up an alert.

![image](https://github.com/user-attachments/assets/eb5aed18-1c9a-4b8d-bb04-73ab85d0ce8e)


3. **Select Target and Signal**:
   - Choose the **Action Group** you just created in the **Action Group** section.
     
     ![image](https://github.com/user-attachments/assets/c6f6b3af-e598-456c-bb88-f73d40c2978c)

   - Set **Signal Name** to **All Administrative Operations** (or select another relevant option as per your requirements).

     ![image](https://github.com/user-attachments/assets/98434f02-610c-457d-9372-33cdb3ed17eb)

   - View the **chart** to monitor the selected metric in real time.

     ![image](https://github.com/user-attachments/assets/1ec70843-53e1-41ff-8331-7abc222b015f)

     
    

4. **Configure Actions**:
   - In the **Actions** section, select the **Action Group** you created earlier.

     ![image](https://github.com/user-attachments/assets/870b6e8a-9f18-4b0d-8325-c79802a216b1)


5. **Review + Create**:
   - Click **Review + Create**, then **Create** to finalize the alert rule.

---

## Step 3: Verify Your Notifications

- Check your email or the selected notification type to ensure you’re receiving alerts as expected.

  ![image](https://github.com/user-attachments/assets/7362d246-5ac6-4e63-896e-a04b12549d5c)


---

> ### Note
> With this setup, you’ll receive real-time notifications for key administrative operations, keeping you updated on resource changes or issues.

---

## Additional Resources
- For more details on Azure Alerts, visit the [Azure Alerts Documentation](https://learn.microsoft.com/azure/monitoring/).
- Click here for demo video [Setting Up Azure Alert Notifications with Action Groups and Alert Rules](https://www.linkedin.com/posts/reya-josephine-a871a827b_azurealerts-realtimemonitoring-azurecloud-activity-7260356193716510721-8iSC?utm_source=share&utm_medium=member_desktop)

