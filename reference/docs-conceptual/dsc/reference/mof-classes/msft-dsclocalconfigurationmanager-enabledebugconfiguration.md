---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: EnableDebugConfiguration メソッド
ms.openlocfilehash: f1290e4d898332361850ffc85aa0a8d79863c8f7
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953439"
---
# <a name="enabledebugconfiguration-method"></a>EnableDebugConfiguration メソッド

DSC リソースのデバッグを有効にします。

## <a name="syntax"></a>構文

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a>パラメーター

*BreakAll* \[in\] リソース スクリプトのすべての行にブレークポイントを設定します。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>解説

これは静的メソッドです。

## <a name="requirements"></a>必要条件

**MOF:** DscCore.mof

**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
