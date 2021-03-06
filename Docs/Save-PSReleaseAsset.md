---
external help file: PSReleaseTools-help.xml
online version: 
schema: 2.0.0
---

# Save-PSReleaseAsset

## SYNOPSIS
Download the latest PowerShell v6 alpha releases

## SYNTAX

### All (Default)
```
Save-PSReleaseAsset [[-Path] <String>] [-All] [-Passthru] [-WhatIf] [-Confirm]
```

### Name
```
Save-PSReleaseAsset [[-Path] <String>] -Name <String[]> [-Passthru] [-WhatIf] [-Confirm]
```

### File
```
Save-PSReleaseAsset [[-Path] <String>] -Filename <String> -Size <String> -URL <String> [-Passthru] [-WhatIf]
 [-Confirm]
```

## DESCRIPTION
This command will download the latest PowerShell v6 alpha releases from the GitHub repository.
You can download everything or limit the download to specific platforms.

If you select Windows files you can use the -Format dynamic parameter to download only MSI or ZIP files.
Note that this will not work if you specify a combination of Windows and non-Windows platforms.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Save-PSReleaseAsset F:\PS6 -all
```

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\> Save-PSReleaseAsset -path F:\PS6 -name Win10 -format msi
```

### -------------------------- EXAMPLE 3 --------------------------
```
PS C:\> Save-PSReleaseAsset -path F:\PS6 -name Ubuntu14,Ubuntu16,CentOS
```

### -------------------------- EXAMPLE 4 --------------------------
```
PS C:\> Get-PSReleaseAsset -Family Ubuntu | Save-PSReleaseAsset -path D:\Temp
```

Get the Ubuntu assets and save them to D:\Temp

## PARAMETERS

### -Path
The destination folder for all downloads.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: .
Accept pipeline input: False
Accept wildcard characters: False
```

### -All
Download all files to the destination path.
This is the default behavior.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Select one or more platforms.

```yaml
Type: String[]
Parameter Sets: Name
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filename
The local filename for the download.

```yaml
Type: String
Parameter Sets: File
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Size
The target size for the download release.
If the actual download does not match this value you will get a warning.

```yaml
Type: String
Parameter Sets: File
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -URL
The URL for the download release.

```yaml
Type: String
Parameter Sets: File
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passthru


```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS
### system.string

## OUTPUTS
### system.io.fileinfo

## NOTES
Learn more about PowerShell:
http://jdhitsolutions.com/blog/essential-powershell-resources/

## RELATED LINKS
[Invoke-WebRequest]()
[Get-PSReleaseAsset]()
