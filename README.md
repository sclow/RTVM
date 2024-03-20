# Setup
## Overview
Quick installation of a Windows 10 host to be able to support testing. 

Based on ZeroPointSecurity's RTOVMSetup (https://github.com/ZeroPointSecurity/RTOVMSetup)

## Windows

### 1. Install Boxstarter
Launch an administrative cmd prompt:

```
powershell -exec bypass
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072;
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
Old:
```
. { Invoke-WebRequest -useb https://boxstarter.org/bootstrapper.ps1 } | iex; Get-Boxstarter -Force
```


### 2. Install Boxstarter Package
```
$Cred = Get-Credential $env:USERNAME
Install-BoxstarterPackage -PackageName https://raw.githubusercontent.com/sclow/RTVM/main/win10.choco -Credential $Cred
```

