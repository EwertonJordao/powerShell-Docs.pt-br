---
title: Runspace01 (C#) exemplo de código | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: 2f1839d1ba578cdfe97f60c741c84b0a57f1d8f6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854212"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="1e055-102">Exemplo de código Runspace01 (C#)</span><span class="sxs-lookup"><span data-stu-id="1e055-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="1e055-103">Aqui estão exemplos de código para o espaço de execução descrito [criação de um Console do aplicativo que é executado um comando especificado](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).</span><span class="sxs-lookup"><span data-stu-id="1e055-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).</span></span> <span data-ttu-id="1e055-104">Para fazer isso, o aplicativo invoca um runspace e, em seguida, invoca um comando.</span><span class="sxs-lookup"><span data-stu-id="1e055-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="1e055-105">(Observe que este aplicativo não especificar informações de configuração do espaço de execução, nem explicitamente cria um pipeline).</span><span class="sxs-lookup"><span data-stu-id="1e055-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="1e055-106">O comando é invocado é o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e055-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>
<span data-ttu-id="1e055-107">Aqui estão exemplos de código para o espaço de execução descrito [criação de um Console do aplicativo que é executado um comando especificado](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).</span><span class="sxs-lookup"><span data-stu-id="1e055-107">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](http://msdn.microsoft.com/en-us/793a6570-a072-4799-840b-172f28ce620e).</span></span> <span data-ttu-id="1e055-108">Para fazer isso, o aplicativo invoca um runspace e, em seguida, invoca um comando.</span><span class="sxs-lookup"><span data-stu-id="1e055-108">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="1e055-109">(Observe que este aplicativo não especificar informações de configuração do espaço de execução, nem explicitamente cria um pipeline).</span><span class="sxs-lookup"><span data-stu-id="1e055-109">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="1e055-110">O comando é invocado é o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e055-110">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="1e055-111">Você pode baixar o C# arquivo de origem (runspace01.cs) para esse espaço de execução usando o Microsoft Windows Software Development Kit para Windows Vista e o Microsoft .NET Framework 3.0 Runtime Components.</span><span class="sxs-lookup"><span data-stu-id="1e055-111">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="1e055-112">Para obter instruções de download, consulte [como instalar o Windows PowerShell e o Download do SDK do Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="1e055-112">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="1e055-113">Você pode baixar o C# arquivo de origem (runspace01.cs) para esse espaço de execução usando o Microsoft Windows Software Development Kit para Windows Vista e o Microsoft .NET Framework 3.0 Runtime Components.</span><span class="sxs-lookup"><span data-stu-id="1e055-113">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="1e055-114">Para obter instruções de download, consulte [como instalar o Windows PowerShell e o Download do SDK do Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="1e055-114">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="1e055-115">Os arquivos de origem baixado estão disponíveis na  **\<amostras do PowerShell >** directory.</span><span class="sxs-lookup"><span data-stu-id="1e055-115">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="1e055-116">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="1e055-116">Code Sample</span></span>

[!code-csharp[Runspace01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a><span data-ttu-id="1e055-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1e055-117">See Also</span></span>

[<span data-ttu-id="1e055-118">Guia do programador do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e055-118">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="1e055-119">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e055-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)