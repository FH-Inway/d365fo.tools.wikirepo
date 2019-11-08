# **List available commands in the d365fo.tools**

Please visit the **First-Time-Install-Administrator** or the **First-Time-Install-Non-Administrator** tutorials to learn how to install the tools.

Please visit the **First-Time-Import-Module** tutorial to see the different ways you can load the #d365fo.module into a PowerShell session.

## **Prerequisites**
* Machine with D365FO installed
* PowerShell 5.1
* d365fo.tools module installed

## **List all available commands**
For us to have something to work with, we need to get the list of available functions in the module. Type the following command:

```
Get-Command -Module d365fo.tools
```

See below gif on how to do it
**ScreenCast-Gif**


## **Get help content for a specific function**
If you want to know more about a specific function, you can pass the name to `Get-Help`. Type the following command:

```
Get-Help New-D365Bacpac
```

## **Get help content, including examples, for a specific function**
The help content for every function contains at least 1 example on how run the function. Type the following command:

```
Get-Help New-D365Bacpac -Full
```


## **Get examples only, for a specific function**
The help content for every function contains at least 1 example on how run the function. Type the following command:

```
Get-Help New-D365Bacpac -Examples
```