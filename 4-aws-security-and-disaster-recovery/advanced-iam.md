# Advanced IAM

## Permission Boundary

- Permisison boundary can only be applied to users or roles. 
- A permissions boundary is an advanced feature for using a managed policy to set the 
  maximum permissions that an identity-based policy can grant to an IAM entity. 
- An entity's permissions boundary allows it to perform only the actions that are 
  allowed by both its identity-based policies and its permissions boundaries. 
- Identity based policy with boundaries - Identity-based policies are inline or     
  managed policies that are attached to a user, group of users, or role. Identity-based policies grant permisison to the entity, and permission boundaries limit those permissions. The effective permission are the intersection of both policy types. 

## AWS STS - Security Token Service

- Allows to grant limited and temporary access to AWS resources
- Token valid for up to one hour (must be refreshed)
- STS most important APIs:
    - **AssumeRole**:
        - Usage within our account: for temporary enhanced security
        - Cross account: assume role on target account to perform actions there
    - **AssumeRoleWithSAML**:
        - Return credentials for user logging in with SAML
    - **AssumeRoleWithWebIdentity**:
        - Return credentials for users logged in with IdP (Facebook login, Google login, OIDC)
        - AWS recommends against using this, use Cognito instead
    - **GetSessionToken**:
        - Fro MFA, from an user or AWS account root user

## Using STS to Assume a Role

1. Define an IAM Role within an account or cross-account
2. Define which principals can access this IAM Role
3. Use AWS STS to retrieve credentials and impersonate the IAM Role you have access to (AssumeRole API)
4. Temporary credentials will be valid for 15 minutes up to 1 hour