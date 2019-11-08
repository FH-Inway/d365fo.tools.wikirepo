# **Working with D365FO services**

This tutorial will show you how to work with the functions that enables you to manage the different D365FO services.

Please visit the **First-Time-Install-Administrator** or the **First-Time-Install-Non-Administrator** tutorials to learn how to install the tools.

Please visit the **First-Time-Import-Module** tutorial to see the different ways you can load the #d365fo.module into a PowerShell session.

## **Prerequisites**
* Machine with D365FO installed
* PowerShell 5.1
* d365fo.tools module installed

Please visit the **First-Time-Import-Module** tutorial to see the different ways you can load the #d365fo.module into a PowerShell session.

## **List all available D365FO services**
If you want to see the entire list of D365FO services and/or see their current running state, type the following command:

```
Get-D365Environment -All
```

## **Stop all D365FO services**
If you want to stop all services on the machine, maybe you want to install an update or import a model, type the following command:

```
Stop-D365Environment -All
```

## **Start all D365FO services**
If you want to start all services on the machine, type the following command:

```
Start-D365Environment -All
```

## **Restart all D365FO services**
If you want to restart all services on the machine, maybe because you are having some issues with caching, type the following command:

```
Restart-D365Environment -All
```

**Image of Run As Administrator**

See below gif on how to do it
**ScreenCast-Gif**

