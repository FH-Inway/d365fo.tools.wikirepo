The d365fo.tools module is built upon the foundation of the PSFramework, which enables a full blown configuration store for PowerShell modules and scripts.

A very important note is that everything is working on local user as default. If you want to store the different configuration on a system wide fashion that option exists, but is beyond this guide. We will create a new guide to explain how to utilize the system wide feature.

We have several configuration sub sections:
* Environment
* Azure Storage Account
* Azure Logic App

## **Environment Configuration Store**
The environment configuration store is a multi array store, that can store different environment details, per environment, for your convenience.

**Available cmdlets / functions**
* Add-D365EnvironmentConfig
* Get-D365EnvironmentConfig
* Get-D365ActiveEnvironmentConfig
* Set-D365ActiveEnvironmentConfig

### **Add-D365EnvironmentConfig** 
`Add-D365EnvironmentConfig` is used to register a new environment and all its details. Please read more about the details of the cmdlet in the docs or `Get-Help Add-D365EnvironmentConfig`

It is **not** necessary to fill in all the details when using the `Add-D365EnvironmentConfig`

**Example on how to fill out the details for every parameter.**
This will create a environment configuration that is stored with the name "TEST"

```
$params = @{}
$params.URL = (Get-D365Url).Url
$params.SqlUser = "sqladmin"
$params.SqlPwd = "afafKHkhke"
$params.Company = "DAT"
$params.TfsUri = (Get-D365TfsUri).TfsUri
Add-D365EnvironmentConfig -Name TEST @params
```

### **Get-D365EnvironmentConfig** 
`Get-D365EnvironmentConfig` is used to show all the registered environments and their details. Please read more about the details of the cmdlet in the docs or `Get-Help Get-D365EnvironmentConfig`


**Example on how to list all environments**

```
Get-D365EnvironmentConfig

Name    : TEST
TfsUri  : https://projectname.visualstudio.com/
URL     : https://usnconeboxax1aos.cloud.onebox.dynamics.com/
Company : DAT
SqlUser : sqladmin
SqlPwd  : afafKHkhke
```

### **Set-D365ActiveEnvironmentConfig**
`Set-D365ActiveEnvironmentConfig` is used to register some of the in-memory variables that the module relies on, by promoting an environment configuration to the status active. It is simply done by using the name that you gave it while working with `Add-D365EnvironmentConfig` and all details will be copied over to a new set that is only used with the active environment logic. Please read more about the details of the cmdlet in the docs or `Get-Help Set-D365ActiveEnvironmentConfig`
