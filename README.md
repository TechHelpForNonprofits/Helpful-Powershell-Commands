# ADPowershell-Commands
Helpful Powershell commands for Active Directory

#You may need to set your execution policy if these commands won't work
```powershell 
Set-ExecutionPolicy -ExecutionPolicy -Bypass
```
#Find user accounts that haven't logged in for 90 days or more
```powershell
Search-ADAccount -UsersOnly -AccountInactive -TimeSpan 90.00:00:00 | Select-Object Name,LastLogonDate | Sort-Object LastLogonDate
```
<i>#If you want to save to a file you would add  "| -Path c:\OldAccounts.csv" to the end w/o quotes</i><br/>
<br/>
#Find user accounts that are disabled
```powershell
Search-ADAccount -UsersOnly -AccountDisabled | Select-Object SamAccountName
```
#Find user accounts that have passwords that never expire
```powershell
Search-ADaccount -UsersOnly -PasswordNeverExpires | select-object SamAccountName
```
