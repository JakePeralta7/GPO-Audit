# Important Settings

Here I'm going to list settings we should pay close attention to

## Computer Configuration
### Windows Settings
#### Security Settings
##### Local Policies
###### Security Options
- Network security: Do not store LAN Manager hash value on next password change

    Windows generates and stores user account passwords in “hashes.” Windows generates both a LAN Manager hash (LM hash) and a Windows NT hash (NT hash) of passwords. It stores them in the local Security Accounts Manager (SAM) database or Active Directory.

    The LM hash is weak and prone to hacking. Therefore, you should prevent Windows from storing an LM hash of your passwords