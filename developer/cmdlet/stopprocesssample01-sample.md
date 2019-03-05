---
title: Exemplo de StopProcessSample01 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bed607-369b-4507-87fa-f6011c2f1970
caps.latest.revision: 9
ms.openlocfilehash: f601bcd5cc57ce9828338676bf71cbe235593b5d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857132"
---
# <a name="stopprocesssample01-sample"></a><span data-ttu-id="727dd-102">Amostra StopProcessSample01</span><span class="sxs-lookup"><span data-stu-id="727dd-102">StopProcessSample01 Sample</span></span>

<span data-ttu-id="727dd-103">Este exemplo mostra como gravar um cmdlet que solicita comentários do usuário antes de tentar interromper um processo e como implementar um `PassThru` indicando que o usuário deseja o cmdlet para retornar um objeto de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="727dd-103">This sample shows how to write a cmdlet that requests feedback from the user before it attempts to stop a process, and how to implement a `PassThru` parameter indicating that the user wants the cmdlet to return an object.</span></span> <span data-ttu-id="727dd-104">Esse cmdlet é semelhante ao `Stop-Process` cmdlet fornecido pelo Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="727dd-104">This cmdlet is similar to the `Stop-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

### <a name="how-to-build-the-sample-by-using-visual-studio"></a><span data-ttu-id="727dd-105">Como criar o exemplo usando o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="727dd-105">How to build the sample by using Visual Studio.</span></span>

1. <span data-ttu-id="727dd-106">Com o Windows PowerShell 2.0 do SDK instalado, navegue até a pasta StopProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="727dd-106">With the Windows PowerShell 2.0 SDK installed, navigate to the StopProcessSample01 folder.</span></span> <span data-ttu-id="727dd-107">O local padrão é C:\Program Files (x86) \Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample01.</span><span class="sxs-lookup"><span data-stu-id="727dd-107">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\StopProcessSample01.</span></span>

2. <span data-ttu-id="727dd-108">Clique duas vezes no ícone para o arquivo de solução (. sln).</span><span class="sxs-lookup"><span data-stu-id="727dd-108">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="727dd-109">Isso abre o projeto de exemplo no Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="727dd-109">This opens the sample project in Microsoft Visual Studio.</span></span>

3. <span data-ttu-id="727dd-110">No **construir** menu, selecione **compilar solução**.</span><span class="sxs-lookup"><span data-stu-id="727dd-110">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="727dd-111">A biblioteca para o exemplo será compilada nas pastas padrão \bin ou \bin\debug.</span><span class="sxs-lookup"><span data-stu-id="727dd-111">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="727dd-112">Como executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="727dd-112">How to run the sample</span></span>

1. <span data-ttu-id="727dd-113">Crie a seguinte pasta de módulo:</span><span class="sxs-lookup"><span data-stu-id="727dd-113">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/StopProcessSample01`

2. <span data-ttu-id="727dd-114">Copie o assembly de exemplo para a pasta de módulo.</span><span class="sxs-lookup"><span data-stu-id="727dd-114">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="727dd-115">Inicie o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="727dd-115">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="727dd-116">Execute o seguinte comando para carregar o assembly no Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="727dd-116">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `import-module stopprossessample01`

5. <span data-ttu-id="727dd-117">Execute o seguinte comando para executar o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="727dd-117">Run the following command to run the cmdlet:</span></span>

    `stop-proc`

## <a name="requirements"></a><span data-ttu-id="727dd-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="727dd-118">Requirements</span></span>

<span data-ttu-id="727dd-119">Este exemplo requer o Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="727dd-119">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="727dd-120">Demonstra</span><span class="sxs-lookup"><span data-stu-id="727dd-120">Demonstrates</span></span>

<span data-ttu-id="727dd-121">Este exemplo demonstra o seguinte.</span><span class="sxs-lookup"><span data-stu-id="727dd-121">This sample demonstrates the following.</span></span>

- <span data-ttu-id="727dd-122">Declarando uma classe cmdlet usando o atributo de Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="727dd-122">Declaring a cmdlet class by using the Cmdlet attribute.</span></span>

- <span data-ttu-id="727dd-123">Declarando parâmetros de um cmdlet, usando o atributo de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="727dd-123">Declaring a cmdlet parameters by using the Parameter attribute.</span></span>

- <span data-ttu-id="727dd-124">Chamando o método ShouldProcess para solicitar uma confirmação.</span><span class="sxs-lookup"><span data-stu-id="727dd-124">Calling the ShouldProcess method to request confirmation.</span></span>

- <span data-ttu-id="727dd-125">Implementando um `PassThru` parâmetro que indica se o usuário deseja o cmdlet para retornar um objeto.</span><span class="sxs-lookup"><span data-stu-id="727dd-125">Implementing a `PassThru` parameter that indicates if the user wants the cmdlet to return an object.</span></span> <span data-ttu-id="727dd-126">Por padrão, esse cmdlet não retorna um objeto para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="727dd-126">By default, this cmdlet does not return an object to the pipeline.</span></span>

## <a name="example"></a><span data-ttu-id="727dd-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="727dd-127">Example</span></span>

