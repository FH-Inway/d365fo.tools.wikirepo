# **Export a bacpac file from a Tier1 environment**

This how-to will guide you while you will be exporting a bacpac file from a Tier1 environment.

Please visit the **First-Time-Install-Administrator** or the **First-Time-Install-Non-Administrator** tutorials to learn how to install the tools.

Please visit the **First-Time-Import-Module** tutorial to see the different ways you can load the #d365fo.module into a PowerShell session.

## **Prerequisites**
* Machine with D365FO installed
* PowerShell 5.1
* #d365fo.tools module installed

## **Stop all D365FO services**
We need to stop all D365FO related services, to ensure that our database isn't being updated while we are exporting it. Type the following command:

```
Stop-D365Environment -All
```


## **Start all D365FO services**
We will now export the bacpac file, and instruct the command to output the progress, so we can see that things are running as expected. Type the following command:

```
New-D365Bacpac -ExportModeTier1 -ShowOriginalProgress
```

The command will run for quite some time, but it will eventually exit and output the file location of the newly created bacpac file.
