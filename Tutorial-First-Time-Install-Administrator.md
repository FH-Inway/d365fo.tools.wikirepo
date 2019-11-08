# **Learn how to install #d365fo.tools**

This tutorial will show you how to install the #d365fo.tools on a machine where you have administrator access / privileges. If you are **NOT** able to logon to the machine as an administrator, you should be using the **First-Time-Install-Non-Administrator** tutorial instead.

## **Prerequisites**
Machine with D365FO installed
PowerShell 5.1
Administrator privileges
Internet access / Internet connection

## **Logon to the computer**
You need sign into the machine where you want to install the tools. Remember to sign in as an account with administrator privileges.

## **Start PowerShell (Run As Administrator)**
Locate the PowerShell icon, if you don't have it on your desktop or in the task pane, we can locate it in the Windows Start Menu. Search for it or type PowerShell.

You need to right click on the PowerShell icon and select the "Run As Administrator" option for the menu.

[[images/First-Time-Start-PowerShell-Administrator.gif]]

See below gif on how to do it
**ScreenCast-Gif**

## **Install the #d365fo.tools**
In the PowerShell console/window type the following command:

```
Install-Module -Name d365fo.tools
```

PowerShell will now connect to the internet and try to download the latest version of the #d365fo.tools. Depending on how fresh your machine or PowerShell installation is, you might be prompted for questions / confirmations about core PowerShell configurations. You need to either accept or approve all the prompts, for things to work like expected. See below examples on the prompts and what response you should fill in.

### **NuGet**

### **Provider**

See below gif on how to do it
**ScreenCast-Gif**

## **Import module**
While you just installed the #d365fo.tools on the machine by following this tutorial, you will need to import or simply put, load the module into the PowerShell console, before you can use them. Type the following command:

```
Import-Module -Name d365fo.tools
```

**ScreenCast-Gif**
