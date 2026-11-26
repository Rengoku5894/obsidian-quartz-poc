---
title: PowerShell
description: PowerShell commands and automation examples for Windows administration
tags:
  - powershell
  - windows
  - automation
---

# PowerShell

PowerShell can be used for Windows administration, automation, software detection and troubleshooting.

## Check PowerShell Version

```powershell
$PSVersionTable
```

## Check Windows Information

```powershell
Get-ComputerInfo |
    Select-Object WindowsProductName, WindowsVersion, OsArchitecture
```

## Installed Application Detection

### 64-bit Registry Location

```powershell
Get-ItemProperty `
    HKLM:\Software\Microsoft\Windows\CurrentVersion\Uninstall\* |
    Select-Object DisplayName, DisplayVersion, Publisher
```

### 32-bit Registry Location

```powershell
Get-ItemProperty `
    HKLM:\Software\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\* |
    Select-Object DisplayName, DisplayVersion, Publisher
```

> [!NOTE]
> Depending on application architecture and installation method, application information may appear in different uninstall registry locations.

## Related Articles

- [[Windows]]
- [[Troubleshooting]]
