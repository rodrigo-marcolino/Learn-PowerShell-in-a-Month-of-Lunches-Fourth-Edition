# 3.8 Lab

### 1. Run Update-Help, and ensure that it completes without errors so that you have a copy of the help on your local computer. You need an internet connection.

```powershell
PS> update-help -force
```

---

### 2. Can you find any cmdlets capable of converting other cmdlets’ output into HTML?

```powershell
help html
```

`output:`

```
NAME
 ConvertTo-Html

SYNOPSIS
 Converts .NET objects into HTML that can be displayed in a Web browser.
```

---

### 3. Are there any cmdlets that can redirect output into a file?

```powershell
Get-Command -Noun file, output
```

`output:`

```
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Out-File                                           3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Unblock-File                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Write-Output                                       3.1.0.0    Microsoft.PowerShell.Utility
```

After the command, I can see which command would bee.
In this case, it seems that the command is `out-file`

```powershell
help out-file
```

`output:`

```
NAME
Out-File

SYNOPSIS
Sends output to a file.
```

---

### 4. How many cmdlets are available for working with processes? (Hint: Remember that cmdlets all use a singular noun.)

```powershell
Get-Command -Noun Process
```

`output:`

```
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Debug-Process                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-Process                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Start-Process                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Stop-Process                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Wait-Process                                       3.1.0.0    Microsoft.PowerShell.Management
```

To count the number of cmdlets available we can pipe the output to the `Measure-Object` cmdlet and specify the `-Line` parameter.

```powershell
Get-Command *process | Measure-Object -Line
```

`output:`

```
Lines Words Characters Property
----- ----- ---------- --------
11
```

---

### 5. What cmdlet might you use to set to a PowerShell breakpoint? (Hint: PowerShell-specific nouns are often prefixed with PS.)

```powershell
Get-Command -Noun Process
```

`output:`

```
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Debug-Process                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-Process                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Start-Process                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Stop-Process                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Wait-Process                                       3.1.0.0    Microsoft.PowerShell.Management
```

To count the number of cmdlets available we can pipe the output to the `Measure-Object` cmdlet and specify the `-Line` parameter.

```powershell
Get-Command *breakpoint
```

`output:`

```
CommandType     Name    Version    Source
-----------     ----    -------    ------
Cmdlet          Disable-PSBreakpoint                               3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Enable-PSBreakpoint                                3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-PSBreakpoint                                   3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Remove-PSBreakpoint                                3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Set-PSBreakpoint                                   3.1.0.0    Microsoft.PowerShell.Utility
```

It seems that the command is `Set-PSBreakpoint`

```powershell
help Set-PSBreakpoint
```

`output:`

```
NAME
 Set-PSBreakpoint

SYNOPSIS
 Sets a breakpoint on a line, command, or variable.
```

---

### 6. You’ve learned that aliases are nicknames for cmdlets. What cmdlets are available to create, modify, export, or import aliases?

```powershell
Get-Command -Noun alias
```

`output:`

```
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Export-Alias                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Alias                                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Import-Alias                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          New-Alias                                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Set-Alias                                          3.1.0.0    Microsoft.PowerShell.Utility
```

