So you are working inside your Visual Studio from your development machine. 

You try to open the table browser from inside Visual Studio and see the classic error:
"You are not authorize to login with your current credentials. You will be redirected to the login page in a few seconds"

Look no further!

We assume:
* The machine is onebox / local VM machine downloaded from Microsoft.

**Note:**
This shouldn't be required on ANY machine deployed from LCS.

1. Start PowerShell (Start Menu - type powershell and click enter when you see the icon marked)
2. Run `Import-Module d365fo.tools`
3. Run `Get-D365OfflineAuthenticationAdminEmail` to see what the current e-mail address is
4. Run `Set-D365OfflineAuthenticationAdminEmail -Email "admin@contoso.com"` to change the e-mail/user to admin@contoso.com
5. Restart your Visual Studio, remember to start it elevated (Run As Administrator)
6. Start the Table Browser again and continue with your work.

