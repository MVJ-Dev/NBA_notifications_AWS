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

## 🗂️ Project Structure  
game-day-notifications/
├── src/
│   ├── gd_notifications.py          # Main Lambda function code
├── policies/
│   ├── gb_sns_policy.json           # SNS publishing permissions
│   ├── gd_eventbridge_policy.json   # EventBridge to Lambda permissions
│   └── gd_lambda_policy.json        # Lambda execution role permissions
├── .gitignore
└── README.md                        # Project documentation
