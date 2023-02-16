# 3.8 Lab

1. Run Update-Help, and ensure that it completes without errors so that you have a copy of the help on your local computer. You need an internet connection.

   ```powershell
   PS> update-help -force
   ```

---

2. Can you find any cmdlets capable of converting other cmdlets’ output into HTML?

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

3. Are there any cmdlets that can redirect output into a file?

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

   ***

4. How many cmdlets are available for working with processes? (Hint: Remember that cmdlets all use a singular noun.)
