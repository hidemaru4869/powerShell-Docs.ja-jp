# Update-ModuleManifest
モジュール マニフェスト ファイルを更新します。

## 説明

Update-ModuleManifest コマンドレットは、モジュール マニフェスト (.psd1) ファイルを更新します。

### メモ
    - DscResourcesToExport is only supported on the latest PowerShell version 5.0. We won’t be able to update the field if you are running on lower versions of PowerShell.

## コマンドレット構文
```powershell
Get-Command -Name Update-ModuleManifest -Module PowerShellGet -Syntax
```

## コマンドレット オンライン ヘルプ リファレンス

[Update-ModuleManifest](http://go.microsoft.com/fwlink/?LinkId=619311)

## コマンド例

この新しいコマンドレットを使用して、入力プロパティ値でマニフェスト ファイルを更新します。 このコマンドレットは、New-ModuleManifest が受け取るすべてのパラメーターを受け取ります。

多数のモジュール作成者は FunctionsToExport、CmdletsToExport などのエクスポートされた値に "\*" を指定します。PowerShell ギャラリーへのモジュールの発行時に、指定されていない関数やコマンドはギャラリーに正しく設定されません。 このため、モジュール作成者はマニフェストを適切な値で更新することをお勧めします。

プロパティをエクスポートしたモジュールがある場合は、Update-ModuleManifest によって、エクスポートされた関数、コマンドレット、変数などの情報を指定されたマニフェスト ファイルに入力します。
```powershell
Get-Content -Path "C:\Temp\PSGTEST-TestPackageMetadata\2.5\PSGTEST-TestPackageMetadata.psd1"
@{
# Script module or binary module file associated with this manifest.
# RootModule = ''
# Version number of this module.
ModuleVersion = '2.5'
# ID used to uniquely identify this module
GUID = '610e5c5b-dc42-4eaa-8511-ebfb44066d5e'

#(Other properties removed here for Simplicity…)

# Functions to export from this module
FunctionsToExport = '*'
# Cmdlets to export from this module
CmdletsToExport = '*'
# Variables to export from this module
VariablesToExport = '*'
# Aliases to export from this module
AliasesToExport = '*'
}
```

Update-ModuleManifest の後:
```powershell
Update-ModuleManifest -Path "C:\Temp\PSGTEST-TestPackageMetadata\2.5\PSGTEST-TestPackageMetadata.psd1"
Get-Content -Path "C:\Temp\PSGTEST-TestPackageMetadata\2.5\PSGTEST-TestPackageMetadata.psd1"
#
# Module manifest for module 'NewManifest'
#
# Generated by: author name
#
# Generated on: 11/13/2015
#
@{
# Script module or binary module file associated with this manifest.
# RootModule = ''
# Version number of this module.
ModuleVersion = '2.5'
# ID used to uniquely identify this module
GUID = '610e5c5b-dc42-4eaa-8511-ebfb44066d5e'
# Functions to export from this module
FunctionsToExport = 'Get-FooFn Get-FooWF'
# Cmdlets to export from this module
CmdletsToExport = 'Test-PSGetTestCmdlet'
}
```

各モジュールに、関連付けられているメタデータ フィールドもあります。 PowrShell ギャラリーでメタデータを正しく表示するためには、Update-ModuleManifest を使用して PrivateData でこれらのフィールドに入力できます。

```powershell
Update-ModuleManifest -Path "C:\Temp\PSGTEST-TestPackageMetadata\2.5\PSGTEST-TestPackageMetadata.psd1" -Tags "Tag1" -LicenseUri "http://license.com" -ProjectUri "http://project.com" -IconUri "http://icon.com" -ReleaseNotes "Test module"
```

マニフェスト ファイル テンプレートからの PrivateData ハッシュ テーブルには、次のプロパティがあります

```powershell
# Private data to pass to the module specified in RootModule/ModuleToProcess. This may also contain a PSData hashtable with additional module metadata used by PowerShell.
PrivateData = @{
    PSData = @{
        # Tags applied to this module. These help with module discovery in online galleries.
        # Tags = @()

        # A URL to the license for this module.
        # LicenseUri = ''
    
        # A URL to the main website for this project.
        # ProjectUri = ''
        
        # A URL to an icon representing this module.
        # IconUri = ''
        
        # ReleaseNotes of this module
        # ReleaseNotes = ''
        
        # External dependent modules of this module
        # ExternalModuleDependencies = ''
    } # End of PSData hashtable
} # End of PrivateData hashtable
```



<!--HONumber=Aug16_HO3-->

