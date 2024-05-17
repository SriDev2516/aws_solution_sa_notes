# UserData in EC2

## General 

- User Data is generally used to perform common automated configuration tasks and even
  run scripts after the insance starts. 
- Two types
    - shell scripts
    - cloud-init directives
- By default, scripts entered as user data are executed with root privileges. 
    - If you need non-root users to have file access, you should modify the  
      permissions accordingly in the script. 
- By default, user data runs only during the boot cycle when you first launch an 
  instance. 
    - can update configuration to run every time you restart your instance. 
- You **can't change** the user data if the instances is running (even by using root  
  user credentials). But you can view it. 