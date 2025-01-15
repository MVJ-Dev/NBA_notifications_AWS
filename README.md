# 🌧️ 30 Days DevOps Challenge - Weather Dashboard 🚀  
**Day 1: Building a Weather Data Collection System with AWS S3 & OpenWeather API**

---

## 🌍 Project Overview  

This project is part of the **30 Days DevOps Challenge** and aims to create a **Weather Data Collection System** using cloud technologies. The system fetches live weather data and stores it securely using **AWS S3**.

It integrates:
- 🌦️ **OpenWeather API** for real-time weather data collection
- ☁️ **AWS S3** for cloud storage
- 🛠️ **Infrastructure as Code** using Python
- 🐍 **Python Development**
- 📁 **Version Control** with Git
- 🔒 **Error Handling** and **Environment Management**

---

## 🔑 Key Features  

- 🏙️ Fetches real-time weather data using **OpenWeather API**  
- 💾 Automatically stores weather data in **AWS S3** for reliable cloud storage  
- 🌍 Allows tracking of multiple cities with real-time updates  
- 🔒 Built with **security best practices** using **IAM roles**  

---

## 🛠️ Technologies  

- ☁️ **Cloud Provider**: AWS  
- 🔑 **Core Services**: SNS, Lambda, EventBridge  
- 🌍 **External API**: OpenWeather API  
- 🐍 **Programming Language**: Python 3.x  
- 🔒 **IAM Security**: Least privilege policies for Lambda, SNS, and EventBridge

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
