---
title: Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dc2093a-dc54-42c4-ada3-c8d089ba1e8e
caps.latest.revision: 6
ms.openlocfilehash: a6738a7c4c934b2d6a16695a711f7c6c80afdd2d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075708"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="6ad59-102">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-102">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="6ad59-103">Define uma condição que deve existir para uma definição de controle a ser usado.</span><span class="sxs-lookup"><span data-stu-id="6ad59-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="6ad59-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="6ad59-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="6ad59-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomEntry GroupBy (formato) CustomControl para elemento de GroupBy (formato) EntrySelectedBy CustomEntry para elemento de GroupBy (formato) SelectionCondition EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6ad59-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6ad59-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6ad59-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="6ad59-107">Attributes and Elements</span></span>

<span data-ttu-id="6ad59-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="6ad59-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6ad59-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="6ad59-109">Attributes</span></span>

<span data-ttu-id="6ad59-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6ad59-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6ad59-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6ad59-111">Child Elements</span></span>

|<span data-ttu-id="6ad59-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ad59-112">Element</span></span>|<span data-ttu-id="6ad59-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ad59-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ad59-114">Elemento PropertyName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-114">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="6ad59-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6ad59-115">Optional element.</span></span><br /><br /> <span data-ttu-id="6ad59-116">Especifica uma propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6ad59-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="6ad59-117">Elemento ScriptBlock para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-117">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="6ad59-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6ad59-118">Optional element.</span></span><br /><br /> <span data-ttu-id="6ad59-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6ad59-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="6ad59-120">Elemento SelectionSetName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-120">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="6ad59-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6ad59-121">Optional element.</span></span><br /><br /> <span data-ttu-id="6ad59-122">Especifica o conjunto de tipos do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6ad59-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="6ad59-123">Elemento TypeName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-123">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="6ad59-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6ad59-124">Optional element.</span></span><br /><br /> <span data-ttu-id="6ad59-125">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6ad59-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6ad59-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6ad59-126">Parent Elements</span></span>

|<span data-ttu-id="6ad59-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ad59-127">Element</span></span>|<span data-ttu-id="6ad59-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ad59-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ad59-129">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="6ad59-130">Define os tipos de .NET que usam essa definição de controle ou a condição que deve existir para essa definição a ser usado.</span><span class="sxs-lookup"><span data-stu-id="6ad59-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6ad59-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="6ad59-131">Remarks</span></span>

<span data-ttu-id="6ad59-132">Quando você estiver definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="6ad59-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="6ad59-133">A condição de seleção deve especificar um nome menos de uma propriedade ou um bloco de script, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="6ad59-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="6ad59-134">Os critérios de seleção podem especificar qualquer número de tipos do .NET ou seleção define, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="6ad59-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="6ad59-135">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="6ad59-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ad59-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ad59-136">See Also</span></span>

[<span data-ttu-id="6ad59-137">Elemento PropertyName para SelectionCondition para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6ad59-138">Elemento ScriptBlock para SelectionCondition para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6ad59-139">Elemento SelectionSetName para SelectionCondition para um controle personalizado para o modo de exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6ad59-140">Elemento TypeName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-140">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="6ad59-141">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6ad59-141">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="6ad59-142">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ad59-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
