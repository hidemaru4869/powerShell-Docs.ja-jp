---
title: Runspace10 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c265084-e072-46ca-9844-c3c0e275d6b0
caps.latest.revision: 7
ms.openlocfilehash: fdf0036c68b608d254ed928ae9ac58616a856200
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367341"
---
# <a name="runspace10-sample"></a>Runspace10 サンプル

このサンプルでは、初期セッションの既定の状態を作成する方法、コマンドレットを[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)に追加する方法、初期セッション状態を使用する実行空間を作成する方法、およびを使用してコマンドを実行する方法を示します。[System. Automation. Powershell](/dotnet/api/system.management.automation.powershell)オブジェクト。

## <a name="requirements"></a>要件

このサンプルには、Windows PowerShell 2.0 が必要です。

## <a name="demonstrates"></a>サンプル

このサンプルでは、次のことを示します。

- [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを作成しています。

- [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトに、(ホストアプリケーションによって定義された) コマンドレットを追加します。

- オブジェクトを使用する、 [system.string オブジェクトを](/dotnet/api/System.Management.Automation.Runspaces.Runspace)作成します。

- System.object オブジェクトを使用する、[システムの管理](/dotnet/api/system.management.automation.powershell)........... [...](/dotnet/api/System.Management.Automation.Runspaces.Runspace) .................

- コマンド[を、system.servicemodel オブジェクトの](/dotnet/api/system.management.automation.powershell)パイプラインに追加します。

- コマンドによって返された、[システムの管理](/dotnet/api/System.Management.Automation.PSObject)オブジェクトからプロパティを抽出しています。

## <a name="example"></a>例

このサンプルでは、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを使用して、実行空間を開いたときに使用可能な要素を定義する実行空間を作成します。 このサンプルでは、(ホストアプリケーションによって定義される) Get Proc コマンドレットが初期セッション状態に追加され、コマンドレットは、[システムの管理](/dotnet/api/system.management.automation.powershell)オブジェクトを使用して同期的に実行されます。

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.Generic;
  using System.Collections.ObjectModel;
  using System.Diagnostics;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  #region GetProcCommand

  /// <summary>
  /// Class that implements the GetProcCommand.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
  {
    #region Cmdlet Overrides

    /// <summary>
    /// For each of the requested process names, retrieve and write
    /// the associated processes.
    /// </summary>
    protected override void ProcessRecord()
    {
      // Get the current processes.
      Process[] processes = Process.GetProcesses();

      // Write the processes to the pipeline making them available
      // to the next cmdlet. The second argument (true) tells the
      // system to enumerate the array, and send one process object
      // at a time to the pipeline.
      WriteObject(processes, true);
    }

    #endregion Overrides
  } // End GetProcCommand class.

  #endregion GetProcCommand

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace10
  {
    /// <summary>
    /// This sample shows how to create a default initial session state, how to add
    /// add a cmdlet to the InitialSessionState object, and then how to create
    /// a Runspace object.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    /// This sample demonstrates:
    /// 1. Creating an InitialSessionState object.
    /// 2. Adding a cmdlet to the InitialSessionState object.
    /// 3. Creating a runspace that uses the InitialSessionState object.
    /// 4. Creating a PowerShell object that uses the Runspace object.
    /// 5. Running the added command synchronously.
    /// 6. Working with PSObject objects to extract properties
    ///    from the objects returned by the pipeline.
    private static void Main(string[] args)
    {
      // Create a default InitialSessionState object. The default
      // InitialSessionState object contains all the elements provided
      // by Windows PowerShell.
      InitialSessionState iss = InitialSessionState.CreateDefault();

      // Add the get-proc cmdlet to the InitialSessionState object.
      SessionStateCmdletEntry ssce = new SessionStateCmdletEntry("get-proc", typeof(GetProcCommand), null);
      iss.Commands.Add(ssce);

      // Create a Runspace object that uses the InitialSessionState object.
      // Notice that no PSHost object is specified, so the default host is used.
      // See the Hosting samples for information on creating your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();

        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = myRunSpace;

          // Add the get-proc cmdlet to the pipeline of the PowerShell object.
          powershell.AddCommand("get-proc");

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the output of the pipeline.
          foreach (PSObject result in results)
          {
             Console.WriteLine(
                               "{0,-20} {1}",
                               result.Members["ProcessName"].Value,
                               result.Members["HandleCount"].Value);
          }
        }

        // Close the runspace to release resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a>参照

[Windows PowerShell ホストアプリケーションの作成](./writing-a-windows-powershell-host-application.md)