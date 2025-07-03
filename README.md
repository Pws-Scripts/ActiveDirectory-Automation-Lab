# ActiveDirectory-Automation-Lab
PowerShell automation scripts for managing Active Directory users in a test environment, including user creation, password handling, and attribute inspection.


# 🧑‍💻 Active Directory PowerShell Automation Lab

This repo demonstrates basic PowerShell scripting to manage Active Directory (AD) in a local lab environment.

### 🔧 What’s Covered:

- ✅ Creating new AD users via PowerShell (`New-ADUser`)
- ✅ Securely handling passwords using `ConvertTo-SecureString`
- ✅ Assigning users to specific OUs
- ✅ Retrieving full user object details (`Get-ADUser -Properties *`)
- ✅ Working inside a custom OU structure for lab testing

---
![Commands](/Image/SCNR_1.png) |

### 🧪 Sample Script

```powershell
$password = ConvertTo-SecureString -String "Pass-Code@2k25" -AsPlainText -Force

New-ADUser -Name "User2" `
  -AccountPassword $password `
  -Enabled $true `
  -Path "OU=Test,DC=Local,DC=qhamaninanderebe,DC=com"

Get-ADUser -Identity "User2" -Properties *
