---
title: Windows PowerShell02 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92492a7e-257d-47d3-b119-89df3c5545e8
caps.latest.revision: 9
ms.openlocfilehash: 4d697e73ff4ab4cc4b88593f814d589f89005663
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978646"
---
# <a name="windows-powershell02-sample"></a>Windows PowerShell02 サンプル

このサンプルでは、実行空間プールの実行空間を使用して、コマンドを非同期的に実行する方法を示します。 このサンプルでは、コマンドの一覧を生成し、それらのコマンドを実行します。 Windows PowerShell エンジンは、必要に応じて、プールから実行空間を開きます。

## <a name="requirements"></a>要件

- このサンプルには、Windows PowerShell 2.0 が必要です。

## <a name="demonstrates"></a>例

このサンプルは、次の操作方法を示します。

- 実行空間の最小数と最大数を指定して RunspacePool オブジェクトを作成し、同時に開くことができるようにします。
- コマンドの一覧を作成します。
- コマンドを非同期に実行します。
- [Runspacepool. Getavailablerunspaces *](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces)メソッドを呼び出して、解放されている実行空間の数を確認します。
- コマンドの出力を、system.servicemodel [*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)メソッドを使用してキャプチャします。

## <a name="example"></a>例

このサンプルでは、実行空間プールの実行空間を開く方法と、それらの実行空間でコマンドを非同期に実行する方法を示します。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a>参照

[Windows PowerShell ホストアプリケーションの作成](./writing-a-windows-powershell-host-application.md)
