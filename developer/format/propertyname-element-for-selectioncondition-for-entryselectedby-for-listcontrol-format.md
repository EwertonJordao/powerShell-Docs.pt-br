---
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71c3f1f6-6fe2-42f1-8260-6974d3871748
caps.latest.revision: 11
ms.openlocfilehash: 7d526372cf80327b3fb9b79b6e83429c57780183
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064876"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a>Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListControl (formato)

Especifica a propriedade do .NET que dispara a condição. Quando essa propriedade estiver presente ou quando ela é avaliada como `true`, a condição for atendida e a entrada da lista é usada.

Elemento (formato) elemento ViewDefinitions (formato) exibição elemento (formato) elemento ListControl (formato) ListEntries elemento (formato) ListEntry elemento (formato) EntrySelectedBy elemento de configuração para elemento de SelectionCondition ListEntry (formato) EntrySelectedBy para elemento de PropertyName ListEntry (formato) SelectionCondition para EntrySelectedBy para ListEntry (formato)

## <a name="syntax"></a>Sintaxe

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a>Elementos e atributos

As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.

### <a name="attributes"></a>Atributos

Nenhum.

### <a name="child-elements"></a>Elementos filho

Nenhum.

### <a name="parent-elements"></a>Elementos pai

|Elemento|Descrição|
|-------------|-----------------|
|[Elemento SelectionCondition para EntrySelectedBy para ListEntry (formato)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|Define a condição que deve existir para essa entrada de lista a ser usado.|

## <a name="text-value"></a>Valor de texto

Especifique o nome de propriedade do .NET.

## <a name="remarks"></a>Comentários

A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não é possível especificar ambos. Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou o Item está sendo usado](./defining-conditions-for-displaying-data.md).

Para obter mais informações sobre outros componentes de uma exibição de lista, consulte [criação de exibição de lista](./creating-a-list-view.md).

## <a name="see-also"></a>Consulte Também

[Criando uma exibição de lista](./creating-a-list-view.md)

[Definir condições para quando os dados é exibida.](./defining-conditions-for-displaying-data.md)

[Elemento ListEntry (formato)](./listentry-element-for-listcontrol-format.md)

[Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListEntry (formato)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[Gravar um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
