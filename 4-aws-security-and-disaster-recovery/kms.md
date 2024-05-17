# KMS

## Multi Region Keys in AWS KMS

- AWS KMS supports multi-region keys, which are AWS KMS keys in different AWS regions
  that can be used interchangeably - as though you had same key in multiple regions. 
- You can encrypt data in one region and decrypt it in a different AWS region without
  re-encrypting or making a cross region call to AWS KMS. 
- Amazon- S3 currently trwats multi-region keys as though they were single-region keys 
  and does not use the multi-region features of the key. 
- You cannot convert an existing single-region key to a multi-region key. 


