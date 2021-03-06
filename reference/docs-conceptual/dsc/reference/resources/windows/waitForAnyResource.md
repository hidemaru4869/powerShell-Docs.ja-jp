---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WaitForAny リソース
ms.openlocfilehash: 61fee456d2652e08ed9bdbe64457627ff5b2e145
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71952999"
---
# <a name="dsc-waitforany-resource"></a>DSC WaitForAny リソース

> 適用先:Windows PowerShell 5.1

**WaitForAny** Desired State Configuration (DSC) リソースを [DSC 構成](../../../configurations/configurations.md)のノード ブロック内で使用して、他のノードの構成の依存関係を指定できます。

このリソースは、**ResourceName** プロパティで指定されたリソースが、**NodeName** プロパティで定義された任意のターゲット ノードで目的の状態になった場合に成功します。

> [!NOTE]
> **WaitForAny** リソースでは、Windows リモート管理を使用して他のノードの状態を確認します。 WinRM でのポートとセキュリティ要件の詳細については、「[PowerShell リモート処理のセキュリティに関する考慮事項](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6)」を参照してください。

## <a name="syntax"></a>構文

```Syntax
WaitForAny [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string[]]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Properties

|プロパティ |説明 |
|---|---|
|ResourceName |依存するリソースの名前。 このリソースが別の構成に属している場合は、名前を `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]` という書式に設定します。 |
|NodeName |依存するリソースのターゲット ノード。 |
|RetryIntervalSec |再試行するまでの秒数。 最小値は 1 です。 |
|RetryCount |再試行の回数の最大数。 |
|ThrottleLimit |同時に接続するコンピューターの数。 既定値は、`New-CimSession` の既定値です。 |

## <a name="common-properties"></a>共通プロパティ

|プロパティ |説明 |
|---|---|
|DependsOn |このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。 |
|PsDscRunAsCredential |リソース全体を実行するための資格情報を設定します。 |

> [!NOTE]
> **PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。 詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。

## <a name="example"></a>例

このリソースを使用する方法の例は、「[ノードの相互依存関係の指定](../../../configurations/crossNodeDependencies.md)」を参照してください。