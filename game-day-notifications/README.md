# NBA Game Day Notifications / Sports Alerts System

# Project Objective
This project provides real-time NBA game updates via SMS/Email using AWS services and the NBA API. It demonstrates the integration of cloud technologies, external APIs, and automation to deliver timely notifications to subscribed users.

## *Features*
- Real-Time Updates: Fetch live NBA game scores from the NBA API.
- Notifications: Send updates via SMS or email using Amazon SNS.
- Scheduled Updates: Automate notifications using AWS EventBridge.
- Secure and Scalable: Implements IAM security best practices and leverages AWS's scalable 
  architecture.

## *Prerequisites*
- Acounts Required:    
    - AWS: For Lambda, SNS, and Eventbridge setup.
    - SportsData.io: To obtain the NKA API key.
- Technologies:
    - Python 3.x: For Lambda function development.
    - AWS CLI (optional): To manage AWS resources programmatically.

## *Architecture Overview*
External API (NBA API) → Lambda → SNS → End Users (SMS/Email)
EventBridge scheduling Lambda executions.

## *File Structure*
Organize the project's files and explain their purpose.

nba-notifications/
├── src/
│   ├── nba_notifications.py          # Main Lambda function code
├── policies/
│   ├── sns_policy.json               # SNS publish permissions
│   ├── eventbridge_policy.json       # EventBridge permissions
│   └── lambda_policy.json            # Lambda execution permissions
├── .gitignore
├── README.md                        # Project documentation
└── LICENSE                          # License information

## *Step-by-Step Setup Instructions*
- Step 1: Clone the Repository
    git clone https://github.com/jenmagruder/game-day-notifications.git
    cd game-day-notifications
- Step 2: Configure AWS Resources
- Create an SNS Topic:
    Navigate to AWS SNS in the console.
    Create a topic and note the ARN.

- Set Up IAM Roles:
    Create policies using the JSON files in policies/.
    Attach these policies to a role for Lambda.
    Deploy the Lambda Function:

- Use the AWS Console or CLI to upload nba_notifications.py.
    Configure environment variables for the NBA API key and SNS Topic ARN.
    Automate with EventBridge:

- Set up a schedule in EventBridge to trigger the Lambda function periodically.

## *Usage*
- Testing
    Create a test event in the AWS Lambda Console.
    Run the function and confirm notifications are sent.
    Verify logs in CloudWatch for troubleshooting.
- Running the Project
    Add subscriptions (SMS/Email) to your SNS Topic.
    Trigger the Lambda function manually or wait for the scheduled automation to run.

## *Security*
- IAM Principles:
    Policies use the Principle of Least Privilege.
    Ensure roles only have access to necessary resources.
- API Key Storage:
    API keys are stored securely using environment variables.

## *Lessons Learned*
- Practical experience with AWS services (SNS, Lambda, EventBridge).
- Integration of third-party APIs in cloud environments.
- Automating workflows with serverless technologies.
- Managing security and scalability in cloud projects.

## *Future Enhancements*
Personalization:

Allow users to subscribe to specific teams or game types.
Use DynamoDB to store user preferences.
Multi-Sport Alerts:

Extend notifications to other sports like NFL, MLB, etc.
Web Interface:

Build a UI for subscription management and notifications history.
