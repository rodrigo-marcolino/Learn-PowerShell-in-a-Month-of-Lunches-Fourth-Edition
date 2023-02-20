# 4.10 Lab

### 1. Display a list of running processes.

```powershell
PS> Get-Process
```

---

### 2.Test the connection to google.com or bing.com without using an external command like ping.

```powershell
PS C:\Users\rodri.LAPTOP-UTLDGGR2> Test-Connection google.com

```

`output:`

```
Source        Destination     IPV4Address      IPV6Address                              Bytes    Time(ms)
------        -----------     -----------      -----------                              -----    --------
DEVMACHINE    google.com      172.217.24.46                                             32       28
DEVMACHINE    google.com      172.217.24.46                                             32       31
DEVMACHINE    google.com      172.217.24.46                                             32       28
DEVMACHINE    google.com      172.217.24.46                                             32       29
```

---

### 3. Display a list of all commands that are of the cmdlet type. (This is tricky—we’ve shown you Get-Command, but you need to read the help to find out how to narrow down the list as we’ve asked.)

```powershell
Get-Command -Type cmdlet
```

---

### 4. Display a list of all aliases.

```powershell
Get-Alias
```

---

### 5. Make a new alias, so you can run ntst to run netstat from a PowerShell prompt

```powershell
New-Alias -Name ntst -Value netstat
```

---

### 6. Display a list of processes that begin with the letter p. Again, read the help for the necessary command—and don’t forget that the asterisk (\*) is a near-universal wildcard in PowerShell.

```powershell
PS C:\Users\rodri.LAPTOP-UTLDGGR2> Get-Process -Name p*
```

`output:`

```
Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
    890      68   367608     397508      97.48  24920   1 powershell_ise
    736      38    11592      17236      39.09   6448   1 PowerToys
    219      12    18728       1880      72.44   8916   1 PowerToys.AlwaysOnTop
    795      40    23092       4968      17.66   8924   1 PowerToys.Awake
    496      62    71920      19264      47.75   8960   1 PowerToys.ColorPickerUI
    303      20   157476       5900   1,773.30   8988   1 PowerToys.FancyZones
    143       9    16208       1032       3.34   9012   1 PowerToys.KeyboardManagerEngine
   1133     107   163628      20032      89.41   9052   1 PowerToys.PowerLauncher
    236      28    25724      13772              6892   0 PresentationFontCache
```

---

### 7. Make a new folder (aka directory) using the New-Item cmdlet with the name of MyFolder1. Then do it again and call it MyFolder2. Use Help if you’re not familiar with New-Item.

Creating a new folder call Myfolder1.

```powershell
PS C:\Users\rodri.LAPTOP-UTLDGGR2> New-Item -Name Myfolder1 -Path c:\PowerShell -ItemType Directory
```

`output:`

```
 Directory: C:\PowerShell


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        21/02/2023   6:57 am                Myfolder1
```

Creating a directory called Myfolder2

```powershell
PS C:\Users\rodri.LAPTOP-UTLDGGR2> New-Item -Name Myfolder2 -Path c:\PowerShell -ItemType Directory
```

`output:`

```
 Directory: C:\PowerShell


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        21/02/2023   6:59 am                Myfolder2
```

---

### 8. Getting all processes can be overwhelming. How can you get processes by the name of the process?

```powershell
PS C:\Users\rodri.LAPTOP-UTLDGGR2> get-process -Name powershell
```

`output:`

```
Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
   1039      61   193148     226600       8.59  24920   1 powershell_ise
```

---

### 9. Is there a way to tell Get-Process to tell you the user who started the process?

Finding out what command to use

```powershell
PS C:\Users\rodri.LAPTOP-UTLDGGR2> help get-process -parameter *username*
```

`output:`

```
-IncludeUserName <System.Management.Automation.SwitchParameter>
    Indicates that the UserName value of the Process object is returned with results of the command.

    Required?                    true
    Position?                    named
    Default value                False
    Accept pipeline input?       False
    Accept wildcard characters?  false
```

Testing:

