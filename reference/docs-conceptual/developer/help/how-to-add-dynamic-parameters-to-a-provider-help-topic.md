---
title: プロバイダーに動的パラメーターを追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e20e5ad6-a6e6-4a63-9d42-1ac54214f748
caps.latest.revision: 5
ms.openlocfilehash: 57978616f4a868b1ad260f4b557f9b699a1ef3ab
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557126"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a>プロバイダーのヘルプ トピックに動的パラメーターを追加する方法

このセクションでは、プロバイダーヘルプトピックの**動的パラメーター**セクションにデータを設定する方法について説明します。

*動的パラメーター*とは、指定された条件下でのみ使用可能なコマンドレットまたは関数のパラメーターです。

プロバイダーのヘルプトピックに記載されている動的パラメーターは、プロバイダーのドライブでコマンドレットまたは関数が使用されている場合に、プロバイダーがコマンドレットまたは関数に追加する動的パラメーターです。

動的パラメーターは、プロバイダーのカスタムコマンドレットのヘルプにも記載されています。 プロバイダーのヘルプとカスタムコマンドレットのヘルプの両方を作成するときは、両方のドキュメントに動的パラメーターのドキュメントを含めてください。

プロバイダーが動的パラメーターを実装していない場合、プロバイダーヘルプトピックには空の要素が含まれ `DynamicParameters` ます。

### <a name="to-add-dynamic-parameters"></a>動的パラメーターを追加するには

1. Dll-help ファイル*の*要素内に、 `providerHelp` 要素を追加 `DynamicParameters` します。 要素は、要素の `DynamicParameters` 後、要素の前に記述する必要があり `Tasks` `RelatedLinks` ます。

   たとえば、次のように入力します。

    ```xml
    <providerHelp>
        <Tasks>
        </Tasks>
        <DynamicParameters>
        </DynamicParameters>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

   プロバイダーが動的パラメーターを実装していない場合は、 `DynamicParameters` 要素を空にすることができます。

2. 要素内で `DynamicParameters` 、各動的パラメーターに要素を追加し `DynamicParameter` ます。

   たとえば、次のように入力します。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

3. 各要素に、 `DynamicParameter` `Name` 要素と要素を追加し `CmdletSupported` ます。

   |要素名|説明|
   |------------------|-----------------|
   |名前|パラメーター名を指定します。|
   |サポートされているもの|パラメーターが有効なコマンドレットを指定します。 コマンドレット名のコンマ区切りリストを入力します。|

   たとえば、次の XML ドキュメントでは、 `Encoding` Windows PowerShell FileSystem プロバイダーによって、、コマンドレットに追加される動的パラメーターについて説明して `Add-Content` `Get-Content` `Set-Content` います。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

4. 各 `DynamicParameter` 要素に要素を追加 `Type` します。 要素は、 `Type` `Name` 動的パラメーターの値の .net 型を含む要素のコンテナーです。

   たとえば、次の XML は、動的パラメーターの .NET 型 `Encoding` が、 [Microsoft. PowerShell. Filesystemコマンドレット](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding)の列挙体であることを示しています。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
    ...
    </DynamicParameters>
    ```

5. `Description`要素を追加します。これには、動的パラメーターの簡単な説明が含まれています。 説明を作成する場合は、「[パラメーター情報を追加する方法](./how-to-add-parameter-information.md)」のすべてのコマンドレットパラメーターに指定されているガイドラインを使用します。

   たとえば、次の XML には、動的パラメーターの説明が含まれてい `Encoding` ます。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
            <Description> Specifies the encoding of the output file that contains the content. </Description>
    ...
    </DynamicParameters>
    ```

6. `PossibleValues`要素とその子要素を追加します。 これらの要素には、動的パラメーターの値が記述されています。 この要素は、列挙値用に設計されています。 スイッチパラメーターを使用した場合など、動的パラメーターに値がない場合、または値を列挙できない場合は、空の要素を追加し `PossibleValues` ます。

   次の表に、 `PossibleValues` 要素とその子要素の一覧とその説明を示します。

   |要素名|説明|
   |------------------|-----------------|
   |指定した値|この要素はコンテナーです。 その子要素について以下に説明します。 `PossibleValues`各プロバイダーヘルプトピックに1つの要素を追加します。 要素は空にすることができます。|
   |指定した値|この要素はコンテナーです。 その子要素について以下に説明します。 `PossibleValue`動的パラメーターの値ごとに1つの要素を追加します。|
   |値|値の名前を指定します。|
   |Description|この要素には要素が含まれてい `Para` ます。 要素内のテキストは、 `Para` 要素で指定されている値を表し `Value` ます。|

   たとえば、次の XML は、 `PossibleValue` 動的パラメーターの1つの要素を示して `Encoding` います。

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
    ...
            <Description> Specifies the encoding of the output file that contains the content. </Description>
            <PossibleValues>
                <PossibleValue>
                    <Value> ASCII </Value>
                    <Description>
                        <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                    </Description>
                </PossibleValue>
    ...
            </PossibleValues>
    </DynamicParameters>
    ```

## <a name="example"></a>例

次の例は、 `DynamicParameters` 動的パラメーターの要素を示して `Encoding` います。

```xml
<DynamicParameters/>
    <DynamicParameter>
        <Name> Encoding </Name>
        <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
        <Type>
            <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
        <Type>
        <Description> Specifies the encoding of the output file that contains the content. </Description>
        <PossibleValues>
            <PossibleValue>
                <Value> ASCII </Value>
                <Description>
                    <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                </Description>
            </PossibleValue>
            <PossibleValue>
                <Value> Unicode </Value>
                <Description>
                    <para> Encodes in UTF-16 format using the little-endian byte order. </para>
                </Description>
            </PossibleValue>
        </PossibleValues>
</DynamicParameters>
```
