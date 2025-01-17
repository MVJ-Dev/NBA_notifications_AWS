# 🏀 NBA Game Day Notifications / Sports Alerts System 📲  

## 🌍 Project Overview  
This project is an alert system that sends real-time NBA game day score notifications to subscribed users via SMS/Email. It leverages **Amazon SNS**, **AWS Lambda**, **Python**, **Amazon EventBridge**, and **NBA APIs** to provide sports fans with up-to-date game information. The system demonstrates cloud computing principles and efficient notification mechanisms. ⚡

---

## 🔑 Features  

- 🏀 Fetches live NBA game scores using the **NBA Game API** (SportsData.io).
- 📲 Sends formatted score updates to subscribers via **SMS**/Email using **Amazon SNS**.
- ⏰ Scheduled automation for regular updates using **Amazon EventBridge**.
- 🔒 Designed with security in mind, following the **least privilege** principle for **IAM roles**.

---

## ⚙️ Technologies  

- ☁️ **Cloud Provider**: **AWS**
- 🔧 **Core Services**: **SNS**, **Lambda**, **EventBridge**
- 🌐 **External API**: **NBA Game API** (SportsData.io)
- 🐍 **Programming Language**: **Python 3.x**
- 🔐 **IAM Security**: Least privilege policies for **Lambda**, **SNS**, and **EventBridge**

---

## 📂 Project Structure 
```plaintext
game-day-notifications/
├── src/
│   ├── gd_notifications.py  # Main Lambda function code
├── policies/
│   ├── gd_sns_policy.json  # SNS publishing permissions
│   ├── gd_eventbridge_policy.json  # EventBridge to Lambda permissions
│   └── gd_lambda_policy.json  # Lambda execution role permissions
├── .gitignore
└── README.md  # Project documentation
```

## **Setup Instructions** 🚀

### **Clone the Repository** 🧑‍💻
```bash
git clone: https://github.com/MVJ-Dev/NBA_notifications_AWS
```
### **Create an SNS Topic** 📣
1. Open the **AWS Management Console**.
2. Navigate to the **SNS service**.
3. Click **Create Topic** and select **Standard** as the topic type.
4. Name the topic (e.g., **gd_topic**) and make a note of the **ARN**.
5. Click **Create Topic** to finalize the setup.

### **Add Subscriptions to the SNS Topic** 📨
1. After creating the topic, click on the topic name from the list.
2. Navigate to the **Subscriptions** tab and click **Create subscription**.
3. Select a **Protocol**:
   - **For Email** 📧:
     - Choose **Email**.
   - **For SMS (phone number)** 📱:
     - Choose **SMS**.
     - Enter a valid phone number.
4. Click **Create Subscription**.

### **Create the SNS Publish Policy** 🛡️
1. Open the **IAM service** in the **AWS Management Console**.
2. Navigate to **Policies → Create Policy**.
3. Click **JSON** and paste the JSON policy from the **gd_sns_policy.json** file.
4. Replace **REGION** and **ACCOUNT_ID** with your AWS region and account ID.
5. Click **Next: Tags** (this step can be skipped).
6. Click **Next: Review**.
7. Enter a name for the policy.
8. Review and click **Create Policy**.

### **Create an IAM Role for Lambda** 🧑‍🔧
1. Open the **IAM service** in the **AWS Management Console**.
2. Click **Roles → Create Role**.
3. Select **AWS Service** and choose **Lambda**.
4. Attach the following policies:
   - **SNS Publish Policy (gd_sns_policy)** (created earlier).
   - **Lambda Basic Execution Role** (**AWSLambdaBasicExecutionRole**) (AWS managed policy).
5. Click **Next: Tags** (optional).
6. Click **Next: Review**.
7. Enter a name for the role (e.g., **gd_role**).
8. Review and click **Create Role**.
9. Copy and save the **ARN** of the role for later use in the Lambda function.

### **Deploy the Lambda Function** 🏗️
1. Open the **Lambda service** in the **AWS Management Console**.
2. Click **Create Function**.
3. Select **Author from Scratch**.
4. Enter the function name (e.g., **gd_notifications**).
5. Choose **Python 3.x** as the runtime.
6. Assign the IAM role (**gd_role**) created earlier to the function.
7. Under the **Function Code** section:
   - Copy the contents of the **src/gd_notifications.py** file from the repository.
   - Paste it into the inline code editor.
8. Under the **Environment Variables** section, add these keys:
   - **NBA_API_KEY**: your NBA API key.
   - **SNS_TOPIC_ARN**: the ARN of the SNS topic created earlier.
9. Click **Create Function**.

### **Configure the EventBridge service** ⏰
1. Navigate to the **EventBridge service** in the **AWS Management Console**.
2. Go to **Rules → Create Rule**.
3. Select **Event Source: Schedule**.
4. Set the cron schedule for updates (e.g., hourly).
5. Under **Targets**, select the **Lambda function (gd_notifications)** and save the rule.

### **Test the System** 🧪
1. Open the **Lambda function** in the **AWS Management Console**.
2. Create a **test event** to simulate the function's execution.
3. Run the function and check **CloudWatch Logs** for errors.
4. Confirm that **SMS notifications** are successfully delivered to the subscribed users.
