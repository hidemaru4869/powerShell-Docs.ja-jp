---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: WMI オブジェクトの取得 Get CimInstance
ms.openlocfilehash: 4ff47844fd367a49f554c7c05c491bdddf28eabc
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "77002652"
---
# <a name="getting-wmi-objects-get-ciminstance"></a><span data-ttu-id="71fe5-103">WMI オブジェクトの取得 (Get-CimInstance)</span><span class="sxs-lookup"><span data-stu-id="71fe5-103">Getting WMI Objects (Get-CimInstance)</span></span>

## <a name="getting-wmi-objects-get-ciminstance"></a><span data-ttu-id="71fe5-104">WMI オブジェクトの取得 (Get-CimInstance)</span><span class="sxs-lookup"><span data-stu-id="71fe5-104">Getting WMI Objects (Get-CimInstance)</span></span>

<span data-ttu-id="71fe5-105">Windows Management Instrumentation (WMI) は、Windows システム管理のための中核となるテクノロジであり、幅広い種類の情報を一貫した方法で公開します。</span><span class="sxs-lookup"><span data-stu-id="71fe5-105">Windows Management Instrumentation (WMI) is a core technology for Windows system administration because it exposes a wide range of information in a uniform manner.</span></span> <span data-ttu-id="71fe5-106">WMI によって可能になるタスクが非常に多いことから、WMI オブジェクトにアクセスするための PowerShell コマンドレットである `Get-CimInstance` は、実際の作業を行うための最も便利なコマンドレットの 1 つと言えます。</span><span class="sxs-lookup"><span data-stu-id="71fe5-106">Because of how much WMI makes possible, the PowerShell cmdlet for accessing WMI objects, `Get-CimInstance`, is one of the most useful for doing real work.</span></span> <span data-ttu-id="71fe5-107">ここでは、CimCmdlets を使って WMI オブジェクトにアクセスする方法と、WMI オブジェクトを使って特定の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="71fe5-107">We are going to discuss how to use the CimCmdlets to access WMI objects and then how to use WMI objects to do specific things.</span></span>

### <a name="listing-wmi-classes"></a><span data-ttu-id="71fe5-108">WMI クラスの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="71fe5-108">Listing WMI Classes</span></span>

<span data-ttu-id="71fe5-109">WMI のほとんどのユーザーが直面する最初の問題は、WMI で何ができるかを調べることです。</span><span class="sxs-lookup"><span data-stu-id="71fe5-109">The first problem most WMI users encounter is trying to find out what can be done with WMI.</span></span> <span data-ttu-id="71fe5-110">WMI クラスは、管理できるリソースを記述しています。</span><span class="sxs-lookup"><span data-stu-id="71fe5-110">WMI classes describe the resources that can be managed.</span></span> <span data-ttu-id="71fe5-111">何百もの WMI クラスがあり、その中には数十個のプロパティを持つクラスもあります。</span><span class="sxs-lookup"><span data-stu-id="71fe5-111">There are hundreds of WMI classes, some of which contain dozens of properties.</span></span>

<span data-ttu-id="71fe5-112">この問題に対処するため、`Get-CimClass` では WMI を探索可能にしました。</span><span class="sxs-lookup"><span data-stu-id="71fe5-112">`Get-CimClass` addresses this problem by making WMI discoverable.</span></span> <span data-ttu-id="71fe5-113">ローカル コンピューター上で使える WMI クラスの一覧を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="71fe5-113">You can get a list of the WMI classes available on the local computer by typing:</span></span>

```powershell
Get-CimClass -Namespace root/CIMV2 |
  Where-Object CimClassName -like Win32* |
    Select-Object CimClassName
```

```Output
CimClassName
------------
Win32_DeviceChangeEvent
Win32_SystemConfigurationChangeEvent
Win32_VolumeChangeEvent
Win32_SystemTrace
Win32_ProcessTrace
Win32_ProcessStartTrace
Win32_ProcessStopTrace
Win32_ThreadTrace
Win32_ThreadStartTrace
Win32_ThreadStopTrace
...
```

<span data-ttu-id="71fe5-114">同じ情報をリモート コンピューターから取得するには、次のように、**ComputerName** パラメーターにコンピューター名や IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="71fe5-114">You can retrieve the same information from a remote computer by using the **ComputerName** parameter, specifying a computer name or IP address:</span></span>

