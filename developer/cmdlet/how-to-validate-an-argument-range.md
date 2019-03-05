---
title: Como validar um intervalo de argumento | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange attribute, example
ms.assetid: 3cba3ab7-c3b6-4d17-aa17-88377496551b
caps.latest.revision: 9
ms.openlocfilehash: a39e34d1f1c333185f09b4a934819e1368d29a48
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859732"
---
# <a name="how-to-validate-an-argument-range"></a><span data-ttu-id="31c4b-102">Como validar um intervalo de argumentos</span><span class="sxs-lookup"><span data-stu-id="31c4b-102">How to Validate an Argument Range</span></span>

<span data-ttu-id="31c4b-103">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar os valores mínimo e máximo do argumento de parâmetro antes que o cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="31c4b-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the minimum and maximum values of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="31c4b-104">Você pode definir essa regra de validação ao declarar o atributo ValidateRange.</span><span class="sxs-lookup"><span data-stu-id="31c4b-104">You set this validation rule by declaring the ValidateRange attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="31c4b-105">Para obter mais informações sobre a classe que define esse atributo, consulte [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span><span class="sxs-lookup"><span data-stu-id="31c4b-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span></span>

### <a name="to-validate-an-argument-range"></a><span data-ttu-id="31c4b-106">Para validar um intervalo de argumento</span><span class="sxs-lookup"><span data-stu-id="31c4b-106">To validate an argument range</span></span>

- <span data-ttu-id="31c4b-107">Adicione o atributo ValidateRange conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="31c4b-107">Add the ValidateRange attribute as shown in the following code.</span></span> <span data-ttu-id="31c4b-108">Este exemplo especifica um intervalo de 0 a 5 para o `InputData` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="31c4b-108">This example specifies a range of 0 to 5 for the `InputData` parameter.</span></span>

    ```csharp
    [ValidateRange(0, 5)]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }
    private int inputData;
    ```

<span data-ttu-id="31c4b-109">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="31c4b-109">For more information about how to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="31c4b-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31c4b-110">See Also</span></span>

[<span data-ttu-id="31c4b-111">Declaração de atributo ValidateRange</span><span class="sxs-lookup"><span data-stu-id="31c4b-111">ValidateRange Attribute Declaration</span></span>](./validaterange-attribute-declaration.md)

<span data-ttu-id="31c4b-112">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="31c4b-112">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>