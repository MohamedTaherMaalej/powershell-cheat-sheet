# PowerShell Remoting Cheat Sheet

## Table of Contents

1. [Enable PowerShell Remoting](#enable-powershell-remoting)
2. [Remote Sessions](#remote-sessions)
3. [Invoke-Command](#invoke-command)
4. [Enter-PSSession](#enter-pssession)
5. [Exit-PSSession](#exit-pssession)
6. [Copy-Item Remotely](#copy-item-remotely)
7. [Session Configuration](#session-configuration)
8. [Limiting Remoting Access](#limiting-remoting-access)
9. [Remoting Troubleshooting](#remoting-troubleshooting)

## Enable PowerShell Remoting

```powershell
# On the remote computer
Enable-PSRemoting -Force
```

- Run this command on the remote computer to enable PowerShell remoting.

## Remote Sessions

```powershell
# Create a remote session
$session = New-PSSession -ComputerName "RemoteComputer"

# Close a remote session
Remove-PSSession $session
```

## Invoke-Command

```powershell
# Run a command on a remote computer
Invoke-Command -ComputerName "RemoteComputer" -ScriptBlock { Get-Process }
```

## Enter-PSSession

```powershell
# Enter an interactive session on a remote computer
Enter-PSSession -ComputerName "RemoteComputer"
```

## Exit-PSSession

```powershell
# Exit from an interactive session
Exit-PSSession
```

## Copy-Item Remotely

```powershell
# Copy files/folders to a remote computer
Copy-Item -Path "C:\Local\File.txt" -Destination "\\RemoteComputer\C$\Path\" -ToSession $session
```

## Session Configuration

```powershell
# View session configurations
Get-PSSessionConfiguration
```

- PowerShell sessions are configured using session configurations.

## Limiting Remoting Access

```powershell
# Allow specific users to run commands remotely
Set-Item WSMan:\localhost\Shell\MaxMemoryPerShellMB 500
Set-PSSessionConfiguration -Name Microsoft.PowerShell -ShowSecurityDescriptorUI
```

## Remoting Troubleshooting

```powershell
# Check remoting status
Test-WsMan "RemoteComputer"

# Check if a port is open
Test-NetConnection -ComputerName "RemoteComputer" -Port 5985
```

- Use these commands to troubleshoot issues with PowerShell remoting.

