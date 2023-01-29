# Environment Variables in Windows

## How to use them in PowerShell

Environment Variables can be used in [Powershell](powershell.md) with the prefix `$env:`.

***Example***:
*Variable:*  `%APPDATA%`
*In Powershell:* `$env:APPDATA`

## List of environment variables

**Variable** | **Description**
---|---
`%ALLUSERSPROFILE%`|C:\ProgramData
`%APPDATA%`|C:\Users\{username}\AppData\Roaming
`%COMMONPROGRAMFILES%`|C:\Program Files\Common Files
`%COMMONPROGRAMFILES(x86)%`|C:\Program Files (x86)\Common Files
`%CommonProgramW6432%`|C:\Program Files\Common Files
`%COMSPEC%`|C:\Windows\System32\cmd.exe
`%HOMEDRIVE%`|C:\
`%HOMEPATH%`|C:\Users\{username}
`%LOCALAPPDATA%`|C:\Users\{username}\AppData\Local
`%LOGONSERVER%`|\\{domain_logon_server}
`%PATH%`|C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem
`%PathExt%`|.com;.exe;.bat;.cmd;.vbs;.vbe;.js;.jse;.wsf;.wsh;.msc
`%PROGRAMDATA%`|C:\ProgramData
`%PROGRAMFILES%`|C:\Program Files
`%ProgramW6432%`|C:\Program Files
`%PROGRAMFILES(X86)%`|C:\Program Files (x86)
`%PROMPT%`|$P$G
`%SystemDrive%`|C:
`%SystemRoot%`|C:\Windows
`%TEMP%`|C:\Users\{username}\AppData\Local\Temp
`%TMP%`|C:\Users\{username}\AppData\Local\Temp
`%USERDOMAIN%`|Userdomain associated with current user.
`%USERDOMAIN_ROAMINGPROFILE%`|Userdomain associated with roaming profile.
`%USERNAME%`|{username}
`%USERPROFILE%`|C:\Users\{username}
`%WINDIR%`|C:\Windows
`%PUBLIC%`|C:\Users\Public
`%PSModulePath%`|%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\
`%OneDrive%`|C:\Users\{username}\OneDrive
`%DriverData%`|C:\Windows\System32\Drivers\DriverData
`%CD%`|Outputs current directory path. (Command Prompt.)
`%CMDCMDLINE%`|Outputs command line used to launch current Command Prompt session. (Command Prompt.)
`%CMDEXTVERSION%`|Outputs the number of current command processor extensions. (Command Prompt.)
`%COMPUTERNAME%`|Outputs the system name.
`%DATE%`|Outputs current date. (Command Prompt.)
`%TIME%`|Outputs time. (Command Prompt.)
`%ERRORLEVEL%`|Outputs the number of defining exit status of previous command. (Command Prompt.)
`%PROCESSOR_IDENTIFIER%`|Outputs processor identifier.
`%PROCESSOR_LEVEL%`|Outputs processor level.
`%PROCESSOR_REVISION%`|Outputs processor revision.
`%NUMBER_OF_PROCESSORS%`|Outputs the number of physical and virtual cores.
`%RANDOM%`|Outputs random number from 0 through 32767.
`%OS%`|Windows_NT

Variables should be enclosed in `%`, for example `echo %TEMP%` on Windows 10 will result in the output `C:\Users\\{username}\AppData\Local\Temp`, replacing `{username}` with your login username. In most cases the case doesn't matter, but for consistancy variables are shown in upper case.

