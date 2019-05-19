---
title: Declaração de atributo ValidateLength | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.assetid: 82fe3a35-a94b-4bc1-ad9e-dfc5f1e788b3
caps.latest.revision: 13
ms.openlocfilehash: 4d3cdccc0fe3e24b1221e41beef4821b613aab93
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855153"
---
# <a name="validatelength-attribute-declaration"></a>Declaração de atributo ValidateLength

O atributo ValidateLength Especifica o número mínimo e máximo de caracteres para um argumento de parâmetro de cmdlet. Esse atributo também pode ser usado por funções do Windows PowerShell.

## <a name="syntax"></a>Sintaxe

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Parâmetros

`MinLength` ([System.Integer](/dotnet/api/System.Integer)) Required. Especifica o número mínimo de caracteres permitidos.

`MaxLength` ([System.Integer](/dotnet/api/System.Integer)) Required. Especifica o número máximo de caracteres permitidos.

## <a name="remarks"></a>Comentários

- Para obter mais informações sobre como declarar esse atributo, consulte [como regras de validação de entrada declarar](./how-to-validate-parameter-input.md).

- Quando esse atributo não for usado, o argumento do parâmetro correspondente pode ser de qualquer comprimento.

- O tempo de execução do Windows PowerShell gera um erro sob as seguintes condições:

    - Quando o valor da `MaxLength` parâmetro de atributo é menor que o valor da `MinLength` parâmetro do atributo.

    - Quando o `MaxLength` parâmetro de atributo é definido como 0.

    - Quando o argumento não é uma cadeia de caracteres.

- O atributo ValidateLength é definido pela [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) classe.

## <a name="see-also"></a>Consulte Também

[System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
