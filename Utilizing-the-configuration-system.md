The d365fo.tools module is built upon the foundation of the PSFramework, which enables a full blown configuration store for PowerShell modules and scripts.

A very important note is that everything is working on local user as default. If you want to store the different configuration on a system wide fashion that option exists, but is beyond this guide. We will create a new guide to explain how to utilize the system wide feature.

We have several configuration sub sections:
* Environment
* Azure Storage Account
* Azure Logic App

## **Environment Configuration Store**
The environment configuration store is a multi array store, that can store different environment details, per environment, for your convenience.

Available cmdlets / functions
* Add-D365EnvironmentConfig
* Get-D365EnvironmentConfig
* Get-D365ActiveEnvironmentConfig
* Set-D365ActiveEnvironmentConfig

### **Add-D365EnvironmentConfig** 
`Add-D365EnvironmentConfig` is used to register a new environment and all its details. Please read more about the details of the cmdlet in the docs or `Get-Help Add-D365EnvironmentConfig`

It is not necessary to fill in all the details when using the `Add-D365EnvironmentConfig`

```
$params = @{}
$params.URL = (Get-D365Url).Url
$params.SqlUser = "sqladmin"
$params.SqlPwd = "afafKHkhke"
$params.Company = "DAT"
$params.TfsUri = (Get-D365TfsUri).TfsUri
```
