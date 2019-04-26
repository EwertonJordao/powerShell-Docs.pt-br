---
title: Definindo o membro padrão define objetos | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f94326-8ffe-4d40-bd2a-b79fb0b4a4e5
caps.latest.revision: 8
ms.openlocfilehash: 2d634e7638ec0e0117d65ca0b2d08e68f0068a03
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068242"
---
# <a name="defining-default-member-sets-for-objects"></a><span data-ttu-id="d06c3-102">Definir os conjuntos de membro padrão para objetos</span><span class="sxs-lookup"><span data-stu-id="d06c3-102">Defining Default Member Sets for Objects</span></span>

<span data-ttu-id="d06c3-103">O conjunto de membros PSStandardMembers é usado pelo Windows PowerShell para definir os conjuntos de propriedades padrão para um objeto.</span><span class="sxs-lookup"><span data-stu-id="d06c3-103">The PSStandardMembers member set is used by Windows PowerShell to define the default property sets for an object.</span></span> <span data-ttu-id="d06c3-104">Os conjuntos de propriedades padrão podem ser usados por comandos, como os cmdlets de formatação para exibir somente as propriedades que são definidas pelo conjunto de propriedades.</span><span class="sxs-lookup"><span data-stu-id="d06c3-104">The default property sets can be used by commands such as the formatting cmdlets to display only those properties that are defined by the property set.</span></span> <span data-ttu-id="d06c3-105">Os conjuntos de propriedades padrão incluem DefaultDisplayProperty, DefaultDisplayPropertySet e DefaultKeyPropertySet.</span><span class="sxs-lookup"><span data-stu-id="d06c3-105">The default property sets include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="d06c3-106">Windows PowerShell ignora todos os outros conjuntos de membros e outros conjuntos de propriedades adicionados ao conjunto de membros PSStandardMembers.</span><span class="sxs-lookup"><span data-stu-id="d06c3-106">Windows PowerShell ignores all other member sets and any other property sets added to the PSStandardMembers member set.</span></span>

## <a name="member-set-for-systemdiagnosticsprocess"></a><span data-ttu-id="d06c3-107">Conjunto de membros para Diagnostics</span><span class="sxs-lookup"><span data-stu-id="d06c3-107">Member Set for System.Diagnostics.Process</span></span>

<span data-ttu-id="d06c3-108">No exemplo a seguir, o conjunto de membros PSStandardMembers define a propriedade DefaultDisplayPropertySet definida para [Diagnostics](/dotnet/api/System.Diagnostics.Process) objetos.</span><span class="sxs-lookup"><span data-stu-id="d06c3-108">In the following example, the PSStandardMembers member set defines the DefaultDisplayPropertySet property set for [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects.</span></span> <span data-ttu-id="d06c3-109">Essa propriedade definida é usada pelas [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d06c3-109">This property set is used by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span>

```xml
<Type>
  <Name>System.Diagnostics.Process</Name>
  <Members>
    <MemberSet>
     <Name>PSStandardMembers</Name>
     <Members>
       <PropertySet>
         <Name>DefaultDisplayPropertySet</Name>
         <ReferencedProperties>
           <Name>Id</Name>
           <Name>Handles</Name>
           <Name>CPU</Name>
           <Name>Name</Name>
         </ReferencedProperties>
      </PropertySet>
    </Members>
  </MemberSet>
```

<span data-ttu-id="d06c3-110">A saída a seguir mostra as propriedades padrão retornadas pela [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d06c3-110">The following output shows the default properties returned by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span> <span data-ttu-id="d06c3-111">Somente o `Id`, `Handles`, `CPU`, e `Name` propriedades são retornadas para cada objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="d06c3-111">Only the `Id`, `Handles`, `CPU`, and `Name` properties are returned for each process object.</span></span>

```powershell
Get-Process | format-list
```

```output
Id      : 2036
Handles : 27
CPU     :
Name    : AEADISRV

Id      : 272
Handles : 38
CPU     :
Name    : agrsmsvc
...
```

## <a name="see-also"></a><span data-ttu-id="d06c3-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d06c3-112">See Also</span></span>

<span data-ttu-id="d06c3-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="d06c3-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
