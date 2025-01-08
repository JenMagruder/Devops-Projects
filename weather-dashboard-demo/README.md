# 30 Days DevOps Challenge - Weather Dashboard

Day 1: Building a weather data collection system using AWS S3 and OpenWeather API

# Weather Data Collection System - DevOps Day 1 Challenge

## Project Overview
# Weather Dashboard with AWS S3 Integration
The Weather Dashboard is a Python-based project that fetches real-time weather data for specified cities using the OpenWeather API and securely stores it in AWS S3. The project demonstrates integration between APIs and cloud services, focusing on automation, scalability, and data organization.

## Features
- Fetches real-time weather data for multiple cities
- Displays temperature (°F), humidity, and weather conditions
- Automatically creates an s3 bucket and stores weather data in AWS S3
- Supports multiple cities tracking
- Timestamps all data for historical tracking
- Provide clear error handling for API and AWS operations.

## Technical Architecture
- **Language:** Python 3.x
- **Cloud Provider:** AWS (S3)
- **External API:** OpenWeather API
- **Dependencies:** 
  - boto3 (AWS SDK)
  - python-dotenv
  - requests

```markdown
## Project Structure
weather-dashboard/
  src/
    __init__.py
    weather_dashboard.py
  tests/
  data/
  .env
  .gitignore
  requirements.txt

## Setup Instructions
1. Clone the repository:
--bash
git clone https://github.com/JenMagruder/devops-projects/weather-dashboard-demo.git

3. Install dependencies:
bashCopypip install -r requirements.txt

4. Configure environment variables (.env):
CopyOPENWEATHER_API_KEY=your_api_key
AWS_BUCKET_NAME=your_bucket_name

4.Configure AWS credentials:
bashCopyaws configure

5. Run the application:
python src/weather_dashboard.py

6. Outputs: 
-Console: Displays weather information (e.g., temperature, humidity, conditions).
-S3 Bucket: Saves JSON files with city-specific weather data.

weather-dashboard/
├── main.py          # Main script to run the project
├── requirements.txt # Dependencies
├── .env             # Environment variables (not included in the repo)
├── README.md        # Project documentation

What I Learned

AWS S3 bucket creation and management
Environment variable management for secure API keys
Python best practices for API integration
Git workflow for project development
Error handling in distributed systems
Cloud resource management

Future Enhancements

Add weather forecasting for multiple weather APIs
Implement data visualization
Add more cities
Create automated testing
Set up CI/CD pipeline
Automate periodic weather data collection using AWS Lambda and CloudWatch
