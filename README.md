---
ms.openlocfilehash: 6e36e6599e36218ce2a925dceda7aa0ee6811057
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068826"
---
# <a name="microsoft-open-source-code-of-conduct"></a><span data-ttu-id="65703-101">Microsoft オープン ソース倫理規定</span><span class="sxs-lookup"><span data-stu-id="65703-101">Microsoft Open Source Code of Conduct</span></span>

<span data-ttu-id="65703-102">このプロジェクトは [Microsoft オープン ソース論理規定](https://opensource.microsoft.com/codeofconduct/)を採用しています。</span><span class="sxs-lookup"><span data-stu-id="65703-102">This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="65703-103">詳細については[論理規定についてのよくある質問](https://opensource.microsoft.com/codeofconduct/faq/)をご覧ください。また、追加の質問やコメントがある場合は[opencode@microsoft.com](mailto:opencode@microsoft.com)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="65703-103">For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.</span></span>

<span data-ttu-id="65703-104">[![ビルドの状態](https://ci.appveyor.com/api/projects/status/onshefxnc4g4pv87/branch/staging?svg=true)](https://ci.appveyor.com/project/PowerShell/powershell-docs/branch/staging)</span><span class="sxs-lookup"><span data-stu-id="65703-104">[![Build status](https://ci.appveyor.com/api/projects/status/onshefxnc4g4pv87/branch/staging?svg=true)](https://ci.appveyor.com/project/PowerShell/powershell-docs/branch/staging)</span></span>

## <a name="powershell-documentation"></a><span data-ttu-id="65703-105">PowerShell ドキュメント</span><span class="sxs-lookup"><span data-stu-id="65703-105">PowerShell Documentation</span></span>

<span data-ttu-id="65703-106">PowerShell-Docs リポジトリへようこそ。PowerShell-Docs は、公式の PowerShell ドキュメントが格納されている場所です。</span><span class="sxs-lookup"><span data-stu-id="65703-106">Welcome to the PowerShell-Docs repository, housing the official PowerShell documentation.</span></span>

## <a name="repository-structure"></a><span data-ttu-id="65703-107">リポジトリの構造</span><span class="sxs-lookup"><span data-stu-id="65703-107">Repository Structure</span></span>

<span data-ttu-id="65703-108">このリポジトリ内の次の各最上位フォルダーには、[Microsoft Docs](https://docs.microsoft.com/powershell) に公開されるドキュメント セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="65703-108">Each of the following top-level folders in this repo contain a DocSet that is published to [Microsoft Docs](https://docs.microsoft.com/powershell).</span></span>

- <span data-ttu-id="65703-109">[/developer/](https://docs.microsoft.com/powershell/developer/) は、PowerShell SDK ドキュメントの今後のホームとなります</span><span class="sxs-lookup"><span data-stu-id="65703-109">[/developer/](https://docs.microsoft.com/powershell/developer/) is the future home of the PowerShell SDK documentation</span></span>
  - <span data-ttu-id="65703-110">現在、このコンテンツを MSDN から移行する処理を行っています</span><span class="sxs-lookup"><span data-stu-id="65703-110">We are in the process of migrating this content from MSDN</span></span>
- <span data-ttu-id="65703-111">[/dsc/](https://docs.microsoft.com/powershell/dsc/) は Desired State Configuration の機能に関するフォルダーです</span><span class="sxs-lookup"><span data-stu-id="65703-111">[/dsc/](https://docs.microsoft.com/powershell/dsc/) is for the Desired State Configuration feature</span></span>
- <span data-ttu-id="65703-112">[/gallery/](https://docs.microsoft.com/powershell/gallery) は [PowerShell ギャラリー](https://www.powershellgallery.com/)に関するフォルダーです</span><span class="sxs-lookup"><span data-stu-id="65703-112">[/gallery/](https://docs.microsoft.com/powershell/gallery) is for the [PowerShell Gallery](https://www.powershellgallery.com/)</span></span>
- <span data-ttu-id="65703-113">[/jea/](https://docs.microsoft.com/powershell/jea/) は Just Enough Administration の機能に関するフォルダーです</span><span class="sxs-lookup"><span data-stu-id="65703-113">[/jea/](https://docs.microsoft.com/powershell/jea/) is for the Just Enough Administration feature</span></span>
- <span data-ttu-id="65703-114">[/reference/](https://docs.microsoft.com/powershell/scripting/) は、バージョン 3.0、4.0、5.0、5.1、6.0 全体での PowerShell の概念説明のトピックおよびモジュールの参照用のフォルダーです</span><span class="sxs-lookup"><span data-stu-id="65703-114">[/reference/](https://docs.microsoft.com/powershell/scripting/) is for PowerShell conceptual topics and module reference across versions 3.0, 4.0, 5.0, 5.1, and 6.0</span></span>
  - <span data-ttu-id="65703-115">また、このコンテンツは、`Get-Help` コマンドレットによって取得されたヘルプ コンテンツのソースともなります</span><span class="sxs-lookup"><span data-stu-id="65703-115">This content is also the source of help content retrieved by the `Get-Help` cmdlet</span></span>
- <span data-ttu-id="65703-116">[/wmf](https://docs.microsoft.com/powershell/wmf/readme) には Windows Management Framework のリリース ノートと Windows の以前のバージョンに対して PowerShell の新しいバージョンを配布するために使用されるパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="65703-116">[/wmf](https://docs.microsoft.com/powershell/wmf/readme) contains release notes for the Windows Management Framework, the package used to distribute new versions of PowerShell to previous versions of Windows.</span></span>

## <a name="contributing"></a><span data-ttu-id="65703-117">投稿</span><span class="sxs-lookup"><span data-stu-id="65703-117">Contributing</span></span>

<span data-ttu-id="65703-118">[pull request](https://help.github.com/articles/using-pull-requests/)を使用して、積極的に投稿をこのリポジトリの*ステージング* ブランチに結合しています。</span><span class="sxs-lookup"><span data-stu-id="65703-118">We actively merge contributions into this repository via [pull request](https://help.github.com/articles/using-pull-requests/) into the *staging* branch.</span></span>
<span data-ttu-id="65703-119">コミュニティが投稿を自由に使用できるように、pull request を送信する前に[投稿の使用許諾契約に署名](https://cla.microsoft.com/)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65703-119">Please note that before you submit a pull request you must [sign a Contribution License Agreement](https://cla.microsoft.com/) to ensure that the community is free to use your submissions.</span></span>

<span data-ttu-id="65703-120">投稿の詳細については、[共同作成者ガイド](CONTRIBUTING.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65703-120">For more information on contributing, read our [contributor's guide](CONTRIBUTING.md).</span></span>
<span data-ttu-id="65703-121">共同作成者ガイドには、ドキュメント、お勧めのツール、スタイルや書式設定に関する要求を投稿する方法についての詳細情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="65703-121">The contributor's guide contains detail information about how to contribute documentation, suggested tools, and style and formatting requirements.</span></span>
<span data-ttu-id="65703-122">異なるバージョン間で一貫性のあるドキュメントを保つため、問題と Pull Request のテンプレートを使用してください。</span><span class="sxs-lookup"><span data-stu-id="65703-122">Please use the Issue and Pull Request templates to help keep documentation consistent across versions.</span></span>

## <a name="licenses"></a><span data-ttu-id="65703-123">ライセンス</span><span class="sxs-lookup"><span data-stu-id="65703-123">Licenses</span></span>

<span data-ttu-id="65703-124">このプロジェクトには、2 つのライセンス ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="65703-124">There are two license files for this project.</span></span>
<span data-ttu-id="65703-125">MIT ライセンスは、このリポジトリに含まれるコードに適用されます。</span><span class="sxs-lookup"><span data-stu-id="65703-125">The MIT License applies to the code contained in this repo.</span></span>
<span data-ttu-id="65703-126">Creative Commons ライセンスは、ドキュメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="65703-126">The Creative Commons license applies to the documentation.</span></span>