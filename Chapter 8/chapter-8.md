# 8.10 Lab

### 1. Identify a cmdlet that produces a random number.

</br>Finding out the command.

```powershell
PS C:\Labs> Get-Command *random*
```

`output`

```
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-Random                                         7.0.0.0    Microsoft.PowerShell.Utility
```

```powershell
PS C:\Labs> Get-Random
```

`output`

```
1973906388
```

---

### 2. Identify a cmdlet that displays the current date and time.

</br>
Finding out the command.

```powershell
PS C:\Labs> Get-Command  -Verb get -Noun *date*
```

`output:`

```

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-WindowsUpdateLog                               1.0.0.0    WindowsUpdate
Cmdlet          Get-Date                                           7.0.0.0    Microsoft.PowerShell.Utility
```

```powershell
PS C:\Labs> Get-Date
```

`output`

```
Thursday, 2 March 2023 10:38:25 pm
```

---

### 3. Use the commands from section 7.2 to find and install (if needed) the latest-version module by Microsoft for working with archives that contain the command `Compress-Archive`.

```powershell
Find-Module -Command Compress-Archive | Install-Module -Force

```

---

### 4. Import the module you just installed.

&nbsp;
First, List all modules to see the full name of the module.

```powershell
PS C:\Labs> Get-Module
```

`output:`

```
ModuleType Version    PreRelease Name                                ExportedCommands
---------- -------    ---------- ----                                ----------------
Binary     7.0.0.0               CimCmdlets                          {Get-CimAssociatedInstance, Get-CimClass, Get-CimInstanc…
Script     0.1.2.0               ConnectWiseAutomateAgent            {ConvertFrom-CWAASecurity, ConvertTo-CWAASecurity, Get-C…
Manifest   1.2.5                 Microsoft.PowerShell.Archive        {Compress-Archive, Expand-Archive}
Manifest   7.0.0.0               Microsoft.PowerShell.Management     {Add-Content, Clear-Content, Clear-Item, Clear-ItemPrope…
Manifest   7.0.0.0               Microsoft.PowerShell.Security       {ConvertFrom-SecureString, ConvertTo-SecureString, Get-A…
Manifest   7.0.0.0               Microsoft.PowerShell.Utility        {Add-Member, Add-Type, Clear-Variable, Compare-Object…}
Manifest   2.0.0.0               NetAdapter                          {Disable-NetAdapter, Disable-NetAdapterBinding, Disable-…
Manifest   1.0.0.0               NetTCPIP                            {Find-NetRoute, Get-NetCompartment, Get-NetIPAddress, Ge…
Script     1.4.8.1               PackageManagement                   {Find-Package, Find-PackageProvider, Get-Package, Get-Pa…
Script     0.2.0                 PowerShellEditorServices.Commands   {Clear-Host, ConvertFrom-ScriptExtent, ConvertTo-ScriptE…
Binary     0.2.0                 PowerShellEditorServices.VSCode     {Close-VSCodeHtmlContentView, New-VSCodeHtmlContentView,…
Script     2.2.5                 PowerShellGet                       {Find-Command, Find-DscResource, Find-Module, Find-RoleC…
Manifest   1.2.0                 PSLANScan                           {Find-LANHosts, Get-IPs}
Script     2.2.6                 PSReadLine                          {Get-PSReadLineKeyHandler, Get-PSReadLineOption, Remove-…
```

&nbsp;
Then you can import it.

```powershell
PS C:\Labs> Import-Module Microsoft.PowerShell.Archive
```

---

### 5. Create a Tests folder for the next step with 10 files in it, and name it ~/TestFolder.

</br>
Creating a TestFolder

```powershell
PS C:\Labs> New-Item -ItemType Directory -Name TestFolder
```

Creating the 10 files in the TestFolder.

```powershell
PS C:\Labs> 1..10 | ForEach-Object {New-Item -ItemType File -Name ("/TestFolder/$_.txt" -f $_)}
```

`output:`

```
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---          27/02/2023 12:40 am              0 1.txt
-a---          27/02/2023 12:40 am              0 2.txt
-a---          27/02/2023 12:40 am              0 3.txt
-a---          27/02/2023 12:40 am              0 4.txt
-a---          27/02/2023 12:40 am              0 5.txt
-a---          27/02/2023 12:40 am              0 6.txt
-a---          27/02/2023 12:40 am              0 7.txt
-a---          27/02/2023 12:40 am              0 8.txt
-a---          27/02/2023 12:40 am              0 9.txt
-a---          27/02/2023 12:40 am              0 10.txt
```

---

### 6. Compress-Archive ~/TestFolder/\* -DestinationPath ~/TestFolder.zip

```powershell
PS C:\Labs> Compress-Archive ~/TestFolder/* -DestinationPath ~/TestFolder.zip
```

---

### 7. Expand-Archive ~/TestFolder.zip -DestinationPath ~/TestFolder2

```powershell
PS C:\Labs> Expand-Archive ~/TestFolder.zip -DestinationPath ~/TestFolder2
```
