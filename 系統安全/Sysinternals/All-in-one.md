#
```
Sysinternals Process(行程==>惡意程式?) Utilities
Sysinternals Security(安全) Utilities
Sysinternals File(檔案) and Disk(硬碟) Utilities(公用程式)
Sysinternals Networking(網路) Utilities

```
## Sysinternals Process(行程==>惡意程式?) Utilities
```
超重要  Autoruns
See what programs are configured to startup automatically when your system boots and you login. 
Autoruns also shows you the full list of Registry and file locations 
where applications can configure auto-start settings.

Handle
This handy command-line utility will show you what files are open by which processes, and much more.

ListDLLs ==> List all the DLLs that are currently loaded, 
including where they are loaded and their version numbers. 
Version 2.0 prints the full path names of loaded modules.

PortMon ==>
Monitor serial and parallel port activity with this advanced monitoring tool. 
It knows about all standard serial and parallel IOCTLs and 
even shows you a portion of the data being sent and received. 
Version 3.x has powerful new UI enhancements and advanced filtering capabilities.

重要 ProcDump
This new command-line utility is aimed at capturing process dumps of otherwise difficult to isolate 
and reproduce CPU spikes. 
It also serves as a general process dump creation utility 
and can also monitor and generate process dumps when a process has a hung window or unhandled exception.

超重要  Process Explorer ==> Find out what files, registry keys and other objects processes have open,
  which DLLs they have loaded, and more. This uniquely powerful utility will even show you who owns each process.

超重要 Process Monitor ==> Monitor file system, Registry, process, thread and DLL activity in real-time.
    比Task Manager(工作管理員)好太多

超重要 駭客最愛 PsExec ==> Execute processes remotely.

PsGetSid ==> Displays the SID of a computer or a user.

PsKill(殺程式) ==> Terminate local or remote processes.

PsList(顯示程式)==> Show information about processes and threads.

PsService ==> View and control services.

PsSuspend ==> Suspend and resume processes.

PsTools
The PsTools suite includes command-line utilities for listing the processes running on local or remote computers, running processes remotely, rebooting computers, dumping event logs, and more.

ShellRunas
Launch programs as a different user via a convenient shell context-menu entry.

重要 VMMap
See a breakdown of a process's committed virtual memory types as well as 
the amount of physical memory (working set) assigned by the operating system to those types. 
Identify the sources of process memory usage and the memory cost of application features.
```
## Sysinternals Security(安全) Utilities
```
AccessChk
This tool shows you the accesses the user or group you specify has to files, Registry keys or Windows services.

AccessEnum
This simple yet powerful security tool shows you who has what access to directories, files and Registry keys on your systems. Use it to find holes in your permissions.

Autologon ==> Bypass password screen during logon.

超重要 Autoruns
See what programs are configured to startup automatically when your system boots and you log in. Autoruns also shows you the full list of Registry and file locations where applications can configure auto-start settings.

LogonSessions ==> List active logon sessions

超重要  Process Explorer
Find out what files, registry keys and other objects processes have open, which DLLs they have loaded, and more. This uniquely powerful utility will even show you who owns each process.

PsExec ==> Execute processes with limited-user rights.

PsLoggedOn ==> Show users logged on to a system.

PsLogList ==> Dump event log records.

PsTools
The PsTools suite includes command-line utilities for listing 
the processes running on local or remote computers, running processes remotely, 
rebooting computers, dumping event logs, and more.

Rootkit Revealer(過期了嗎?) ==> RootkitRevealer is an advanced rootkit detection utility.

SDelete
Securely overwrite your sensitive files and cleanse your free space 
of previously deleted files using this DoD-compliant secure delete program.

ShareEnum
Scan file shares on your network and view their security settings to close security holes.

ShellRunas 
Launch programs as a different user via a convenient shell context-menu entry.

Sigcheck ==> Dump file version information and verify that images on your system are digitally signed.

超重要 Sysmon ==> Monitors and reports key system activity via the Windows event log.
```
## Sysinternals File(檔案) and Disk(硬碟) Utilities(公用程式)
```


```
## Sysinternals Networking(網路) Utilities
```
AD Explorer ==> an advanced Active Directory (AD) viewer and editor.

AD Insight ==>  an LDAP (Light-weight Directory Access Protocol) real-time monitoring tool 
                 aimed at troubleshooting Active Directory client applications.
```

```
AdRestore ==> Undelete Server 2003 Active Directory objects.

重要PipeList ==> 
Displays the named pipes on your system, 
including the number of maximum instances and active instances for each pipe.

重要 PsFile ==> See what files are opened remotely.

PsPing ==> Measures network performance.

超重要 PsTools ==>
The PsTools suite includes command-line utilities for 
listing the processes running on local or remote computers, 
running processes remotely, rebooting computers, dumping event logs, and more.

ShareEnum ==> Scan file shares on your network and view their security settings 
              to close security holes.

超重要 TCPView ==> Active socket command-line viewer.

Whois ==>See who owns an Internet address.
```