<span data-ttu-id="727dd-128">Este exemplo mostra como implementar uma `PassThru` parâmetro que indica que o usuário deseja o cmdlet para retornar um objeto, e como solicitar comentários do usuário por chamadas para o `ShouldProcess` e `ShouldContinue` métodos.</span><span class="sxs-lookup"><span data-stu-id="727dd-128">This sample shows how to implement a `PassThru` parameter that indicates that the user wants the cmdlet to return an object, and how to request user feedback by calls to the `ShouldProcess` and `ShouldContinue` methods.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Collections;
using Win32Exception = System.ComponentModel.Win32Exception;
using System.Management.Automation;    // Windows PowerShell namespace
using System.Globalization;

namespace Microsoft.Samples.PowerShell.Commands
{
   #region StopProcCommand

    /// <summary>
   /// This class implements the stop-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsLifecycle.Stop, "Proc",
       SupportsShouldProcess = true)]
   public class StopProcCommand : Cmdlet
   {
       #region Parameters

      /// <summary>
      /// This parameter provides the list of process names on
      /// which the Stop-Proc cmdlet will work.
      /// </summary>
       [Parameter(
          Position = 0,
          Mandatory = true,
          ValueFromPipeline = true,
          ValueFromPipelineByPropertyName = true
       )]
       public string[] Name
       {
           get { return processNames; }
           set { processNames = value; }
       }
       private string[] processNames;

       /// <summary>
       /// This parameter overrides the ShouldContinue call to force
       /// the cmdlet to stop its operation. This parameter should always
       /// be used with caution.
       /// </summary>
       [Parameter]
       public SwitchParameter Force
       {
           get { return force; }
           set { force = value; }
       }
       private bool force;

       /// <summary>
       /// This parameter indicates that the cmdlet should return
       /// an object to the pipeline after the processing has been
       /// completed.
       /// </summary>
       [Parameter]
       public SwitchParameter PassThru
       {
           get { return passThru; }
           set { passThru = value; }
       }
       private bool passThru;

       #endregion Parameters

       #region Cmdlet Overrides

       /// <summary>
       /// The ProcessRecord method does the following for each of the
       /// requested process names:
       /// 1) Check that the process is not a critical process.
       /// 2) Attempt to stop that process.
       /// If no process is requested then nothing occurs.
       /// </summary>
       protected override void ProcessRecord()
       {
           foreach (string name in processNames)
           {
               // For every process name passed to the cmdlet, get the associated
               // processes.
               // Write a nonterminating error for failure to retrieve
               // a process.
               Process[] processes;

               try
               {
                   processes = Process.GetProcessesByName(name);
               }
               catch (InvalidOperationException ioe)
               {
                   WriteError(new ErrorRecord(ioe,"UnableToAccessProcessByName",
                       ErrorCategory.InvalidOperation, name));

                   continue;
               }

               // Try to stop the processes that have been retrieved.
               foreach (Process process in processes)
               {
                   string processName;

                   try
                   {
                       processName = process.ProcessName;
                   }
                   catch (Win32Exception e)
                   {
                      WriteError(new ErrorRecord(e, "ProcessNameNotFound",
                                           ErrorCategory.ReadError, process));
                      continue;
                   }

                   // Confirm the operation with the user first.
                   // This is always false if the WhatIf parameter is set.
                   if (!ShouldProcess(string.Format(CultureInfo.CurrentCulture,"{0} ({1})", processName,
                               process.Id)))
                   {
                       continue;
                   }

                   // Make sure that the user really wants to stop a critical
                   // process that culd possibly stop the computer.
                   bool criticalProcess =
                       criticalProcessNames.Contains(processName.ToLower(CultureInfo.CurrentCulture));

                   if (criticalProcess &&!force)
                   {
                       string message = String.Format
                           (CultureInfo.CurrentCulture,
                                "The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                                    processName);

                       // It is possible that the ProcessRecord method is called
                       // multiple times when objects are recieved as inputs from
                       // the pipeline. So to retain YesToAll and NoToAll input that
                       // the user may enter across mutilple calls to this function,
                       // they are stored as private members of the cmdlet.
                       if (!ShouldContinue(message, "Warning!",
                                               ref yesToAll, ref noToAll))
                       {
                           continue;
                       }
                   } // if (cricicalProcess...

                   // Stop the named process.
                   try
                   {
                       process.Kill();
                   }
                   catch (Exception e)
                   {
                       if ((e is Win32Exception) || (e is SystemException) ||
                          (e is InvalidOperationException))
                       {
                           // This process could not be stopped so write
                           // a nonterminating error.
                           WriteError(new ErrorRecord(e, "CouldNotStopProcess",
                                           ErrorCategory.CloseError, process));
                           continue;
                       } // if ((e is...
                       else throw;
                   } // catch

                   // If the PassThru parameter is
                   // specified, return the terminated process.
                   if (passThru)
                   {
                       WriteObject(process);
                   }
               } // foreach (Process...
           } // foreach (string...
       } // ProcessRecord

       #endregion Cmdlet Overrides

       #region Private Data

       private bool yesToAll, noToAll;

       /// <summary>
       /// Partial list of critical processes that should not be
       /// stopped.  Lower case is used for case insensitive matching.
       /// </summary>
       private ArrayList criticalProcessNames = new ArrayList(
          new string[] { "system", "winlogon", "spoolsv" }
       );

       #endregion Private Data

   } // StopProcCommand

   #endregion StopProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="727dd-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="727dd-129">See Also</span></span>

<span data-ttu-id="727dd-130">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="727dd-130">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>