---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: スクリプト ウィンドウとコンソール ウィンドウでタブ補完を使用する方法
ms.assetid: 3b752c3c-0bd0-4eca-a2d3-2d5a37fd9d84
ms.openlocfilehash: 24a3f00987ff5ca4bf82d1a3206857ec3c4b3f09
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402214"
---
# <a name="how-to-use-tab-completion-in-the-script-pane-and-console-pane"></a><span data-ttu-id="39431-103">スクリプト ウィンドウとコンソール ウィンドウでタブ補完を使用する方法</span><span class="sxs-lookup"><span data-stu-id="39431-103">How to Use Tab Completion in the Script Pane and Console Pane</span></span>

<span data-ttu-id="39431-104">タブ補完は、スクリプト ウィンドウまたはコマンド ウィンドウで入力するときに、自動的に提供される支援機能です。</span><span class="sxs-lookup"><span data-stu-id="39431-104">Tab completion provides automatic help when you are typing in the Script Pane or in the Command Pane.</span></span> <span data-ttu-id="39431-105">この機能を活用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="39431-105">Use the following steps to take advantage of this feature:</span></span>

## <a name="to-automatically-complete-a-command-entry"></a><span data-ttu-id="39431-106">コマンドの入力を自動的に補完するには</span><span class="sxs-lookup"><span data-stu-id="39431-106">To automatically complete a command entry</span></span>

<span data-ttu-id="39431-107">コマンド ウィンドウまたはスクリプト ウィンドウでは、コマンドのいくつかの文字を入力し、Tab キーを押すと、目的の補完テキストを選択できます。</span><span class="sxs-lookup"><span data-stu-id="39431-107">In the Command Pane or Script Pane, type a few characters of a command and then press TAB to select the desired completion text.</span></span> <span data-ttu-id="39431-108">最初に入力したテキストで始まる項目が複数ある場合は、目的の項目が表示されるまで Tab キーを何回か押します。</span><span class="sxs-lookup"><span data-stu-id="39431-108">If multiple items begin with the text that you initially typed, then continue pressing Tab until the item you want appears.</span></span> <span data-ttu-id="39431-109">タブ補完は、コマンドレット名、パラメーター名、変数名、オブジェクトのプロパティ名、またはファイルのパスを入力する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39431-109">Tab completion can help with typing a cmdlet name, parameter name, variable name, object property name, or a file path.</span></span>

> [!NOTE]
> <span data-ttu-id="39431-110">スクリプト ウィンドウでは、.ps1、.psd1、.psm1 ファイルを編集している場合にのみ、Tab キーを押したときに自動的にコマンドが補完されます。</span><span class="sxs-lookup"><span data-stu-id="39431-110">In the Script Pane, pressing TAB will automatically complete a command only when you are editing .ps1, .psd1, or .psm1 files.</span></span> <span data-ttu-id="39431-111">コマンド ウィンドウに入力する場合は、常にタブ補完が機能します。</span><span class="sxs-lookup"><span data-stu-id="39431-111">Tab completion works any time when you are typing in the Command Pane.</span></span>

## <a name="to-automatically-complete-a-cmdlet-parameter-entry"></a><span data-ttu-id="39431-112">コマンドレット パラメーターの入力を自動的に補完するには</span><span class="sxs-lookup"><span data-stu-id="39431-112">To automatically complete a cmdlet parameter entry</span></span>

<span data-ttu-id="39431-113">コマンド ウィンドウまたはスクリプト ウィンドウで、コマンドレット名を入力し、その後にダッシュを入力し、次に Tab キーを押します。</span><span class="sxs-lookup"><span data-stu-id="39431-113">In the Command Pane or Script pane, type a cmdlet followed by a dash and then press TAB.</span></span>

<span data-ttu-id="39431-114">たとえば、「`Get-Process -`」と入力し、Tab キーを何回か押すと、コマンドレットの各パラメーターが順番に表示されます。</span><span class="sxs-lookup"><span data-stu-id="39431-114">For example, type `Get-Process -` and then press TAB multiple times to display each of the parameters for the cmdlet in turn.</span></span>

## <a name="see-also"></a><span data-ttu-id="39431-115">参照</span><span class="sxs-lookup"><span data-stu-id="39431-115">See Also</span></span>

- [<span data-ttu-id="39431-116">Windows PowerShell ISE の紹介</span><span class="sxs-lookup"><span data-stu-id="39431-116">Introducing the Windows PowerShell ISE</span></span>](Introducing-the-Windows-PowerShell-ISE.md)
- [<span data-ttu-id="39431-117">PowerShell タブを作成する方法</span><span class="sxs-lookup"><span data-stu-id="39431-117">How to Create a PowerShell Tab</span></span>](How-to-Create-a-PowerShell-Tab-in-Windows-PowerShell-ISE.md)