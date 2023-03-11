# Lab 12.7

## 1. Get the commands from the PSReadLine module.

```powershell
PS C:\Labs> Get-Command -module psreadline
```

`Output:`

```
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        PSConsoleHostReadLine                              2.2.6      PSReadLine
Cmdlet          Get-PSReadLineKeyHandler                           2.2.6      PSReadLine
Cmdlet          Get-PSReadLineOption                               2.2.6      PSReadLine
Cmdlet          Remove-PSReadLineKeyHandler                        2.2.6      PSReadLine
Cmdlet          Set-PSReadLineKeyHandler                           2.2.6      PSReadLine
Cmdlet          Set-PSReadLineOption                               2.2.6      PSReadLine
```
---
## 2. Get the commands using the verb Get from the PSReadLine module.
```powershell
PS C:\Labs> Get-Command get* -module psreadline
```
`Output:`

```
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-PSReadLineKeyHandler                           2.2.6      PSReadLine
Cmdlet          Get-PSReadLineOption                               2.2.6      PSReadLine
```
---
##