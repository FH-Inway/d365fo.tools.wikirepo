You ran into an issue with the module and want to try and fix it, while testing things?

```
Set-PSFConfig d365fo.tools.Import.IndividualFiles -Value $true
Import-Module d365fo.tools -Force -Passthru
```

You need better file names and line numbers while playing around?

```
Set-PSFConfig d365fo.tools.Import.DoDotSource -Value $true 
Import-Module d365fo.tools -Force -Passthru
```