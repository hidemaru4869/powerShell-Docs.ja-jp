---
title: PowerShell Core のサポート ライフサイクル
description: PowerShell Core のサポートを管理するポリシー
ms.date: 03/09/2020
ms.openlocfilehash: c319371778eb4615559ae12e0cd153a535ed22bf
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "80500989"
---
# <a name="powershell-support-lifecycle"></a>PowerShell のサポート ライフサイクル

PowerShell は、Windows PowerShell とは別に出荷され、インストールされ、構成される別個のツール セットであり、コンポーネント セットです。 PowerShell は、Windows ライセンス契約には含まれていません。

PowerShell は、[有料サポート][]、[Microsoft Enterprise Agreements][enterprise-agreement]、[マイクロソフト ソフトウェア アシュアランス][assurance]など、従来の Microsoft サポート契約でサポートされています。
サポート リクエストで問題を報告して PowerShell の[サポート][]を受け、それに対して支払うこともできます。

## <a name="community-support"></a>コミュニティ サポート

GitHub でも[コミュニティ サポート][]を用意しています。問題やバグを報告したり、機能を要望したりできます。
また、Microsoft [PowerShell Tech コミュニティ][]の他のコミュニティ メンバーや、[PowerShell][pshub] ハブ ページのコミュニティ セクションに記載されているいずれかのフォーラムから、ヘルプを得られる場合もあります。 コミュニティによりご自身の問題が短期間で対処または解決されることは保証できません。 早急な対応が必要な問題の場合、従来の有料サポートをご利用ください。

## <a name="lifecycle-of-powershell-7"></a>PowerShell 7 のライフサイクル

