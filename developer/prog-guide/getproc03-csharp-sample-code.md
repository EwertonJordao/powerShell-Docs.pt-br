---
title: GetProc03 (C#) exemplos de código | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebc0d538-69ac-43d5-837d-b6f47344fc6a
caps.latest.revision: 5
ms.openlocfilehash: 116a116a5ba5b81a77b4432a81f001cc999fe46d
ms.sourcegitcommit: f60fa420bdc81db174e6168d3aeb11371e483162
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2019
ms.locfileid: "67301369"
---
# <a name="getproc03-c-sample-code"></a>Código de exemplo GetProc03 (C#)

O código a seguir mostra a implementação de um `Get-Process` redirecionasse o cmdlet que aceite entrada. Essa implementação define uma `Name` parâmetro que aceita entrada do pipeline, recupera informações de processo do computador local com base em nomes fornecidos e, em seguida, usa o [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_)método como o mecanismo de saída para enviar objetos ao pipeline.

> [!NOTE]
> Você pode baixar o C# arquivo de origem (getprov03.cs) para esse cmdlet Get-Proc usando o Microsoft Windows Software Development Kit para Windows Vista e o .NET Framework 3.0 Runtime Components. Para obter instruções de download, consulte [como instalar o Windows PowerShell e o Download do SDK do Windows PowerShell](/powershell/developer/installing-the-windows-powershell-sdk).
>
> Os arquivos de origem baixado estão disponíveis na  **\<amostras do PowerShell >** directory.

## <a name="code-sample"></a>Exemplo de código

[!code-csharp[GetProcessSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L11-L78 "GetProcessSample03.cs")]

## <a name="see-also"></a>Consulte Também

[Guia do programador do Windows PowerShell](./windows-powershell-programmer-s-guide.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
