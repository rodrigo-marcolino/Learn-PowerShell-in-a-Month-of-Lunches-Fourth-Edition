# 9.5 Lab

### 1. NOTE For this lab, you can use any OS you prefer (try it on multiple ones if you would like), and make sure you are using PowerShell 7.1 or higher.

Now it’s your turn. We’re assuming that you’re working in a virtual machine or other machine that is okay to mess up a little in the name of learning. Please don’t do this in a production environment on a mission-critical computer!

This exercise will be about secrets management. DevOps engineers should be very familiar with this concept. The idea is simple: We have a bunch of sensitive information (passwords, connection strings, etc.) that we need to use in our commands, but we need to keep those secrets in a secure location. We also may want to share those secrets with other members on our team—and an email is not secure enough, folks!

The PowerShell team has recently been working on a module called Secrets Management to do just this. It’s a generic module for interacting with any secret store that supports it. Some will be local secret stores like the macOS Keychain, and others will be cloud services like Azure Key Vault and HashiCorp Vault. Your goal is to grab this module, store a secret in your secret store of choice, and then retrieve it. If you use a cloud-based secret store, try to retrieve the secret from a different machine as the ultimate test.

`Find out the module:`

```powershell
PS C:\Labs> Get-ChildItem | select Name, CreationTime | sort-Object CreationTime -Descending
```

`output:`

```
Version              Name                                Repository           Description
-------              ----                                ----------           -----------
1.1.2                Microsoft.PowerShell.SecretManagem… PSGallery            This module provides a convenient way for a user to store and retrieve secrets. The secrets are…
0.9.2                SecretManagement.KeePass            PSGallery            A cross-platform Keepass Secret Management vault extension. See the README.MD in the module for more details.
2.0.0                SecretManagement.Hashicorp.Vault.KV PSGallery            A PowerShell SecretManagement extension for Hashicorp Vault Key Value Engine
1.0.0                SecretManagement.JustinGrote.CredM… PSGallery            This PowerShell module is an extension vault module for the PowerShell SecretManagement module.…
0.1.1                SecretManagement.BitWarden          PSGallery            SecretManagement extension for BitWarden!
0.2.1                SecretManagement.LastPass           PSGallery            SecretManagement extension for LastPass!
16.5.0               SecretManagement.Keeper             PSGallery            SecretManagement extension vault for Keeper
0.0.4.6              SecretManagement.1Password          PSGallery            SecretManagement extension for 1Password
1.0.1                SecretManagement.CyberArk           PSGallery            SecretManagement extension for CyberArk
0.0.9.1              SecretManagement.Chromium           PSGallery            A cross-platform Chromium (Edge/Chrome) Secret Management vault extension. See the README.MD in the module for more details.
0.1.3                SecretManagement.KeyChain           PSGallery            SecretManagement extension vault for macOS KeyChain
1.0.435              SecretManagement.PleasantPasswordS… PSGallery            A cross-platform Pleasent Password Server Secret Management vault extension. See the README.MD in the module for more details.
1.3.0                SecretManagement.Keybase            PSGallery            Keybase Secret Management Extension
2022.7.27.1          SecretManagement.DevolutionsHub     PSGallery            Secret management extension for Devolutions Hub
2022.3.2.0           SecretManagement.DevolutionsServer  PSGallery            Secret management extension for Devolutions Server
0.0.1                SecretManagement.LAPS               PSGallery            SecretManagement extension for Microsoft's Local Administrator Password Solution
2.1.1                SecretManagementArgumentCompleter   PSGallery            Argument completer for Microsoft.Powershell.SecretManagement
0.0.0.3              SecretManagement.HcVault.KV2        PSGallery            SecretManagement extension for Hashicorp Vault KV2 Engine
2.0.1                SecretManagement.NetwrixPasswordSe… PSGallery            A Secret Management vault extension for Netwrix Password Secure
1.0.0                SecretManagement.ExtensionTemplate  PSGallery            No
```