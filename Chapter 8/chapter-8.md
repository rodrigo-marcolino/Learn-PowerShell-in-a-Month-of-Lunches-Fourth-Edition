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

### 3. What type of object does the cmdlet from task 2 produce? (What is the TypeName of the object produced by the cmdlet?)

```powershell
PS C:\Labs> Get-Date | gm
```

`output`

```
TypeName: System.DateTime

Name                 MemberType     Definition
----                 ----------     ----------
Add                  Method         datetime Add(timespan value)
```

---

### 4. Using the cmdlet from task 2 and Select-Object, display only the current day of the week in a table like the following (caution: the output will right-align, so make sure your PowerShell window doesn’t have a horizontal scrollbar):

```
DayOfWeek
---------
   Monday
```

Find out the object property that we can use

```powershell
PS C:\Labs> Get-Date | Get-Member -Name *week*
```

`output:`

```
TypeName: System.DateTime

Name      MemberType Definition
----      ---------- ----------
DayOfWeek Property   System.DayOfWeek DayOfWeek {get;}
```

```powershell
PS C:\Labs> Get-Date | select DayOfWeek
```

`output:`

```
DayOfWeek
---------
 Thursday
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
