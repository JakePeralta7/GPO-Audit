# Understanding The GPO Structure

The GPO is divided to two, User Configuration and Computer Configuration

## GPO Assignment
- A GPO can be associated (linked) to one or more Active Directory containers.

- Multiple containers can be linked to the same GPO, and a single container can have more than one GPO linked to it. 

- If multiple GPOs are linked to one container, you can prioritize the order in which GPOs are applied.

## GPO Inheritence
By default, Group Policy is inherited and cumulative, and it affects all computers and users in an Active Directory container.

GPOs are processed in the following order:

1. The local GPO is applied.
2. GPOs linked to sites are applied.
3. GPOs linked to domains are applied.
4. GPOs linked to organizational units are applied. For nested organizational units, GPOs linked to parent organizational units are applied before GPOs linked to child organizational units are applied.

The last GPO to be applied is the first to try and solve a conflict (different explicit settings)

## GPO Processing
### Initial Processing
For computers, Group Policy is applied when the computer starts. For users, Group Policy is applied at log on.

### Background Refresh
In addition to the initial processing of Group Policy when the computer starts and when the user logs on, the system periodically applies (refreshes) Group Policy in the background.

By default, a refresh occurs every 90 minutes. The system may add a random time of up to 30 minutes to the refresh interval. You can change these default values by using a Group Policy setting in the Administrative Templates extension to Group Policy. Setting the value to zero minutes causes the refresh rate to be set to seven seconds.

## View Effective Group Policy
In a standard network, overtime understanding the GPO structure can become next to impossible (lots of gpo, lots of conflicting assignment)

So, in order to check which Effective GPO a specific combination of user and computer will get I wrote a PowerShell script (need to be run on computer with gpm mmc installed)
```powershell
# Constants
$outputFile = “C:\TempGPOExport.html”
$computerName = "COMPUTER-NAME.domain.local"
$userName = "exapmle_user"

$gpm = New-Object -ComObject GPMgmt.GPM
$constants = $gpm.GetConstants()
$gpmRSOP = $GPM.GetRSOP($Constants.RSOPModeLogging,$null,0)
$gpmRSOP.LoggingComputer = $computerName
$gpmRSOP.LoggingUser = $userName
$gpmRSOP.LoggingFlags = $Constants.RsopLoggingNoUser
$gpmRSOP.CreateQueryResults()

# Exporting in HTML format
$gpmRSOP.GenerateReportToFile($constants.ReportHTML,$outputfile)
```