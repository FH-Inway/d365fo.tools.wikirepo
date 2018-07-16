So you are working with troubleshooting or maybe extending Dynamics 365 Finance & Operations.

* You might have a TableId and want to know what table(name) is behind that id.
* You might have a table(name) and want to know what TableId is behind that table name.
* You might have a TableId and FieldId and want to know what hides behind different ids.
* You might have a table(name) and want to know what fields are part of the table.
* You might have part of a field(name) and want to search all tables for a matching field.

Look no further!

We assume:
* That you already did run the `Install-Modele -Name d365fo.tools` on the machine / server you will be using for this. 
* That you will be running this from a Tier 1 machine /environment or one the AOS machines / Servers in the Tier 2 environment.

1. Start PowerShell (Start Menu - type powershell and click enter when you see the icon marked)
2. Run `Import-Module d365fo.tools`

**You want to search for CustTable, either by TableId or TableName**

```
Get-D365Table -Id 10347
```
*You only have the TableId: 10347 on your hands and your memory doesn't seem to remember that this is actually CustTable*

```
Get-D365Table -Name CustTable
```
*You only have the "CustTable" on your hands and your memory doesn't seem to remember that this is actually TableId: 10347*

**You want to see all fields for CustTable, either by TableId or TableName**
```
Get-D365TableField -TableId 10347
#OR
Get-D365TableField -TableId 10347 -IncludeTableDetails | Format-Table
```
*You only have the TableId: 10347 on your hands and you can't remember all fields that is part of that table*
```
Get-D365TableField -TableName CustTable
#OR
Get-D365TableField -TableName CustTable -IncludeTableDetails | Format-Table
```
*You only have the "CustTable" on your hands and you can't remember all fields that is part of that table*

**You want to see a specific field for CustTable, either by TableId or TableName, and either by FieldId or FieldName**
```
Get-D365TableField -TableId 10347 -FieldId 175
#OR
Get-D365TableField -TableId 10347 -Name vatnum
```
*You only have the TableId: 10347 on your hands and you can't the FieldId or FieldName for VATNUM*
```
Get-D365TableField -TableName CustTable -FieldId 175
#OR
Get-D365TableField -TableName CustTable -Name vatnum
```
*You only have the "CustTable" on your hands and you can't the FieldId or FieldName for VATNUM*

## **You are ready to take your PowerShell skills to the next level**
