So you are working with the task of creating bacpac files and moving them between different Tiers. You did read the guide on docs.microsoft.com and found it to be cumbersome. You find it rather tricky getting the files in and out of the different environments.

Look no further!

We assume:
* You already use the New-D365Bacpac cmdlet for creating the desired bacpac file
* You already have an active Azure Storage Account
* You already have created the needed tokens for the Azure Storage Account

You need to have the **Azure Storage Account Id**, **Access Token** and the name of the **blob** / **container** ready. This is provided to you from https://portal.azure.com when you create the **Access Token**.

1. Start PowerShell (Start Menu - type powershell and click enter when you see the icon marked)
2. Run `Import-Module d365fo.tools`

**Listing files**
```
Get-D365AzureStorageFile -AccountId "miscfiles" -AccessToken "xx508xx63817x752xx74004x30705xx92x58349x5x78f5xx34xxxxx51" -Blobname "backupfiles"
```
*This will get the details of all the files stored in the **"backupfiles"** blob / container inside the **"miscfiles"** Azure Storage Account*

```
Get-D365AzureStorageFile -AccountId "miscfiles" -AccessToken "xx508xx63817x752xx74004x30705xx92x58349x5x78f5xx34xxxxx51" -Blobname "backupfiles" -Name "*UAT*"
```
*This will get the details of all the files where the name contains "UAT" that are stored in the **"backupfiles"** blob / container inside the **"miscfiles"** Azure Storage Account*

**Downloading files**
```
Invoke-D365AzureStorageDownload -AccountId "miscfiles" -AccessToken "xx508xx63817x752xx74004x30705xx92x58349x5x78f5xx34xxxxx51" -Blobname "backupfiles" -FileName "OriginalUAT.bacpac" -Path "c:\temp" 
```
*This will download the **"OriginalUAT.bacpac"** file from the Azure Storage Account and store it in **"c:\temp\OriginalUAT.bacpac"**.

```
Invoke-D365AzureStorageDownload -AccountId "miscfiles" -AccessToken "xx508xx63817x752xx74004x30705xx92x58349x5x78f5xx34xxxxx51" -Blobname "backupfiles" -Path "c:\temp" -GetLatest
```
*This will download the file with the latest modified datetime stamp from the Azure Storage Account and store it in **"c:\temp"** - the full file path will be returned as output when done.

**Uploading files**

```
Invoke-D365AzureStorageUpload -AccountId "miscfiles" -AccessToken "xx508xx63817x752xx74004x30705xx92x58349x5x78f5xx34xxxxx51" -Blobname "backupfiles" -Filepath "c:\temp\bacpac\UAT_20180701.bacpac" -DeleteOnUpload
```
*This will upload the **"c:\temp\bacpac\UAT_20180701.bacpac"** to the Azure Storage Account and delete the file located on the machine when the upload is completed.*