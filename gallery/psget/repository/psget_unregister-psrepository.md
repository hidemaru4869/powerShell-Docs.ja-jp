# Unregister-PSRepository

リポジトリの登録を解除します。

## 説明

Unregister-PSRepository コマンドレットは現在のユーザーのリポジトリの登録を解除します。
- PSGallery リポジトリの登録解除と再登録は、エンタープライズ シナリオと切断されたシナリオで許可されています。
- ユーザーは、実行するだけで PSGallery を再登録できます `Register-PSRepository -Default`
- PSGallery は、Publish-Module と Publish-Script コマンドレット内の既定の発行リポジトリであるため、PSGallery が登録されているリポジトリの一覧で使用できない場合はエラーがスローされます。

## コマンドレット構文

```powershell
Get-Command -Name Unregister-PSRepository -Module PowerShellGet -Syntax
```
## コマンドレット オンライン ヘルプ リファレンス

[Unregister-PSRepository](http://go.microsoft.com/fwlink/?LinkID=517130)

## コマンド例

```powershell
Unregister-PSRepository -Name "MyPrivateGallery"

Get-PSRepository exp | Unregister-PSRepository
```

### PSGallery リポジトリの登録解除と再登録は、エンタープライズ シナリオと切断されたシナリオで許可されています。
```powershell

# Unregister PSGallery repository
Unregister-PSRepository PSGallery

# Publish-Module throws an error when PSGallery is not a registered repository
Publish-Module -Name MyModule
publish-module : Unable to find repository 'PSGallery'. Use Get-PSRepository to see all available repositories. Try again after specifying a valid repository name. You can use 'Register-PSRepository -Default' to register the PSGallery repository.
At line:1 char:1
+ publish-module -name mymodule
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (PSGallery:String) [Publish-Module], ArgumentException
    + FullyQualifiedErrorId : PSGalleryNotFound,Publish-Module

# Re-register PSGallery repository
Register-PSRepository -Default
```

<!--HONumber=Aug16_HO3-->

