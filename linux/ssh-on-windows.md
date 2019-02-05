# SSH on Windows

For this, we need OpenSSH.Client. We can check if it's installed by running this in Administrator Powershell:

```
Get-WindowsCapability -Online | ? Name -like 'OpenSSH.Client*'
```

To install it, run:

```
Add-WindowsCapability -Online -Name OpenSSH.Client~~~~0.0.1.0
```
