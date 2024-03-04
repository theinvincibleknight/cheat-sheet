# PowerShell
Cross-platform command-line interface and scripting language for system and network administration


## PowerShell commands related to managing files

Get-Command: Retrieves all commands in the current session.
```PowerShell
Get-Command
```
Get-Help: Provides help for commands.
```PowerShell
Get-Help Get-Command
```
Get-Process: Retrieves information about processes.
```powershell
Get-Process
```
Get-Service: Retrieves information about services.
```powershell
Get-Service
```
Get-Item: Retrieves information about items in a namespace.
```powershell
Get-Item C:\Path\To\File.txt
```
Get-ChildItem: Retrieves the items and child items in one or more specified locations.
```powershell
Get-ChildItem C:\Path\To\Folder
```
Set-Item: Changes the value of an item.
```powershell
Set-Item -Path variable:\myVar -Value "New Value"
```
New-Item: Creates a new item.
```powershell
New-Item -ItemType File -Path C:\Path\To\NewFile.txt
```
Remove-Item: Deletes an item.
```powershell
Remove-Item -Path C:\Path\To\File.txt
```
Get-EventLog: Gets events in the event log.
```powershell
Get-EventLog -LogName System -Newest 10
```
Clear-EventLog: Clear events from the event log.
```powershell
Clear-EventLog -LogName System
```
New-EventLog: Create a new event log and a new event source on a local or remote computer.
```powershell
New-EventLog -LogName NewLog -Source NewSource
```
## PowerShell commands related to managing system and application services

Start-Service: Starts one or more stopped services.
```powershell
Start-Service -Name serviceName
```
Stop-Service: Stops one or more running services.
```powershell
Stop-Service -Name serviceName
```
Restart-Service: Stops and then starts one or more services.
```powershell
Restart-Service -Name serviceName
```
Get-Service: Retrieves the status of services on a local or remote computer.
```powershell
Get-Service
```
Set-Service: Changes the start mode of a service.
```powershell
Set-Service -Name serviceName -StartupType Automatic
```
New-Service: Creates a new service.
```powershell
New-Service -Name NewService -BinaryPathName "C:\Path\To\Service.exe"
```
Remove-Service: Deletes a service.
```powershell
Remove-Service -Name serviceName
```
Get-EventLog: Gets events in the event log (useful for monitoring services).
```powershell
Get-EventLog -LogName System -Source "Service Control Manager" -Newest 10
```

These commands can help you manage, monitor, and configure services on your system. Remember to replace "serviceName" with the actual name of the service you're working with.

## PowerShell commands related to managing the Windows Registry:

Get-ItemProperty: Gets the properties of a registry key.
```powershell
Get-ItemProperty -Path 'HKLM:\Software\ExampleKey'
```
Set-ItemProperty: Sets the properties of a registry key.
```powershell
Set-ItemProperty -Path 'HKCU:\Software\ExampleKey' -Name 'ExampleValue' -Value 'NewValue'
```
New-Item: Creates a new registry key.
```powershell
New-Item -Path 'HKLM:\Software\NewKey'
```
Remove-Item: Removes a registry key.
```powershell
Remove-Item -Path 'HKCU:\Software\ExampleKey' -Recurse
```
Get-Item: Gets the registry key at the specified path.

```powershell
Get-Item -Path 'HKLM:\Software'
```
Copy-Item: Copies a registry key.
```powershell
Copy-Item -Path 'HKCU:\SourceKey' -Destination 'HKCU:\DestinationKey' -Recurse
```
Move-Item: Moves a registry key.
```powershell
Move-Item -Path 'HKCU:\SourceKey' -Destination 'HKCU:\DestinationKey'
```
Backup-Item: Creates a backup of a registry key.
```powershell
Backup-Item -Path 'HKLM:\Software\ExampleKey' -Destination 'C:\Backup\ExampleKey.reg'
```
Restore-Item: Restores a registry key from a backup.
```powershell
Restore-Item -Path 'C:\Backup\ExampleKey.reg' -Destination 'HKLM:\Software\RestoredKey'
```
Remember to use these commands with caution, as modifying the registry can impact system stability. Always back up the registry before making significant changes.

## PowerShell commands related to managing Computer Management tasks:

Get-Process: Get a list of processes running on a local or remote computer.

```powershell
Get-Process
```
Stop-Process: Stop a running process.

```powershell
Stop-Process -Name processName
```
Get-HotFix: Get the list of installed hotfixes on a local or remote computer.
```powershell
Get-HotFix
```
Get-WmiObject: Get instances of WMI classes on a local or remote computer.
```powershell
Get-WmiObject -Class Win32_ComputerSystem
```
## PowerShell commands for managing local users and groups:

### Local Users:

Create a New Local User:
```powershell
New-LocalUser -Name "Username" -Password (ConvertTo-SecureString -AsPlainText "Password" -Force) -FullName "Full Name" -Description "Description"
```
Delete a Local User:
```powershell
Remove-LocalUser -Name "Username"
```
Modify Local User Properties:
```powershell
Set-LocalUser -Name "Username" -Description "New Description" -PasswordNeverExpires $true
```
List All Local Users:
```powershell
Get-LocalUser
```
Check Current Logged In User:
```powershell
$env:USERNAME
```
Force Logout User (logoff session):
```powershell
Stop-Process -Name explorer -Force
```
Set Password Expiry:
```powershell
Set-LocalUser -Name "Username" -PasswordNeverExpires $false -AccountExpires (Get-Date).AddDays(90)
```
Enable Local User:
```powershell
Enable-LocalUser -Name "Username"
```
Disable Local User:
```powershell
Disable-LocalUser -Name "Username"
```
### Local Groups:
Create a New Local Group:
```powershell
New-LocalGroup -Name "GroupName"
```
Add User to Local Group:
```powershell
Add-LocalGroupMember -Group "GroupName" -Member "Username"
```
Remove User from Local Group:
```powershell
Remove-LocalGroupMember -Group "GroupName" -Member "Username"
```
Delete Local Group:
```powershell
Remove-LocalGroup -Name "GroupName"
```
List All Local Groups:
```powershell
Get-LocalGroup
```
Remember to replace "Username" and "GroupName" with the actual names you are working with. These commands should help you perform various tasks related to managing local users and groups in PowerShell.
