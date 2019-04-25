---
title: Escrevendo um aplicativo de Host do PowerShell do Windows | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81aeafad-dbc3-4712-8bb9-e6a417be260f
caps.latest.revision: 15
ms.openlocfilehash: 2df5a59833fcdd58c6b2afbb4882111592fb3d76
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082491"
---
# <a name="writing-a-windows-powershell-host-application"></a><span data-ttu-id="73cd1-102">Escrever um aplicativo host do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="73cd1-102">Writing a Windows PowerShell Host Application</span></span>

<span data-ttu-id="73cd1-103">Você pode hospedar o Windows PowerShell em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="73cd1-103">You can host Windows PowerShell in your application.</span></span> <span data-ttu-id="73cd1-104">O aplicativo host pode definir o espaço de execução onde os comandos são executados, abra sessões em um computador local ou remoto e invocar os comandos de forma síncrona ou assíncrona com base nas necessidades do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="73cd1-104">The host application can define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

<span data-ttu-id="73cd1-105">Os tópicos a seguir explicam como criar um aplicativo que hospeda o</span><span class="sxs-lookup"><span data-stu-id="73cd1-105">The following topics explain how to create an application that hosts</span></span>

## <a name="in-this-section"></a><span data-ttu-id="73cd1-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="73cd1-106">In This Section</span></span>

<span data-ttu-id="73cd1-107">[Início rápido de Host do Windows PowerShell](./windows-powershell-host-quickstart.md) fornece instruções e exemplos de código para ajudá-lo a iniciar a criação de aplicativos host.</span><span class="sxs-lookup"><span data-stu-id="73cd1-107">[Windows PowerShell Host Quickstart](./windows-powershell-host-quickstart.md) Provides instructions and code samples to get you started creating host applications.</span></span>

<span data-ttu-id="73cd1-108">[Criação de espaços de execução](./creating-runspaces.md) um conjunto de tópicos que explicam como criar espaços de execução para executar o comando do Windows PowerShell em um aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="73cd1-108">[Creating Runspaces](./creating-runspaces.md) A set of topics that explain how to create runspaces to run Windows PowerShell command in a host application.</span></span>

<span data-ttu-id="73cd1-109">[Adicionando e invocar comandos](./adding-and-invoking-commands.md) explica como criar e executar um pipeline de comando em seu aplicativo host...</span><span class="sxs-lookup"><span data-stu-id="73cd1-109">[Adding and invoking commands](./adding-and-invoking-commands.md) Explains how to create and run a command pipeline in your host application..</span></span>

<span data-ttu-id="73cd1-110">[Criação de espaços de execução remotos](./creating-remote-runspaces.md) explica como se conectar a um espaço de execução a um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="73cd1-110">[Creating remote runspaces](./creating-remote-runspaces.md) Explains how to connect a runspace to a remote computer.</span></span>

<span data-ttu-id="73cd1-111">[Criando uma interface do usuário personalizada](./creating-a-custom-user-interface.md) introduz personalizadas do usuário, interfaces e fornece links para exemplos.</span><span class="sxs-lookup"><span data-stu-id="73cd1-111">[Creating a custom user interface](./creating-a-custom-user-interface.md) Introduces custom user interfaces and provides links to examples.</span></span>

<span data-ttu-id="73cd1-112">[Exemplos de aplicativo de host](./host-application-samples.md) esta seção inclui exemplos de aplicativos completa do host.</span><span class="sxs-lookup"><span data-stu-id="73cd1-112">[Host Application Samples](./host-application-samples.md) This section includes samples of complete host applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="73cd1-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="73cd1-113">See Also</span></span>

[<span data-ttu-id="73cd1-114">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="73cd1-114">Windows PowerShell</span></span>](http://msdn.microsoft.com/en-us/b41a2af3-aec1-402d-8e18-c2c26be461ff)