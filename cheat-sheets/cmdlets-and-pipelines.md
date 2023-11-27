# PowerShell Cmdlets and Pipelines Cheat Sheet

## Table of Contents

1. [Cmdlets](#cmdlets)
2. [Common Cmdlets](#common-cmdlets)
3. [Pipelines](#pipelines)
4. [Piping Output](#piping-output)
5. [Selecting Properties](#selecting-properties)
6. [Filtering](#filtering)
7. [Sorting](#sorting)
8. [Grouping](#grouping)
9. [Measuring](#measuring)

## Cmdlets

Cmdlets (pronounced "command-lets") are lightweight commands in PowerShell. They perform specific functions and are designed to work with objects.

- `Get-Command`: List all available commands.
- `Get-Help <cmdlet>`: Get help for a specific cmdlet.
- `Get-Command -Module <module>`: List commands from a specific module.
- `Get-Command -Name <name>`: Get information about a specific command.

## Common Cmdlets

- `Get-Process`: Get information about running processes.
- `Get-Service`: Retrieve information about services.
- `Get-EventLog`: Access Windows event logs.
- `Get-Content`: Read the content of a file.
- `Set-Content`: Set the content of a file.
- `Get-Item`: Get information about an item (file, folder, registry key, etc.).
- `Get-ChildItem`: List items in a directory.

## Pipelines

Pipelines allow you to pass the output of one cmdlet as input to another cmdlet, enabling powerful and efficient one-liners.

```powershell
Get-Process | Stop-Process
```

## Piping Output

```powershell
# Pipe the output of one cmdlet to another
Get-Service | Where-Object { $_.Status -eq 'Running' } | Stop-Service
```

## Selecting Properties

```powershell
# Select specific properties from the output
Get-Process | Select-Object Name, CPU, Handles
```

## Filtering

```powershell
# Filter output based on a condition
Get-Process | Where-Object { $_.CPU -gt 50 }
```

## Sorting

```powershell
# Sort output based on a property
Get-Process | Sort-Object CPU -Descending
```

## Grouping

```powershell
# Group output based on a property
Get-Process | Group-Object -Property UserName
```

## Measuring

```powershell
# Measure properties like Count, Sum, Average, etc.
Get-Process | Measure-Object -Property CPU -Sum
```