| **Variable** | **Default/Information** |
| -------- | ------- |
| `USERNAME` | your user name |
| `USERDOMAIN` | The domain or machine name |
| `COMPUTERNAME` | The machine name |
| `NUMBER_OF_PROCESSORS` | The number of processors running on the machine |
| `DATE` | The current date |
| `TIME` | The current time in TIME format |
| `RANDOM` | A random number from 0 to 32767 |
| `OS` | The operating system (Win10 still reports Windows_NT) |
| `PATHEXT` | .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC, comma separated exectuable file extensions in order of precedence (left to right) |
| `PROCESSOR_ARCHITECTURE` | AMD64/IA64/x86 the architecture of the current process |
| `PROCESSOR_IDENTIFIER` | Processor ID |
| `PROCESSOR_LEVEL` | Processor level |
| `PROCESSOR_REVISION` | Processor revision |
| `PROMPT` | The command prompt format (for example $P$G) |
| `ERRORLEVEL` | The error value set when a program exits |
| `COMSPEC` | C:\Windows\System32\cmd.exe |
| `LOGONSERVER` | \\\{domain} |
| `USERDOMAIN_ROAMINGPROFILE` | User domain associated with romaing profile |

## Default directory locations

| **Variable** | **Directory location** |
| -------- | ------- |
| `SYSTEMDRIVE` | C: (or whatever your system drive is) |
| `CD` | The current directory |
| `TMP` or `TEMP` | C:\Users\\{username}\AppData\Local\Temp |
| `HOMEDRIVE`    | C: |
| `HOMEPATH`     | \Users\\{username} |
| `USERPROFILE` | C:\Users\\{username} |
| `APPDATA`     | C:\Users\\{username}\AppData\Roaming |
| `ALLUSERSPROFILE` | C:\ProgramData |
| `PROGRAMFILES` | C:\Program Files |
| `PROGRAMFILES(x86)` | C:\Program Files (x86) |
| `COMMONPROGRAMFILES` | C:\Program Files\Common Files |
| `COMMONPROGRAMFILES(x86)` | C:\Program Files (x86)\Common Files |
| `PROGRAMDATA` | C:\ProgramData |
| `LOCALAPPDATA` | C:\Users\\{username}\AppData\Local |
| `SYSTEMROOT` or `WINDIR` | C:\windows (Note: WINDIR may be altered so user SYSTEMROOT instead) |
| `PUBLIC` | C:\Users\Public |
| `PATH` | Your file search path |
| `PSMODULEPATH` | C:\Program Files\WindowsPowerShell\Modules;C:\windows\system32\WindowsPowerShell\v1.0\Module |
| `ONEDRIVE` | C:\Users\\{username}\OneDrive |
| `DRIVERDATA` | C:\Windows\System32\Drivers\DriverData |
| `CMDCMDLINE` | Command line used to launch CMD (i.e. "C:\windows\system32\cmd.exe") |
| `CMDEXTVERSION` | Number of command process extensons for CMD prompt |

## Common directory locations (including the %)

| **Variable** | **Directory location** |
| -------- | ------- |
| `%USERPROFILE%\Desktop` | C:\Users\\{username}\Desktop |
| `%USERPROFILE%\Downloads` | C:\Users\\{username}\Downloads |
| `%USERPROFILE%\Documents` | C:\Users\\{username}\Documents |
| `%USERPROFILE%\Pictures` | C:\Users\\{username}\Pictures |
| `%USERPROFILE%\Music` | C:\Users\\{username}\Music |
| `%USERPROFILE%\Videos` | C:\Users\\{username}\Videos |
| `%PROGRAMDATA%\Microsoft\Windows\Start Menu\Programs` | C:\ProgramData\Microsoft\Windows\Start Menu\Programs |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | C:\Users\\{username}\AppData\Roaming\Microsoft\Windows\Start Menu\Programs |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup` | C:\Users\\{username}\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup |

## Some default application directories

| **Variable** | **Description** |
| -------- | ------- |
| `%USERPROFILE%\\.npmrc` | NPM ini-formatted configuration file |
| `%USERPROFILE%\\.gitconfig` | Global Git configuration file |
| `%USERPROFILE%\\.bash_history` | History of BASH commands |
| `%APPDATA%\cabal` | Cabal configuration and packages |
| `%USERPROFILE%\Documents\Visual Studio 2019\Templates\ProjectTemplates` | Visual Studio user's project templates |
| `%USERPROFILE%\Documents\Visual Studio 2019\Templates\ItemTemplates` | Visual Studio user's item templates |
| `%USERPROFILE%\\.nuget\packages` | Nuget packages folder | 
