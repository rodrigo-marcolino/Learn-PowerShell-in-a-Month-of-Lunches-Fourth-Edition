# 6.7 Lab

### 1. Create two similar, but different, text files. Try comparing them by using `Compare-Object`. </br>Run something like this: `Compare-Object -Reference (Get-Content File1.txt) -Difference (Get-Content File2.txt)`. </br>If the files have only one line of text that’s different, the command should work.

```powershell
PS C:\Labs> "file number 1" | out-file MyFile1.txt
PS C:\Labs> "file number 2" | out-file MyFile2.txt
PS C:\Labs> Compare-Object .\MyFile1.txt .\MyFile2.txt
```

`output:`

```

InputObject   SideIndicator
-----------   -------------
.\MyFile2.txt =>
.\MyFile1.txt <=
```

---

### 2. Create a zero-length file named /Labs/Test.txt (use New-Item).

```powershell
PS C:\Labs> New-Item -Path C:\Labs -Name test.txt -ItemType file
```

---

### 3. Is it possible to use Set-Item to change the contents of /Labs/Test.txt to -TESTING? Or do you get an error? If you get an error, why?

It's not supported by the FileSystem

---

### 4. Using the Environment provider, display the value of the system environment variable PATH.

```powershell
PS C:\Labs> Get-Item env:PATH
```

`output:`

```

Name                           Value
----                           -----
Path                           C:\Program Files (x86)\VMware\VMware Player\bin\;C:\Python310\Scripts\;C:\Python310\;C:\Program Files\Microsoft\jdk-11.0.12.7-hotspot\bin;C:\Windows\system3...
```

---

### 5. Use help to determine what the differences are between the -Filter, -Include, and -Exclude parameters of Get-ChildItem.

Getting the full documentation for Get-ChildItem

```powershell
get-help Get-ChildItem -Detailed
```

`-Filter:`Is applied before the command retrieves the items.  
`-Include:`Specifies the items to include in the output. Is applied after the command retrieves the items.  
`-Include:`Specifies the items to exclude from output.
