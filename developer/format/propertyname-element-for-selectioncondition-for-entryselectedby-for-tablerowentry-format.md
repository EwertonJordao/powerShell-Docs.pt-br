---
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba3b4d9b-2b8c-4a3a-8887-6c606eb9d490
caps.latest.revision: 10
ms.openlocfilehash: 48011950ed64e78a84292762f2c7779003dc59fd
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064655"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format"></a><span data-ttu-id="6c9ae-102">Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="6c9ae-102">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

<span data-ttu-id="6c9ae-103">Especifica a propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="6c9ae-104">Quando essa propriedade estiver presente ou quando ela é avaliada como `true`, a condição for atendida e a entrada da tabela é usada.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-104">When this property is present or when it evaluates to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="6c9ae-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento TableControl (formato) elemento TableRowEntries (formato) elemento TableRowEntry (formato) EntrySelectedBy elemento de configuração para TableRowEntry (formato) Elemento SelectionCondition para EntrySelectedBy para elemento de PropertyName TableRowEntry (formato) SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="6c9ae-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6c9ae-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6c9ae-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6c9ae-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="6c9ae-107">Attributes and Elements</span></span>

<span data-ttu-id="6c9ae-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6c9ae-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="6c9ae-109">Attributes</span></span>

<span data-ttu-id="6c9ae-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6c9ae-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6c9ae-111">Child Elements</span></span>

<span data-ttu-id="6c9ae-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6c9ae-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6c9ae-113">Parent Elements</span></span>

|<span data-ttu-id="6c9ae-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c9ae-114">Element</span></span>|<span data-ttu-id="6c9ae-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="6c9ae-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6c9ae-116">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="6c9ae-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="6c9ae-117">Define a condição que deve existir para essa entrada de tabela a ser usado.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6c9ae-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="6c9ae-118">Text Value</span></span>

<span data-ttu-id="6c9ae-119">Especifique o nome de propriedade do .NET.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c9ae-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="6c9ae-120">Remarks</span></span>

<span data-ttu-id="6c9ae-121">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="6c9ae-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="6c9ae-122">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para quando uma entrada de exibição ou o Item está sendo usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="6c9ae-122">For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="6c9ae-123">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="6c9ae-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6c9ae-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6c9ae-124">See Also</span></span>

[<span data-ttu-id="6c9ae-125">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="6c9ae-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="6c9ae-126">Definir condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="6c9ae-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="6c9ae-127">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="6c9ae-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="6c9ae-128">Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="6c9ae-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="6c9ae-129">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c9ae-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
