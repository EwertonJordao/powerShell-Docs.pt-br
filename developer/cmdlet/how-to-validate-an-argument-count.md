---
title: Como validar uma contagem de argumento | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateCount attribute, example
ms.assetid: 4e6b6ac4-1003-4e7e-9d4a-9f1cf74fc4af
caps.latest.revision: 8
ms.openlocfilehash: b6ddb8185f21a65b2e3142ebb640962047e11763
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859132"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="cb183-102">Como validar uma contagem de argumentos</span><span class="sxs-lookup"><span data-stu-id="cb183-102">How to Validate an Argument Count</span></span>

<span data-ttu-id="cb183-103">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o número de argumentos (a contagem) que aceita um parâmetro antes que o cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="cb183-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="cb183-104">Você pode definir essa regra de validação ao declarar o atributo ValidateCount.</span><span class="sxs-lookup"><span data-stu-id="cb183-104">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="cb183-105">Para obter mais informações sobre a classe que define esse atributo, consulte [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span><span class="sxs-lookup"><span data-stu-id="cb183-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="cb183-106">Para validar uma contagem de argumento</span><span class="sxs-lookup"><span data-stu-id="cb183-106">To validate an argument count</span></span>

- <span data-ttu-id="cb183-107">Adicione o atributo de validação, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="cb183-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="cb183-108">Este exemplo especifica que o parâmetro aceitará um argumento ou até três argumentos.</span><span class="sxs-lookup"><span data-stu-id="cb183-108">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

    ```csharp
    [ValidateCount(1, 3)]
    [Parameter(Position = 0, Mandatory = true)]
    public string[] UserNames
    {
      get { return userNames; }
      set { userNames = value; }
    }

    private string[] userNames;
    ```

<span data-ttu-id="cb183-109">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="cb183-109">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cb183-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cb183-110">See Also</span></span>

[<span data-ttu-id="cb183-111">Declaração de atributo ValidateCount</span><span class="sxs-lookup"><span data-stu-id="cb183-111">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

<span data-ttu-id="cb183-112">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="cb183-112">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>