```powershell
get-process -Name powershell* -IncludeUserNam
```

`output:`

```
Handles      WS(K)   CPU(s)     Id UserName               ProcessName
-------      -----   ------     -- --------               -----------
    710      84100     0.75   6396 DEVMACHINE\rodri       powershell
    922     292496    26.66  24920 DEVMACHINE\rodri       powershell_ise
```

---

### 10. Is there a way to run a command on a remote host? (Hint: Invoke is the verb for running something now.)

```powershell
help Invoke-Command –Parameter computername
```

---

### 11. Examine the help file for the Out-File cmdlet. The files created by this cmdlet default to a width of how many characters? Is there a parameter that would enable you to change that width?

```powershell
Help Out-File –Parameter Width
```

`output:`

```

-Width <System.Int32>
    Specifies the number of characters in each line of output. Any additional characters are truncated, not wrapped. If this parameter is not used, the width is determined by the
    characteristics of the host. The default for the PowerShell console is 80 characters. If you want to control the width for all invocations of `Out-File` as well as the redirection
    operators (`>` and `>>`), set `$PSDefaultParameterValues['out-file:width'] = 2000` before using `Out-File`.

    Required?                    false
    Position?                    named
    Default value                None
    Accept pipeline input?       False
    Accept wildcard characters?  false
```

---

### 12. By default, Out-File overwrites any existing file that has the same filename as what you specify. Is there a parameter that would prevent the cmdlet from overwriting an existing file?

```powershell
Get-Process | Out-File -FilePath "C:\Processes.txt" -NoClobber

```

---

### 13. How could you see a list of all aliases defined in PowerShell?

```powershell
Get-Alias
```

---

### 14 . Using both an alias and abbreviated parameter names, what is the shortest command line you could type to retrieve a list of commands with the word process in the name?

```powershell
PS C:\Users\rodri.LAPTOP-UTLDGGR2> Gcm -na *process*
```

`output:`

```

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           Start-ASRSwitchProcessServerJob                    0.2.4      AzureRM.RecoveryServices.SiteRecovery
Function        Get-AppvVirtualProcess                             1.0.0.0    AppvClient
Function        Start-AppvVirtualProcess                           1.0.0.0    AppvClient
Cmdlet          ConvertTo-ProcessMitigationPolicy                  1.0.12     ProcessMitigations
Cmdlet          Debug-Process                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Enter-PSHostProcess                                3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Exit-PSHostProcess                                 3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-ComputeProcess                                 1.0.0.0    HostComputeService
Cmdlet          Get-Process                                        3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Get-ProcessMitigation                              1.0.12     ProcessMitigations
Cmdlet          Get-PSHostProcessInfo                              3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-VMProcessor                                    2.0.0.0    Hyper-V
Cmdlet          Set-ProcessMitigation                              1.0.12     ProcessMitigations
Cmdlet          Set-VMProcessor                                    2.0.0.0    Hyper-V
Cmdlet          Start-AzureRmRecoveryServicesAsrSwitchProcessSe... 0.2.4      AzureRM.RecoveryServices.SiteRecovery
Cmdlet          Start-Process                                      3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Stop-ComputeProcess                                1.0.0.0    HostComputeService
Cmdlet          Stop-Process                                       3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Wait-Process                                       3.1.0.0    Microsoft.PowerShell.Management
Application     qprocess.exe                                       10.0.19... C:\Windows\system32\qprocess.exe
```

---

### 15. How many cmdlets are available that can deal with generic objects? (Hint: Remember to use a singular noun like object rather than a plural one like objects.)

```powershell
PS C:\Users\rodri.LAPTOP-UTLDGGR2> Get-Command –Noun object
```

`output:`

```

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Compare-Object                                     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          ForEach-Object                                     3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Group-Object                                       3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Measure-Object                                     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          New-Object                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Select-Object                                      3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Sort-Object                                        3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object                                         3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Where-Object                                       3.0.0.0    Microsoft.PowerShell.Core
```

---

### 16. This chapter briefly mentioned arrays. What help topic could tell you more about them?

```powershell
help *array*
```

---
