---
title: WideControl 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715ea055-037b-46ad-b70f-87b3f5134403
caps.latest.revision: 14
ms.openlocfilehash: 2742be0389a1bf04af100a490a59c0d938165811
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367991"
---
# <a name="widecontrol-element-format"></a>WideControl 要素 (書式)

ビューのワイド (単一値) リスト形式を定義します。 このビューには、各オブジェクトの1つのプロパティ値またはスクリプト値が表示されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) WideControl 要素 (形式)

## <a name="syntax"></a>構文

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、`WideControl` 要素の属性、子要素、および親要素について説明します。 `AutoSize` と `ColumnNumber` の要素を同時に指定することはできません。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[WideControl の AutoSize 要素 (形式)](./autosize-element-for-widecontrol-format.md)|省略可能な要素です。<br /><br /> データのサイズに基づいて列のサイズと列の数を調整するかどうかを指定します。|
|[WideControl の ColumnNumber 要素 (形式)](./columnnumber-element-for-widecontrol-format.md)|省略可能な要素です。<br /><br /> ワイドビューに表示される列の数を指定します。|
|[WideEntries 要素 (Format)](./wideentries-element-for-widecontrol-format.md)|必須の要素です。<br /><br /> ワイドビューの定義を提供します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[View 要素 (Format)](./view-element-format.md)|1つ以上の .NET オブジェクトを表示するために使用されるビューを定義します。|

## <a name="remarks"></a>コメント

ワイドビューを定義する場合は、`AutoSize` 要素または `ColumnNumber` を追加できますが、両方を追加することはできません。

ほとんどの場合、ワイドビューごとに1つの定義のみが必要ですが、同じビューを使用して異なる .NET オブジェクトを表示する場合は、複数の定義を指定できます。 このような場合は、オブジェクトまたはオブジェクトのセットごとに個別の定義を指定できます。

ワイドビューのコンポーネントの詳細については、「[ワイドビューコンポーネント](./creating-a-wide-view.md)」を参照してください。

## <a name="example"></a>例

次の例[は、`WideControl` のオブジェクトの](/dotnet/api/System.Diagnostics.Process)プロパティを表示するために使用される要素を示しています。

```xml
<View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>...</WideEntries>
  </WideControl>
</View>
```

ワイドビューの完全な例については、「 [Wide ビュー (Basic)](./wide-view-basic.md)」を参照してください。

## <a name="see-also"></a>参照

[WideControl の Autosize 要素 (形式)](./autosize-element-for-widecontrol-format.md)

[WideControl の ColumnNumber 要素 (形式)](./columnnumber-element-for-widecontrol-format.md)

[View 要素 (Format)](./view-element-format.md)

[WideEntries 要素 (Format)](./wideentries-element-for-widecontrol-format.md)

[ワイドビュー (基本)](./wide-view-basic.md)

[ワイドビューの作成](./creating-a-wide-view.md)

[PowerShell フォーマットファイルの作成](./writing-a-powershell-formatting-file.md)
