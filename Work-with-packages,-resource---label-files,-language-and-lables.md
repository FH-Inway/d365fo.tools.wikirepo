**Work with packages, label files, language and labels**

```
Get-D365InstalledPackage
```
*Gets all installed packages on the system/machine*

```
Get-D365InstalledPackage -Name "ApplicationSuite"
```
*Gets the "ApplicationSuite" package*

```
Get-D365InstalledPackage -Name "ApplicationSuite" | Get-D365PackageLabelFile -Language "en-US"
```
*Gets all the "en-US" resource / label files from the ApplicationSuite package*

```
Get-D365InstalledPackage -Name "ApplicationSuite" | Get-D365PackageLabelFile -Language "en-US" -Name "PRO"
```
*Gets the PRO resource / label file from the "ApplicationSuite" package with the language "EN-US"*

```
Get-D365InstalledPackage -Name "ApplicationSuite" | Get-D365PackageLabelFile -Language "en-US" -Name "PRO" | Get-D365Label
```
*Gets all label details from the PRO resource / label file from the "ApplicationSuite" package with the language "EN-US"*

```
Get-D365InstalledPackage -Name "ApplicationSuite" | Get-D365PackageLabelFile -Language "*" -Name "PRO" | Get-D365Label -Name "@PRO505"
```
*Gets the "@PRO505" label details from the "PRO" resource / label file from the "ApplicationSuite" package, **across all languages***

```
Get-D365InstalledPackage -Name "ApplicationSuite" | Get-D365PackageLabelFile -Language "en-US" | Get-D365Label -Value "*qty*" -IncludePath
```
*Gets all "en-US" labels where the value contains "*qty*" from the "ApplicationSuite" package, **across all resource / label files***