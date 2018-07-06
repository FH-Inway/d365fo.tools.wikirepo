So you are working on a project that needs to ensure it can quickly restore a Tier 2 (MS hosted) environment. 

You noticed that it takes a fair amount of manuel work and clicking around, before actually starting the export process of the desired bacpac file?

Look no further!

We assume:
* That you already did run the `Install-Modele -Name d365fo.tools` on the machine / server you will be using for this. 
* That you will be running this from 1 one the AOS machines / Servers in the Tier 2 environment.
* That you have installed the correct SSMS version that matches the receiving environment installation

You need have the sql username and password ready, this is found on LCS under the implementation project and the details page for the desired environment.

1. Start PowerShell (Start Menu - type powershell and click enter when you see the icon marked)
2. Run `Import-Module d365fo.tools`
3. Run `New-BacPacv2 -ExecutionMode FromAzure -SqlUser User123 -SqlPwd "Password123" -NewDatabaseName BacpacPrep -BacpacDirectory C:\Temp\Bacpac\ -BacpacName "BacpacPrep-20180701"`
   - Remember to fill in the correct SqlUser and SqlPwd obtained from LCS
   - Ensure that you have enough space to handle bacpac file on disk
4. Wait for the command to finish

When done the cmdlet will tell you where the file is stored and how much time it took.

If you want you can then upload the file to an Azure Storage (blob) account.

We assume:
* That you already did run the `Install-Module "Azure.Storage"` from an elevated powershell.

1. Start PowerShell (Start Menu - type powershell and click enter when you see the icon marked)
2. Run `Import-Module d365fo.tools`
3. Run `"C:\Temp\Bacpac\BacpacPrep-20180701.bacpac" | Invoke-AzureStorageUpload -AccountId "miscfiles" -AccessToken "xx508xx63817x752xx74004x30705xx92x58349x5x78f5xx34xxxxx51" -Blobname "backupfiles"`
   - Remember to update the script with correct values for -AccountId, -AccessToken og -Blobname

**Advanced example - oneliner that creates the bacpac file, uploads it to azure storage and deletes it**
```
New-BacPacv2 -ExecutionMode FromAzure -SqlUser User123 -SqlPwd "Password123" -NewDatabaseName BacpacPrep -BacpacDirectory C:\Temp\Bacpac\ -BacpacName "BacpacPrep-20180701" | Invoke-AzureStorageUpload -AccountId "miscfiles" -AccessToken "xx508xx63817x752xx74004x30705xx92x58349x5x78f5xx34xxxxx51" -Blobname "backupfiles" -DeleteOnUpload
```