🏀 NBA Game Day Notification System 📲

📝 Project Overview
This project implements a real-time NBA game score alert system that sends updates to users via SMS/Email. The system leverages AWS Lambda, Amazon SNS, EventBridge, Python, and the NBA API to deliver timely game information. It demonstrates cloud architecture and efficient event-driven notification mechanisms.

🌐 Technologies
Cloud Platform: AWS ☁️
Core AWS Services: SNS, Lambda, EventBridge
External API: NBA Game API (SportsData.io) 🏀
Programming Language: Python 3.x 🐍
IAM Security:
Enforced least privilege policies for Lambda, SNS, and EventBridge 🔒

🗂️ Project Structure
game-day-notifications/
├── src/
│   ├── gd_notifications.py          # Main Lambda function code
├── policies/
│   ├── gb_sns_policy.json           # SNS publishing permissions
│   ├── gd_eventbridge_policy.json   # EventBridge to Lambda permissions
│   └── gd_lambda_policy.json        # Lambda execution role permissions
├── .gitignore
└── README.md                        # Project documentation


