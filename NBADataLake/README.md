# NBADataLake
*Automated NBA data analytics using AWS S3, Glue, and Athena.*

## Overview
This project automates the creation of a data lake for NBA analytics using AWS services:
- **Amazon S3**: Stores raw and processed NBA data.
- **AWS Glue**: Catalogs data and manages schema.
- **Amazon Athena**: Queries the stored NBA data efficiently.

### Key Features
- Automates setup for data ingestion and querying.
- Fetches live NBA data using SportsData.io API.
- Demonstrates best practices in cloud architecture and IAM security.

## Prerequisites

### API Access
1. Create a free account at [SportsData.io](https://sportsdata.io/).
2. Navigate to *Developers > API Resources* and select "NBA".
3. Copy your API key from the "Query String Parameters" section.

### AWS Setup
- IAM Role/Permissions:
  - **S3**: `CreateBucket`, `PutObject`, `DeleteBucket`, `ListBucket`
  - **Glue**: `CreateDatabase`, `CreateTable`, `DeleteDatabase`, `DeleteTable`
  - **Athena**: `StartQueryExecution`, `GetQueryResults`

## Getting Started

### Step 1: Configure AWS CLI
1. Install AWS CLI:
   ```bash
   pip install awscli
   ```
2. Configure AWS credentials:
   ```bash
   aws configure
   ```
   Provide your **Access Key**, **Secret Key**, and **Default Region**.

### Step 2: Set Up Python Script
1. Create the `setup_nba_data_lake.py` file:
   ```bash
   nano setup_nba_data_lake.py
   ```
2. Copy the script content from [GitHub](https://github.com/jenmagruder/NBADataLake) and paste it into the file.
3. Add your API key under the `api_key` variable in the script.
4. Save and close the file.

### Step 3: Create `.env` File
1. Create an environment file:
   ```bash
   nano .env
   ```
2. Add your API key and endpoint:
   ```env
   SPORTS_DATA_API_KEY=your_api_key
   NBA_ENDPOINT=https://api.sportsdata.io/v3/nba/scores/json/Players
   ```
3. Save and close the file.

### Step 4: Run the Script
Execute the script to set up the data lake:
```bash
python3 setup_nba_data_lake.py
```
- Verify successful creation of resources in the console output.

## Verifying the Setup

### 1. Check S3 Buckets
- Navigate to S3 in AWS Management Console.
- Confirm the creation of `Sports-analytics-data-lake` bucket.
- Verify `raw-data/nba_player_data.json` exists in the bucket.

### 2. Query Data with Athena
- Navigate to Amazon Athena.
- Use this query to test the setup:
  ```sql
  SELECT FirstName, LastName, Position, Team
  FROM nba_players
  WHERE Position = 'PG';
  ```
- Confirm query results are displayed.

## What We Learned
- **IAM Security**: Applied least privilege for roles and policies.
- **Automation**: Scripted resource creation for efficiency.
- **Data Integration**: Integrated external APIs with AWS workflows.

## Future Enhancements
1. Automate data ingestion with **AWS Lambda**.
2. Transform data using **AWS Glue ETL**.
3. Add visual analytics using **AWS QuickSight**.
4. Integrate team-specific subscriptions for tailored alerts.

## License
This project is intended for educational purposes only. Use of NBA data must comply with [SportsData.io](https://sportsdata.io/) terms and conditions.

---
**Disclaimer:** The NBA and associated trademarks are the property of the National Basketball Association. This project is not affiliated with or endorsed by the NBA.