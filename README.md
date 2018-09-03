# Pre-requisite:

Follow this guide to deploy Hasura GraphQL (on EC2) on RDS:
https://blog.hasura.io/instant-graphql-on-aws-rds-1edfb85b5985

# Setup our tables
1. Create table: `notes`: `id: int, primary_key`, `note: text`

# Setup now cli
1. Create zeit account @ https://zeit.co/
2. Download now cli from https://zeit.co/download#now-cli
3. Login using now Login

# Setup echo serverless function
1. cd echo
2. edit now.json to change app and alias name (Note: alias will be the domain for example setting alias to hge-events-zeit-node-echo will provide hge-events-zeit-node-echo.now.sh)
3. Deploy the function by running `now && now alias && now remove <app-name> --safe -y`

# Add events in Hasura GraphQL

1. In events tab, add a trigger
2. Select all insert, update, delete operations for the trigger.
3. Paste the API endpoint of your AWS lambda as the webhook.
