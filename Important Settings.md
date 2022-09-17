# Important Settings

Here I'm going to list settings in the GPO we should pay close attention to.

## Computer Configuration
### Windows Settings
#### Security Settings
##### Local Policies
###### Security Options
- Network security: Do not store LAN Manager hash value on next password change

    Windows generates and stores user account passwords in “hashes.” Windows generates both a LAN Manager hash (LM hash) and a Windows NT hash (NT hash) of passwords. It stores them in the local Security Accounts Manager (SAM) database or Active Directory.

    The LM hash is weak and prone to hacking. Therefore, you should prevent Windows from storing an LM hash of your passwords.

    Should be: Enabled
## User Configuration
### Policies
#### Windows Settings
#### Administrative Templates
##### System
- Prevent access to the command prompt

    Command Prompts can be used to run commands that give high-level access to users and evade other restrictions on the system. So, to ensure system resources’ security, it’s wise to disable Command Prompt.

    After you have disabled Command Prompt and someone tries to open a command window, the system will display a message stating that some settings are preventing this action.

    Should be: Enabled
###### Removable Storage Access
- All removable storage classes: Deny all accesses

    Removable media drives are very prone to infection, and they may also contain a virus or malware. If a user plugs an infected drive to a network computer, it can affect the entire network. Similarly, DVDs, CDs and Floppy Drives are prone to infection.

    Removable media drives can also bu used for data exfiltration.

    It is therefore best to disable all these drives entirely.
    
    Should be: Enabled