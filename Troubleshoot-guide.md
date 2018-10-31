## **Gathering logs**
Get-PSFMessage -Errors | Format-List
Get-PSFMessage -Errors | Format-List | Out-file c:\temp\errors.txt

Get-PSFMessage -Level InternalComment | Format-List
Get-PSFMessage -Level InternalComment | Format-List | out-file C:\temp\sqlcommands.txt

## **Locate the folder where the module is installed**
explorer.exe (Split-Path (Get-Module d365fo.tools).Path -Parent)