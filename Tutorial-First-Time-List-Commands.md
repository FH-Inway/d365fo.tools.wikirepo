# **List available commands in the d365fo.tools**

This tutorial will show you how to list and search for commands that are available from the d365fo.tools module. Please visit the **First-Time-Install-Administrator** or the **First-Time-Install-Non-Administrator** tutorials to learn how to install the tools.

Please visit the **First-Time-Install-Administrator** or the **First-Time-Install-Non-Administrator** tutorials to learn how to install the tools.

Please visit the **First-Time-Import-Module** tutorial to see the different ways you can load the #d365fo.module into a PowerShell session.

## **Prerequisites**
* Machine with D365FO installed
* PowerShell 5.1
* d365fo.tools module installed

## **Start PowerShell**
Locate the PowerShell icon, if you don't have it on your desktop or in the task pane, we can locate it in the Windows Start Menu. Search for it or type PowerShell.

**Image of PowerShell**

See below gif on how to do it
**ScreenCast-Gif**

## **List all available commands**
If you want to see the entire list of available commands from the d365fo.tools, you can ask PowerShell to list them for you. Type the following command:

```
Get-Command -Module d365fo.tools
```

See below gif on how to do it
**ScreenCast-Gif**


## **Search for commands**
If you want to search for command that contains a specific word or phrase, you can ask PowerShell to search for commands in the d365fo.tools module. Type the following command:

```
Get-Command *bacpac* -Module d365fo.tools
```

See below gif on how to do it
**ScreenCast-Gif**
