# Strata
Mobile application built in AWS

![image](https://user-images.githubusercontent.com/98776682/219730153-426e1d3f-cd12-4270-9897-8d094c6421bc.png)

Integrated using AWS Amplify

Brief Explanation of Backend Services
1. Amazon Cognito: authentication service that stores user login information in a DynamoDB table, and can also provide federated logins, easily connected to front end through AWS Amplify
2. AWS AppSync: Handles GraphQL API calls from front end and sends to lambda resolvers **Note - most steps from API to datastore are typically taken care of by AppSync but regular RDS instances are not natively supported, so manual work was needed
// Next two work concurrently
3. AWS Lambda: Takes the specific API call and translates what is needed into SQL code to either add or retrieve data from the PostreSQL db running on RDS
4. AWS Secrets Manager: Used in conjuction with AWS Lambda to avoid hardcoding db credentials in the function
5. Amazon RDS: PostgreSQL was the chosen relational database
