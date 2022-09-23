# Important Settings

Here I'm going to list settings in the GPO we should pay close attention to.

## Computer Configuration
### Policies
#### Windows Settings
##### Security Settings
###### Account Policies
- Password Policy
    - Minimum password length

            Set the minimum password length to higher limits. For example, for elevated accounts, passwords should be set to at least 15 characters, and for regular accounts at least 12 characters. Setting a lower value for minimum password length creates unnecessary risk.

        Should be: up to you

    - Maximum password age

        If you set the password expiration age to a lengthy period of time, users will not have to change it very frequently, which means it’s more likely a password could get stolen. Shorter password expiration periods are always preferred.

        Should be: up to you

- Account Lockout Policy
    - Account lockout threshold

        This security setting determines the number of failed logon attempts that causes a user account to be locked out. A locked-out account cannot be used until it is reset by an administrator or until the lockout duration for the account has expired. You can set a value between 0 and 999 failed logon attempts. If you set the value to 0, the account will never be locked out.

        Should be: up to you

###### Local Policies
- Security Options
    - Network security: Do not store LAN Manager hash value on next password change

        Windows generates and stores user account passwords in “hashes.” Windows generates both a LAN Manager hash (LM hash) and a Windows NT hash (NT hash) of passwords. It stores them in the local Security Accounts Manager (SAM) database or Active Directory.

        The LM hash is weak and prone to hacking. Therefore, you should prevent Windows from storing an LM hash of your passwords.

        Should be: Enabled

    - Accounts: Guest Account Status

        Through a Guest Account, users can get access to sensitive data. Such accounts grant access to a Windows computer and do not require a password. Enabling this account means anyone can misuse and abuse access to your systems.

        Thankfully, these accounts are disabled by default. It’s best to check that this is the case in your IT environment as, if this account is enabled in your domain,  disabling it will prevent people from abusing access

        Should be: Disabled

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
