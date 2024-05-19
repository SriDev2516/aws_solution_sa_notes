# KMS

## KMS Keys Types

- Symmetric (AES-256 keys)
   - Single key used to Encrypt and Decrypt
   - You never get access to the KMS Key unencrypted (must call KMS API to use)
- Asymmetric (RSA & ECC key pairs)
   - Public (Encrypt) and Private Key (Decrypt) pair
   - Public key is downloadable, but cannot access the Private Key
   - Use Case: encyption outside of AWS by users who can't call the KMS API


## Automatic Key rotation:

- AWS manageed KMS Key: automatic every 1 year
- Custoer-manager KMS key: (must be enabled) automatic every 1 year
- Imported KMS key: only manual rotation possible using alias
    - Manual Rotation Steps:
        - Create a new key
        - Import the new keys into AWS KMS
        - Update the alias to point the new key
    - Alias Usage:
        - Aliases provide a friendly name for KMS keys
        - Changing the alias to the new key allows applications to use the updated key 
          without modifying configuration. 
    - Manual rotation requires more effort and careful management compared to the 
      automatic rotation of AWS-created keys. 


## Multi Region Keys in AWS KMS

- AWS KMS supports multi-region keys, which are AWS KMS keys in different AWS regions
  that can be used interchangeably - as though you had same key in multiple regions. 
- You can encrypt data in one region and decrypt it in a different AWS region without
  re-encrypting or making a cross region call to AWS KMS. 
- Amazon- S3 currently trwats multi-region keys as though they were single-region keys 
  and does not use the multi-region features of the key. 
- You cannot convert an existing single-region key to a multi-region key. 


