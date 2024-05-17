# AWS Cognito

- Cognito is used for givin users an identity in oder to being able to communicate with a system
- Cognito offers 3 products:
    - **Cognito User Pools:**
        - Sign in functionality for the app users
        - Integrates with API Gateway
    - **Cognito Identity Pool (Federated Identity):**
        - Provides AWS credentials to users which want to access AWS resources directly
        - Integrates with Cognito User Pools as an identity provider
    - **Cognito Sync:**
        - Used for synchronize data from a device to Cognito
        - Deprecated, replaced by AppSync

## AWS Cognito User Pools

- It is a serverless database for users of an application
- it is a simple login provider: username (or email) / password combination
- Possibility to verify emails/phone numbers and add MFA
- Can enable Federated Identities (Facebook, Google, SAML, etc.). **This is not the same CIP (AWS Federated Identity)!**
- Sends back a JSON Web Token (JWT)
- Can be integrated with API Gateway for authentication

## AWS Cognito Federated Identity Pools

- Goal:
    - Provide direct access to AWS resources from the client side
- How:
    - Log in to a federated identity provider - or remain anonymous
    - Get temporary AWS credentials from the Federated Identity Pool
    - These credentials come with pre-defined IAM policies stating their permissions
- Examples:
    - Provide temporary access to write to a S3 bucket using Facebook login

## AWS Cognito Sync

- Deprecated - use AWS AppSync
- Can be used for cross device synchronization from any platform: iOS, Android, etc.
- It provides some offline capabilities, synchronization will happen when the device will come online
- **Requires Federated Identity Pool in Cognito (not User Pool!)**
- Data is stored in datasets, each dataset can have up to 1MB of data. We can have up to 20 datasets to synchronize


## Difference between Amazon Cognito User Pools and Amazon Cognito Identity Pools:

### User Pools

    - A user pool is a user directory in Amazon cognito. With a user pool, your users can sign in to your web or mobile app 
      throuh Amazon Cognito or federated through a third-party identity provider (IDP)
    - Whether your users sign in directly or through a third party, all members of the user pool have a directory profile 
      that you can access through an SDK

### Identity Pools

    - With an Identity pool, your users can obtain temporary AWS credentials to access AWS services, such as Amazon S3 and 
      DynamoDB