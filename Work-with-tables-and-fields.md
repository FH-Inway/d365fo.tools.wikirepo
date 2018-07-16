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

**You want to search for custtable, either by TableId or TableName**

```
Get-D365Table -Id 10347
```
*You only have the id: 10347 on your hands and your memory doesn't seem to remember that this is actually CustTable*

```
Get-D365Table -Name Custtable
```
*You only have the CustTable on your hands and your memory doesn't seem to remember that this is actually TableId: 10347*