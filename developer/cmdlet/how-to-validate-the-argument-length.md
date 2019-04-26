---
title: Como validar o comprimento do argumento | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, example
ms.assetid: d5ddaa6e-4904-46da-beb0-0295a8f38332
caps.latest.revision: 12
ms.openlocfilehash: 8a21675acd087df93f93c25952c78931255d60b3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067699"
---
# <a name="how-to-validate-the-argument-length"></a>Como validar o tamanho do argumento

Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o número de caracteres (o comprimento) do argumento de parâmetro antes que o cmdlet é executado. Você pode definir essa regra de validação ao declarar o atributo ValidateLength.

> [!NOTE]
> Para obter mais informações sobre a classe que define esse atributo, consulte [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).

## <a name="to-validate-the-argument-length"></a>Para validar o comprimento do argumento

- Adicione o atributo de validação, conforme mostrado no código a seguir. Este exemplo especifica que o comprimento do argumento deve ter um comprimento de caracteres de 0 a 10.

    ```csharp
    [ValidateLength(0, 10)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateLength](./validatelength-attribute-declaration.md).

## <a name="see-also"></a>Consulte Também

[Declaração de atributo ValidateLength](./validatelength-attribute-declaration.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
