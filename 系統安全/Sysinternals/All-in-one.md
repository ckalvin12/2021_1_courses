#
```
https://docs.microsoft.com/en-us/sysinternals/downloads/
```
```
1.Sysinternals Process(行程==>惡意程式?) Utilities
2.Sysinternals Security(安全) Utilities
3.Sysinternals File(檔案) and Disk(硬碟) Utilities(公用程式)
4.Sysinternals Networking(網路) Utilities
5.Sysinternals System Information(系統資訊) Utilities
6.Sysinternals Miscellaneous(其他) Utilities
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
## Sysinternals System Information(系統資訊) Utilities
```
Autoruns
See what programs are configured to startup automatically when your system boots and you login. 
Autoruns also shows you the full list of Registry and file locations 
where applications can configure auto-start settings.

ClockRes
View the resolution of the system clock, which is also the maximum timer resolution.

Coreinfo
Coreinfo is a command-line utility that shows you the mapping between logical processors and the physical processor, NUMA node, and socket on which they reside, as well as the cache’s assigned to each logical processor.

Handle
This handy command-line utility will show you what files are open by which processes, and much more.

重要 LiveKd ==> Use Microsoft kernel debuggers to examine a live system.

LoadOrder
See the order in which devices are loaded on your WinNT/2K system.

LogonSessions
List the active logon sessions on a system.

PendMoves
Enumerate the list of file rename and delete commands that will be executed the next boot.

Process Explorer
Find out what files, registry keys and other objects processes have open, which DLLs they have loaded, and more. This uniquely powerful utility will even show you who owns each process.

Process Monitor
Monitor file system, Registry, process, thread and DLL activity in real-time.

ProcFeatures
This applet reports processor and Windows support for Physical Address Extensions and No Execute buffer overflow protection.

PsInfo ==> Obtain information about a system.

PsLoggedOn
Show users logged on to a system

PsTools
The PsTools suite includes command-line utilities for listing the processes running on local or remote computers, running processes remotely, rebooting computers, dumping event logs, and more.

RAMMap
An advanced physical memory usage analysis utility that 
presents usage information in different ways on its several different tabs.

WinObj
The ultimate Object Manager namespace viewer is here.
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
# Sysinternals Miscellaneous(其他) Utilities
```
AD Explorer
Active Directory Explorer is an advanced Active Directory (AD) viewer and editor.

AdRestore
Restore tombstoned Active Directory objects in Server 2003 domains.

Autologon
Bypass password screen during logon.

BgInfo
This fully-configurable program automatically generates desktop backgrounds that include important information about the system including IP addresses, computer name, network adapters, and more.

BlueScreen
This screen saver not only accurately simulates Blue Screens, but simulated reboots as well (complete with CHKDSK), and works on Windows Vista, Server 2008 and higher.

Ctrl2cap
This is a kernel-mode driver that demonstrates keyboard input filtering just above the keyboard class driver in order to turn caps-locks into control keys. Filtering at this level allows conversion and hiding of keys before NT even "sees" them. Ctrl2cap also shows how to use NtDisplayString() to print messages to the initialization blue-screen.

DebugView
Another first from Sysinternals: 
This program intercepts calls made to DbgPrint by device drivers and 
OutputDebugString made by Win32 programs. 
It allows for viewing and recording of debug session output on your local machine 
or across the Internet without an active debugger.

Desktops
This new utility enables you to create up to four virtual desktops 
and to use a tray interface or hotkeys to preview 
what’s on each desktop and easily switch between them.

Hex2dec ==> Convert hex numbers to decimal and vice versa.

NotMyFault
Notmyfault is a tool that you can use to crash, hang, 
and cause kernel memory leaks on your Windows system.

PsLogList
Dump event log records.

PsTools
The PsTools suite includes command-line utilities for listing the processes 
running on local or remote computers, running processes remotely,
rebooting computers, dumping event logs, and more.

RegDelNull
Scan for and delete Registry keys that contain embedded null-characters 
that are otherwise undeleteable by standard Registry-editing tools.

Registry Usage (RU)
View the registry space usage for the specified registry key.

RegJump
Jump to the registry path you specify in Regedit.

Strings ==> Search for ANSI and UNICODE strings in binary images.

ZoomIt
Presentation utility for zooming and drawing on the screen.
```
