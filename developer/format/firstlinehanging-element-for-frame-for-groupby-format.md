---
title: Elemento FirstLineHanging para quadro de GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cdcf66e-96a5-47b5-9269-b4330bde29f2
caps.latest.revision: 6
ms.openlocfilehash: 08db1f2d89c3fe6c1e9a5a522de3071425042c3f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065801"
---
# <a name="firstlinehanging-element-for-frame-for-groupby-format"></a>Elemento FirstLineHanging para Frame para GroupBy (formato)

Especifica quantos caracteres, a primeira linha de dados é deslocada para a esquerda. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomEntry GroupBy (formato) CustomControl para elemento de GroupBy (formato) CustomItem CustomEntry para elemento de quadro GroupBy (formato) CustomItem para elemento GroupBy (formato) FirstLineHanging de quadro para GroupBy (formato)

## <a name="syntax"></a>Sintaxe

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `FirstLineHanging` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

Nenhum.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento de quadro para CustomItem para GroupBy (formato)](./frame-element-for-customitem-for-groupby-format.md)|Define como os dados são exibidos, como o deslocamento de dados para a esquerda ou direita.|

## <a name="text-value"></a>Valor de texto

Especifique o número de caracteres que você deseja deslocar a primeira linha dos dados.

## <a name="remarks"></a>Comentários

Se esse elemento for especificado, não é possível especificar o [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elemento.

## <a name="see-also"></a>Consulte Também

[Elemento FirstLineIndent para quadro de GroupBy (formato)](./firstlineindent-element-for-frame-for-groupby-format.md)

[Elemento de quadro para CustomItem para GroupBy (formato)](./frame-element-for-customitem-for-groupby-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
