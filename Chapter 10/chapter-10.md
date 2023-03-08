# 10.9 Lab

### 1. Would the following command work to retrieve a list of commands from modules that start with Microsoft.\* on the current machine? Why or why not? Write an explanation, similar to the ones we provided earlier in this chapter.

```powerShell
Get-Command -Module (Get-Module -ListAvailable -Name Microsoft.* |
Select-Object -ExpandProperty name)
```
