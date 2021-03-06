---
title: Criando espaços de Tróia remotos | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 057a666f-731b-423d-9d80-7be6b1836244
caps.latest.revision: 5
ms.openlocfilehash: c97b0dfc12d96f99c53383d3578579f1988efd52
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71143545"
---
# <a name="creating-remote-runspaces"></a>Criar runspaces remotos

Comandos do PowerShell que usam um parâmetro **ComputerName** podem ser executados em qualquer computador que executa o PowerShell. Para executar comandos que não usam um parâmetro **ComputerName** , você pode usar o WS-Management para configurar um runspace que se conecta a um computador especificado e executar comandos nesse computador.

## <a name="using-a-wsmanconnection-to-create-a-remote-runspace"></a>Usando um WSManConnection para criar um runspace remoto

 Para criar um runspace que se conecta a um computador remoto, você cria um objeto [System. Management. Automation. Runspaces. WSManConnectionInfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) . Especifique o ponto de extremidade de destino para a conexão definindo a propriedade [System. Management. Automation. Runspaces. WSManConnectionInfo. conexãouri](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo.ConnectionUri) do objeto. Em seguida, você cria um runspace chamando o método [System. Management. Automation. Runspaces. RunspaceFactory. CreateRunspace](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory.CreateRunspace) , especificando o objeto [System. Management. Automation. Runspaces. WSManConnectionInfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) como `connectionInfo` o meter.

 O exemplo a seguir mostra como criar um runspace que se conecta a um computador remoto. No exemplo, `RemoteComputerUri` é usado como um espaço reservado para o URI real de um computador remoto.

```csharp
namespace Samples
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;            // PowerShell namespace.
  using System.Management.Automation.Runspaces;  // PowerShell namespace.

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class RemoteRunspace02
  {
    /// <summary>
    /// This sample shows how to create a remote runspace that
    /// runs commands on the local computer.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    private static void Main(string[] args)
    {
      // Create a WSManConnectionInfo object using the default constructor
      // to connect to the "localHost". The WSManConnectionInfo object can
      // also be used to specify connections to remote computers.
      Uri RemoteComputerUri = new uri("http://Server01:5985/WSMAN");
      WSManConnectionInfo connectionInfo = new WSManConnectionInfo(RemoteComputerUri);

      // Set the OperationTimeout property and OpenTimeout properties.
      // The OperationTimeout property is used to tell PowerShell
      // how long to wait (in milliseconds) before timing out for an
      // operation. The OpenTimeout property is used to tell Windows
      // PowerShell how long to wait (in milliseconds) before timing out
      // while establishing a remote connection.
      connectionInfo.OperationTimeout = 4 * 60 * 1000; // 4 minutes.
      connectionInfo.OpenTimeout = 1 * 60 * 1000; // 1 minute.

      // Create a remote runspace using the connection information.
      //using (Runspace remoteRunspace = RunspaceFactory.CreateRunspace())
      using (Runspace remoteRunspace = RunspaceFactory.CreateRunspace(connectionInfo))
      {
        // Establish the connection by calling the Open() method to open the runspace.
        // The OpenTimeout value set previously will be applied while establishing
        // the connection. Establishing a remote connection involves sending and
        // receiving some data, so the OperationTimeout will also play a role in this process.
          remoteRunspace.Open();

        // Create a PowerShell object to run commands in the remote runspace.
        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = remoteRunspace;
          powershell.AddCommand("get-process");
          powershell.Invoke();

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the results.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                              "{0,-20} {1}",
                              result.Members["ProcessName"].Value,
                              result.Members["HandleCount"].Value);
          }
        }

        // Close the connection. Call the Close() method to close the remote
        // runspace. The Dispose() method (called by using primitive) will call
        // the Close() method if it is not already called.
        remoteRunspace.Close();
      }
    }
  }
}
```