```powershell
Get-CimClass -Namespace root/CIMV2 -ComputerName 192.168.1.29
```

<span data-ttu-id="71fe5-115">リモート コンピューターから返されるクラスの一覧は、そのコンピューターで実行されている特定のオペレーティング システムや、インストールされているアプリケーションによって追加された特定の WMI 拡張機能に応じて異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="71fe5-115">The class listing returned by remote computers may vary due to the specific operating system the computer is running and the particular WMI extensions added by installed applications.</span></span>

> [!NOTE]
> <span data-ttu-id="71fe5-116">CIM コマンドレットを使用してリモート コンピューターに接続するときは、リモート コンピューターで WMI が実行されていて、使用するアカウントがリモート コンピューターのローカル管理者グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="71fe5-116">When using CIM cmdlets to connect to a remote computer, the remote computer must be running WMI and the account you are using must be in the local administrators group on the remote computer.</span></span>
> <span data-ttu-id="71fe5-117">リモート システムに PowerShell をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="71fe5-117">The remote system does not need to have PowerShell installed.</span></span> <span data-ttu-id="71fe5-118">そのため、WMI が利用可能であれば、PowerShell を実行していないオペレーティング システムであっても管理できます。</span><span class="sxs-lookup"><span data-stu-id="71fe5-118">This allows you to administer operating systems that are not running PowerShell, but do have WMI available.</span></span>

### <a name="displaying-wmi-class-details"></a><span data-ttu-id="71fe5-119">WMI クラスの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="71fe5-119">Displaying WMI Class Details</span></span>

<span data-ttu-id="71fe5-120">WMI クラスの名前がわかっている場合は、その名前を使って情報をすぐに取得できます。</span><span class="sxs-lookup"><span data-stu-id="71fe5-120">If you already know the name of a WMI class, you can use it to get information immediately.</span></span> <span data-ttu-id="71fe5-121">たとえば、コンピューターに関する情報を取得するためによく使われる WMI クラスの 1 つに、**Win32_OperatingSystem** があります。</span><span class="sxs-lookup"><span data-stu-id="71fe5-121">For example, one of the WMI classes commonly used for retrieving information about a computer is **Win32_OperatingSystem**.</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem
```

```Output
SystemDirectory     Organization BuildNumber RegisteredUser SerialNumber            Version
---------------     ------------ ----------- -------------- ------------            -------
C:\WINDOWS\system32 Microsoft    18362       USER1          00330-80000-00000-AA175 10.0.18362
```

<span data-ttu-id="71fe5-122">ここでは、すべてのパラメーターを示しましたが、このコマンドはもっと簡潔に表現できます。</span><span class="sxs-lookup"><span data-stu-id="71fe5-122">Although we are showing all of the parameters, the command can be expressed in a more succinct way.</span></span>
<span data-ttu-id="71fe5-123">**ComputerName** パラメーターは、ローカル システムに接続するときには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="71fe5-123">The **ComputerName** parameter is not necessary when connecting to the local system.</span></span> <span data-ttu-id="71fe5-124">最も一般的なケースを示し、このパラメーターを思い出してもらうために使いました。</span><span class="sxs-lookup"><span data-stu-id="71fe5-124">We show it to demonstrate the most general case and remind you about the parameter.</span></span> <span data-ttu-id="71fe5-125">**Namespace** の既定値は `root/CIMV2` であるため、これも省略できます。</span><span class="sxs-lookup"><span data-stu-id="71fe5-125">The **Namespace** defaults to `root/CIMV2`, and can be omitted as well.</span></span> <span data-ttu-id="71fe5-126">最後に、ほとんどのコマンドレットでは、共通のパラメーターの名前を省略できます。</span><span class="sxs-lookup"><span data-stu-id="71fe5-126">Finally, most cmdlets allow you to omit the name of common parameters.</span></span> <span data-ttu-id="71fe5-127">`Get-CimInstance` の場合、最初のパラメーターで名前を指定しないと、PowerShell ではそれが **Class** パラメーターとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="71fe5-127">With `Get-CimInstance`, if no name is specified for the first parameter, PowerShell treats it as the **Class** parameter.</span></span> <span data-ttu-id="71fe5-128">したがって、先ほどのコマンドは、次のように入力することもできました。</span><span class="sxs-lookup"><span data-stu-id="71fe5-128">This means the last command could have been issued by typing:</span></span>

```powershell
Get-CimInstance Win32_OperatingSystem
```

<span data-ttu-id="71fe5-129">**Win32_OperatingSystem** クラスには、ここで紹介した以外にも多数のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="71fe5-129">The **Win32_OperatingSystem** class has many more properties than those displayed here.</span></span> <span data-ttu-id="71fe5-130">Get-Member を使うと、すべてのプロパティを参照できます。</span><span class="sxs-lookup"><span data-stu-id="71fe5-130">You can use Get-Member to see all the properties.</span></span> <span data-ttu-id="71fe5-131">WMI クラスのプロパティは、他のオブジェクト プロパティと同じように自動的に取得できます。</span><span class="sxs-lookup"><span data-stu-id="71fe5-131">The properties of a WMI class are automatically available like other object properties:</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem | Get-Member -MemberType Property
```