PowerShell 7 のリリースでは、PowerShell は [Microsoft モダン ライフサイクル ポリシー][modern]で引き続きサポートされていますが、サポート日は [.NET Core のサポート ライフサイクル][Long-Term]にリンクされています。 このサービス方法では、お客様は長期サポート (LTS) リリースまたは最新リリースを選択できます。 PowerShell 7.0 は LTS リリースです。 サポートは、.NET Core 3.1 のサポートで終了します。 次の LTS リリースは、次の .NET Core LTS リリースの後になります。 最新のサポート終了日については、[「PowerShell リリースのサポート終了」の表](#powershell-releases-end-of-life)を参照してください。 LTS リリースの更新プログラムには、既存のワークロードへの影響を回避または最小限に抑えるように設計された重要なセキュリティとサービスの更新プログラムおよび修正プログラムのみが含まれます。

最新リリースは、LTS リリース間で発生するリリースです。 最新リリースには、重要な修正プログラム、イノベーション、新機能が含まれています。 最新リリースは、次の最新リリースまたは LTS リリース後 3 か月間サポートされます。

> [!IMPORTANT]
> サポートを受けるには、最新の更新パッチがインストールされている必要があります。 たとえば、PowerShell 7.0 を実行していて、7.0.1 がリリースされている場合、サポートを受けるには、7.0.1 に更新する必要があります。

## <a name="lifecycle-of-powershell-core-6x"></a>PowerShell Core 6.x のライフサイクル

PowerShell Core では、[Microsoft モダン ライフサイクル ポリシー][modern]を使用しました。 このサポート ライフサイクルでは、最新バージョンで最新の機能を常に提供します。

PowerShell Core のバージョン 6.x ブランチは約半年に一回更新されました (例: 6.0、6.1、6.2 など)。 ただし、PowerShell 7 のリリースと共に、6.x のマイナー バージョン リリースはなくなります。 PowerShell 6.2.x は、サポートされている間、サービス更新プログラムが引き続き受信されます。

> [!IMPORTANT]
> 引き続きサポートを受けるには、新しいマイナー バージョンの公開後、6 か月以内に更新する必要があります。

たとえば、PowerShell Core 6.1 が 2018 年 7 月 1 日に公開された場合、サポートを維持するには、2019 年 1 月 1 日までに PowerShell Core 6.1 に更新する必要があります。

> [!IMPORTANT]
> サポートを受け続けるには、それぞれの新しいパッチ バージョンのリリース後 30 日以内に更新する必要があります。

たとえば、PowerShell Core 6.1 を実行していて 2019 年 2 月 19 日に 6.1.3 がリリースされた場合、サポートを維持するには、リリースの 30 日後である 2019 年 3 月 21 日までに PowerShell Core 6.1.3 に更新する必要があります。 必要な修正プログラムが見つかった場合、その修正プログラムは次の累積的な更新プログラムでリリースされます。

Modern Lifecycle Policy では、製品 (つまり、PowerShell Core) のサポートを終了する 12 か月前にお客様に通知することを Microsoft の義務としています。

## <a name="supported-platforms"></a>サポートされているプラットフォーム

お使いのプラットフォームと PowerShell Core のバージョンが正式にサポートされているかどうかを確認するには、次の表を参照してください。

また、弊社のコミュニティでも一部のプラットフォームに向けたパッケージを提供していますが、これらは正式にはサポートされていません。 これらのパッケージは、表の中で `Community` とマークされています。

`Experimental` としてリストされているプラットフォームは、正式にはサポートされていませんが、実験とフィードバックのために使用することができます。

| プラットフォーム                                          |      6.2      |    7.0    |
| ------------------------------------------------- | :-----------: | :-------: |
| Windows 8.1、10                               |   サポートされています   | サポートされています |
| Windows Server 2012 R2、2016                      |   サポートされています   | サポートされています |
| [Windows Server 半期チャネル][semi-annual] |   サポートされています   | サポートされています |
| Ubuntu 16.04 および 18.04                            |   サポートされています   | サポートされています |
| Ubuntu 19.10 (スナップ パッケージを使用)                   |   コミュニティ   | コミュニティ |
| Ubuntu 20.04 (スナップ パッケージを使用)                   |   コミュニティ   | コミュニティ |
| Debian 9                                          |   サポートされています   | サポートされています |
| Debian 10                                         | サポートされていません | サポートされています |
| CentOS 7                                          |   サポートされています   | サポートされています |
| CentOS 8                                          | サポートされていません | サポートされています |
| Red Hat Enterprise Linux 7                        |   サポートされています   | サポートされています |
| Red Hat Enterprise Linux 8                        | サポートされていません | サポートされています |
| Fedora 30                                         | サポートされていません | サポートされています |
| Alpine 3.8                                        |   注を参照    | 注を参照  |
| Alpine 3.9 および 3.10                               | サポートされていません | 注を参照  |
| macOS 10.12 以降                                      |   サポートされています   | サポートされています |
| Arch                                              |   コミュニティ   | コミュニティ |
| Raspbian                                          |   コミュニティ   | コミュニティ |
| Kali                                              |   コミュニティ   | コミュニティ |
| AppImage (複数の Linux プラットフォームで機能)      |   コミュニティ   | コミュニティ |
| [Snap パッケージ](https://snapcraft.io/powershell)   |   注を参照    | 注を参照  |

> [!NOTE]
> パッケージを実行しているディストリビューションと同様に、Snap パッケージがサポートされます。

> [!NOTE]
> Alpine では、CIM、PowerShell リモート処理、および DSC はサポートされていません。

## <a name="powershell-releases-end-of-life"></a>PowerShell リリースのサポート終了

[PowerShell のライフサイクル](#lifecycle-of-powershell-7)に基づき、さまざまなリリースがサポートされなくなる日付を次の表に示します。

| Version |    サポート終了     |
| :-----: | ------------------ |
|   7.0   | 2022 年 12 月 3 日   |
|   6.2   | 2020 年 9 月 4 日  |
|   6.1   | 2019 年 9 月 28 日 |
|   6.0   | 2019 年 2 月 13 日  |

## <a name="unsupported-platforms"></a>サポートされないプラットフォーム

プラットフォームのバージョンが、プラットフォームの所有者によって定義された有効期限を迎えると、PowerShell Core でもそのプラットフォームのバージョンがサポートされなくなります。 アクセスする必要があるユーザーは引き続き以前にリリースされたパッケージを利用できますが、公式のサポートと更新プログラムはどんな種類のものも提供されなくなります。

そのため、ディストリビューションの所有者によって次のバージョンのサポートは終了され、サポートされていません。

|    プラットフォーム    | Version |                                                         有効期限切れ                                                          |
| -------------- | :-----: | ---------------------------------------------------------------------------------------------------------------------------- |
| Debian         |    8    | [2018 年 6 月](https://lists.debian.org/debian-security-announce/2018/msg00132.html)                                            |
| Fedora         |   24    | [2017 年 8 月](https://fedoramagazine.org/fedora-24-eol/)                                                                     |
| Fedora         |   25    | [2017 年 12 月](https://fedoramagazine.org/fedora-25-end-life/)                                                              |
| Fedora         |   26    | [2018 年 5 月](https://fedoramagazine.org/fedora-26-end-life/)                                                                   |
| Fedora         |   27    | [2018 年 11 月](https://fedoramagazine.org/fedora-27-end-of-life/)                                                           |
| Fedora         |   28    | [2019 年 5 月](https://fedoramagazine.org/fedora-28-end-of-life/)                                                                |
| openSUSE       |  42.1   | [2017 年 5 月](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)                                      |
| openSUSE       |  42.2   | [2018 年 1 月](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html)                                  |
| openSUSE       |  42.3   | [2019 年 7 月](https://lists.opensuse.org/opensuse-security-announce/2019-07/msg00000.html)                                     |
| Ubuntu         |  14.04  | [2019 年 4 月](https://wiki.ubuntu.com/Releases)                                                                               |
| Ubuntu         |  16.10  | [2017 年 7 月](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)                                         |
| Ubuntu         |  17.04  | [2018 年 1 月](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)                                           |
| Ubuntu         |  17.10  | [2018 年 7 月](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)                                         |
| Windows        |    7    | [2020 年 1 月](https://support.microsoft.com/help/4057281/windows-7-support-ended-on-january-14-2020)                        |
| Windows Server | 2008 R2 | [2020 年 1 月](https://support.microsoft.com/help/4456235/end-of-support-for-windows-server-2008-and-windows-server-2008-r2) |

## <a name="notes-on-licensing"></a>ライセンスに関する注意事項

PowerShell Core は [MIT ライセンス][]の下で提供されます。 このライセンスの下で、有料サポート契約がないときは、ユーザーには[コミュニティ サポート][]のみが与えられます。 コミュニティ サポートの場合、マイクロソフトは回答や解決を保証しません。

## <a name="windows-powershell-compatibility"></a>Windows PowerShell の互換性

PowerShell のサポート ライフサイクルでは、PowerShell 7 リリース パッケージ外に付属するモジュールは対象とされません。 たとえば、Windows Server に付属する `ActiveDirectory` モジュールを使用することは、[Windows サポート ライフサイクル][]のサポート対象です。

PowerShell 7 では、Windows PowerShell 用に記述された既存の PowerShell モジュールとの互換性が向上しています。
詳細については、[Windows の互換性について][]に関する記事と[モジュールの互換性の一覧][]を参照してください。

> [!NOTE]
> [**WindowsPSModulePath**](https://www.powershellgallery.com/packages/WindowsPSModulePath) モジュールは、PowerShell 7 では不要になり、サポートされていません。

## <a name="experimental-features"></a>試験的な機能

[試験的な機能][]には[コミュニティ サポート](#community-support)のみが与えられます。

## <a name="release-history"></a>リリース履歴

PowerShell のメジャー リリースのタイムラインを、次の表に示します。 この表は、履歴の参照用に掲載されています。 サポート ライフサイクルの決定に使用するためのものではありません。

|       Version        | リリース日 |                                                                     Note                                                                      |
| -------------------- | :----------: | --------------------------------------------------------------------------------------------------------------------------------------------- |
| PowerShell 7.0 (LTS) |   2020 年 3 月   | .NET Core 3.1 (LTS) 上に構築されています                                                                                                                  |
| PowerShell 6.0       |   2018 年 1 月   | 最初のリリースは .NET Core 2.1 上に構築されています。 Windows、Linux、macOS にインストールできます。                                                              |
| PowerShell 5.1       |   2016 年 8 月   | Windows 10 Anniversary Update および Windows Server 2016 でリリースされました                                                                             |
| PowerShell 5.0       |   2016 年 2 月   | Windows Management Framework (WMF) 5.0 でリリースされました                                                                                            |
| PowerShell 4.0       |   2013 年 10 月   | Windows 8.1 および Windows Server 2012 R2 に統合されています。 Windows 7 SP1、Windows Server 2008 R2 SP1、Windows Server 2012 にインストールできます。 |
| PowerShell 3.0       |   2012 年 10 月   | Windows 8 および Windows Server 2012 に統合されています。 Windows 7 SP1、Windows Server 2008 SP1、Windows Server 2008 R2 SP1 にインストールできます。  |
| PowerShell 2.0       |   2009 年 7 月   | Windows 7 および Windows Server 2008 R2 に統合されています。 Windows XP SP3、Windows Server 2003 SP2、Windows Vista SP1 にインストールできます。            |
| PowerShell 1.0       |   2006 年 11 月   | Windows XP SP2、Windows Server 2003 SP1、Windows Vista にインストールできます。 Windows Server 2008 のオプションのコンポーネントです。                          |

<!-- hyperlink references -->
[有料サポート]: https://support.microsoft.com/hub/4343728/support-for-business
[enterprise-agreement]: https://www.microsoft.com/licensing/licensing-programs/enterprise.aspx
[assurance]: https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx
[コミュニティ サポート]: /powershell/scripting/community/community-support
[pshub]: /powershell
[PowerShell Tech コミュニティ]: https://techcommunity.microsoft.com/t5/PowerShell/ct-p/WindowsPowerShell
[サポート]: https://support.microsoft.com/assistedsupportproducts
[modern]: https://support.microsoft.com/help/30881/modern-lifecycle-policy
[Long-Term]: https://dotnet.microsoft.com/platform/support/policy/dotnet-core
[lifecycle-chart]: ./images/modern-lifecycle.png
[semi-annual]: /windows-server/get-started/semi-annual-channel-overview
[MIT ライセンス]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
[Windows の互換性について]: /powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility
[Windows サポート ライフサイクル]: https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet
[モジュールの互換性の一覧]: /powershell/scripting/whats-new/module-compatibility
[WindowsPSModulePath]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[試験的な機能]: /powershell/module/microsoft.powershell.core/about/about_powershell_config#experimentalfeatures
