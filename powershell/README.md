# PowerShell Scripts

This directory contains PowerShell scripts for Windows automation and system management.

## 📋 Available Scripts

*Scripts will be added here as the collection grows*

## Prerequisites

- PowerShell 5.1 or higher (PowerShell 7+ recommended)
- Windows operating system (or PowerShell Core for cross-platform)
- Appropriate execution policy set

## Getting Started

1. Check your PowerShell version:
```powershell
$PSVersionTable.PSVersion
```

2. Set execution policy (if needed):
```powershell
# For current user (recommended)
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# For specific script
Unblock-File -Path .\script_name.ps1
```

3. Run a script:
```powershell
.\script_name.ps1
```

## Script Categories

- **System Administration**: Scripts for Windows system management
- **Active Directory**: Scripts for AD operations and management
- **File Management**: Scripts for file operations and organization
- **Network Utilities**: Scripts for network configuration and monitoring
- **Automation Tasks**: Scripts for scheduled tasks and workflows

## Best Practices

- Always read the script's README before running
- Run PowerShell as Administrator if required
- Test scripts in a safe environment first
- Review execution policy requirements
- Check for required modules before running

## Common Setup

### Installing Modules:
```powershell
# Install a module (requires admin)
Install-Module -Name ModuleName

# Import a module
Import-Module -Name ModuleName

# List installed modules
Get-Module -ListAvailable
```

### Execution Policy:
PowerShell scripts require appropriate execution policy:

```powershell
# Check current policy
Get-ExecutionPolicy

# Set policy for current user
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# Bypass policy for a single script
PowerShell.exe -ExecutionPolicy Bypass -File .\script_name.ps1
```

## Running Scripts

### Basic execution:
```powershell
.\script_name.ps1
```

### With parameters:
```powershell
.\script_name.ps1 -Parameter1 "Value1" -Parameter2 "Value2"
```

### As Administrator:
```powershell
# Right-click PowerShell and "Run as Administrator", then:
.\script_name.ps1
```

### Scheduled Tasks:
```powershell
# Create a scheduled task
$Action = New-ScheduledTaskAction -Execute "PowerShell.exe" -Argument "-File C:\path\to\script.ps1"
$Trigger = New-ScheduledTaskTrigger -Daily -At "2:00AM"
Register-ScheduledTask -Action $Action -Trigger $Trigger -TaskName "MyTask"
```

## Compatibility

Scripts are designed for:
- Windows 10/11
- Windows Server 2016+
- PowerShell 5.1+
- PowerShell 7+ (cross-platform)

Script-specific requirements are noted in individual READMEs.

## Need Help?

If you encounter issues:
1. Check the script's individual README
2. Verify your PowerShell version: `$PSVersionTable.PSVersion`
3. Check execution policy: `Get-ExecutionPolicy`
4. Ensure all required modules are installed
5. Verify you have necessary permissions
6. Open an issue if the problem persists
