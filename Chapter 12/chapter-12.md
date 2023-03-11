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

## 3. Display all files under /usr/bin that are larger than 5 MB.

As I'm using Windows I'll list files in c:\windows\system32

```powershell
PS C:\Labs> Get-ChildItem C:\Windows\System32 | Where-Object {$_.Length -gt 5mb}
```

`Output:`

```
Directory: C:\Windows\System32

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           5/01/2023 11:21 am        9037312 BingMaps.dll
-a---           5/01/2023 11:21 am        7769088 Chakra.dll
-a---          19/11/2020 12:23 pm        6070904 d2d1.dll
-a---           2/11/2022  6:27 pm        7267688 d3d10warp.dll
-a---          23/04/2022  3:40 pm        6570496 dbgeng.dll
-a---          12/05/2022 11:17 am       18043904 DXCaptureReplay.dll
-a---           6/03/2023  7:01 am       26269696 edgehtml.dll
-a---          25/02/2023  7:06 pm       18767872 HologramWorld.dll
-a---           6/03/2023  7:01 am       24272384 Hydrogen.dll
-a---           6/03/2023  7:01 am        7713280 ieframe.dll
-a---          10/06/2022  7:52 pm        5615024 mfc140.dll
-a---          10/12/2021 11:19 pm       11169712 mfc140d.dll
-a---          10/06/2022  7:52 pm        5649312 mfc140u.dll
-a---          10/12/2021 11:19 pm       11239816 mfc140ud.dll
-a---          18/08/2021  1:59 am       26737480 mfxplugin64_hw.dll
-a---          25/02/2023  6:54 pm      149955784 MRT.exe
-a---           6/03/2023  7:01 am       23444480 mshtml.dll
-a---          25/02/2023  7:06 pm        8404992 mstscax.dll
-a---           7/12/2019  5:26 am        6361600 NlsData0009.dll
-a---           6/03/2023  7:01 am       10854272 ntoskrnl.exe
-a---           5/01/2023 11:21 am        8233024 OneCoreUAPCommonProxyStub.dll
-a---           7/12/2019  5:36 am        5739008 prm0009.dll
-a---           2/08/2021  2:46 pm       17868712 RsDMFT_Assets.dll
-a---           2/08/2021  2:46 pm       10512824 RsDMFT64.dll
-a---          25/02/2023  7:06 pm        7653032 shell32.dll
-a---           7/12/2019 10:09 pm        5865488 spwizimg.dll
-a---           6/03/2023  7:00 am        5751776 StartTileData.dll
-a---          25/02/2023  7:06 pm        6191616 twinui.dll
-a---           6/03/2023  7:01 am        6425600 twinui.pcshell.dll
-a---          25/02/2023  7:06 pm        6559072 vmchipset.dll
-a---           6/03/2023  7:01 am       14214016 vmms.exe
-a---          12/05/2022 11:17 am        5681152 VsGraphicsDesktopEngine.exe
-a---          19/11/2020 12:23 pm        5729280 Windows.AI.MachineLearning.dll
-a---          23/04/2022  3:40 pm        6725120 Windows.Data.Pdf.dll
-a---           2/11/2022  6:28 pm        7548648 Windows.Media.dll
-a---           6/03/2023  7:00 am       10349360 Windows.Media.Protection.PlayReady.dll
-a---           6/03/2023  7:01 am        5862840 Windows.StateRepository.dll
-a---           6/03/2023  7:01 am        7977392 windows.storage.dll
-a---           2/11/2022  6:27 pm       17551872 Windows.UI.Xaml.dll
-a---           5/01/2023 11:21 am       32610320 WindowsCodecsRaw.dll
-a---          23/04/2022  3:41 pm       11445248 wmp.dll
```

---
