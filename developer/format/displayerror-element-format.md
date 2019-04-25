---
title: Elemento DisplayError (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c45800-a87d-456e-b07c-12d4d8c27c67
caps.latest.revision: 8
ms.openlocfilehash: 2c6a3d678ca68dc0d189f6ab981fdea5fef894cb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066253"
---
# <a name="displayerror-element-format"></a>Elemento DisplayError (formato)

Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro exibindo uma parte dos dados.

Configuração (formato) elemento DefaultSettings (formato) DisplayError elemento (formato)

## <a name="syntax"></a>Sintaxe

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `DisplayError` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

Nenhum.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md)|Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.|

## <a name="remarks"></a>Comentários

Por padrão, quando ocorre um erro ao tentar exibir uma parte dos dados, o local dos dados for deixado em branco. Quando esse elemento é definido como true, a cadeia de caracteres #ERR será exibido.

## <a name="see-also"></a>Consulte Também

[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
