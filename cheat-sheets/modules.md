# PowerShell Modules Cheat Sheet

## Table of Contents

1. [Creating Modules](#creating-modules)
2. [Importing Modules](#importing-modules)
3. [Viewing Module Contents](#viewing-module-contents)
4. [Exporting Functions](#exporting-functions)
5. [Module Manifests](#module-manifests)
6. [Module Versioning](#module-versioning)
7. [Publishing Modules](#publishing-modules)
8. [Installing Modules](#installing-modules)

## Creating Modules

```powershell
# Create a basic module
New-Module -ScriptBlock {
    function Get-Greeting {
        param (
            [string]$name
        )
        "Hello, $name!"
    }
} -Name MyModule
```

## Importing Modules

```powershell
# Import a module
Import-Module MyModule
```

- Use `Import-Module` to load a module into the current session.

## Viewing Module Contents

```powershell
# List functions in a module
Get-Command -Module MyModule
```

## Exporting Functions

```powershell
# Export functions from a module
Export-ModuleMember -Function Get-Greeting
```

- Use `Export-ModuleMember` to specify which functions to export from the module.

## Module Manifests

```powershell
# Create a module manifest
New-ModuleManifest -Path ".\MyModule\MyModule.psd1" -Author "Your Name" -Description "Description of the module" -ModuleVersion 1.0
```

## Module Versioning

```powershell
# Use module versioning
# In module manifest (.psd1) file
# ModuleVersion = "1.0.0.0"
```

## Publishing Modules

```powershell
# Publish a module to PowerShell Gallery
Publish-Module -Name MyModule -NuGetApiKey "YourApiKey" -Repository PSGallery
```

## Installing Modules

```powershell
# Install a module from PowerShell Gallery
Install-Module -Name MyModule -Repository PSGallery
```

- Use `Install-Module` to install a module from the PowerShell Gallery.