```Output
   TypeName: Microsoft.Management.Infrastructure.CimInstance#root/cimv2/Win32_OperatingSystem
Name                                      MemberType Definition
----                                      ---------- ----------
BootDevice                                Property   string BootDevice {get;}
BuildNumber                               Property   string BuildNumber {get;}
BuildType                                 Property   string BuildType {get;}
Caption                                   Property   string Caption {get;}
CodeSet                                   Property   string CodeSet {get;}
CountryCode                               Property   string CountryCode {get;}
CreationClassName                         Property   string CreationClassName {get;}
CSCreationClassName                       Property   string CSCreationClassName {get;}
CSDVersion                                Property   string CSDVersion {get;}
CSName                                    Property   string CSName {get;}
CurrentTimeZone                           Property   short CurrentTimeZone {get;}
DataExecutionPrevention_32BitApplications Property   bool DataExecutionPrevention_32BitApplications {get;}
DataExecutionPrevention_Available         Property   bool DataExecutionPrevention_Available {get;}
...
```

#### <a name="displaying-non-default-properties-with-format-cmdlets"></a><span data-ttu-id="71fe5-132">既定以外のプロパティを Format コマンドレットで表示する</span><span class="sxs-lookup"><span data-stu-id="71fe5-132">Displaying Non-Default Properties with Format Cmdlets</span></span>

<span data-ttu-id="71fe5-133">**Win32_OperatingSystem** クラスに含まれている情報のうち、既定では表示されない情報を表示するには、**Format** コマンドレットを使います。</span><span class="sxs-lookup"><span data-stu-id="71fe5-133">If you want information contained in the **Win32_OperatingSystem** class that is not displayed by default, you can display it by using the **Format** cmdlets.</span></span> <span data-ttu-id="71fe5-134">たとえば、利用可能なメモリのデータを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="71fe5-134">For example, if you want to display available memory data, type:</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem |
  Format-Table -Property TotalVirtualMemorySize, TotalVisibleMemorySize,
    FreePhysicalMemory, FreeVirtualMemory, FreeSpaceInPagingFiles
```

```Output
TotalVirtualMemorySize TotalVisibleMemorySize FreePhysicalMemory FreeVirtualMemory FreeSpaceInPagingFiles
---------------------- ---------------------- ------------------ ----------------- ----------------------
              33449088               16671872            6451868          18424496               16285032
```

> [!NOTE]
> <span data-ttu-id="71fe5-135">`Format-Table` のプロパティ名にはワイルドカードを指定できるので、最後のパイプライン要素は `Format-Table -Property Total*Memory*, Free*` のように省略できます</span><span class="sxs-lookup"><span data-stu-id="71fe5-135">Wildcards work with property names in `Format-Table`, so the final pipeline element can be reduced to `Format-Table -Property Total*Memory*, Free*`</span></span>

<span data-ttu-id="71fe5-136">メモリのデータは、次のように入力して一覧の形式にすると、さらに読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="71fe5-136">The memory data might be more readable if you format it as a list by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_OperatingSystem | Format-List Total*Memory*, Free*
```

```Output
TotalVirtualMemorySize : 33449088
TotalVisibleMemorySize : 16671872
FreePhysicalMemory     : 6524456
FreeSpaceInPagingFiles : 16285808
FreeVirtualMemory      : 18393668
Name                   : Microsoft Windows 10 Pro|C:\WINDOWS|\Device\Harddisk0\Partition2
```