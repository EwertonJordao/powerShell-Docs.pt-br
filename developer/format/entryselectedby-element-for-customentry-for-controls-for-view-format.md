---
title: Elemento EntrySelectedBy para CustomEntry controles para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d80a7d-3797-4c46-ae74-ae5cda79b24f
caps.latest.revision: 8
ms.openlocfilehash: efb20c3f2077547e6eb3cb28240512b444f9c481
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066236"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="9e75f-102">Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="9e75f-102">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="9e75f-103">Define os tipos de .NET que usam essa definição de controle ou a condição que deve existir para essa definição a ser usado.</span><span class="sxs-lookup"><span data-stu-id="9e75f-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="9e75f-104">Esse elemento é usado durante a definição de controles que podem ser usados por um modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="9e75f-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="9e75f-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento controles elemento (formato) controle elemento de configuração para controles para exibição (formato) CustomControl elemento de controle para controles para elemento CustomEntries de exibição (formato) CustomControl para controles para elemento de exibição (formato) CustomEntry CustomEntries para controles para elemento de exibição (formato) EntrySelectedBy CustomEntry controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9e75f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9e75f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9e75f-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9e75f-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="9e75f-107">Attributes and Elements</span></span>

<span data-ttu-id="9e75f-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="9e75f-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="9e75f-109">Você deve especificar pelo menos um critério de seleção para uma definição de, conjunto de seleção ou tipo.</span><span class="sxs-lookup"><span data-stu-id="9e75f-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="9e75f-110">Não há nenhum limite máximo ao número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="9e75f-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="9e75f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9e75f-111">Attributes</span></span>

<span data-ttu-id="9e75f-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9e75f-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9e75f-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9e75f-113">Child Elements</span></span>

|<span data-ttu-id="9e75f-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e75f-114">Element</span></span>|<span data-ttu-id="9e75f-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e75f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e75f-116">Elemento SelectionCondition para EntrySelectedBy controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9e75f-116">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="9e75f-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9e75f-117">Optional element.</span></span><br /><br /> <span data-ttu-id="9e75f-118">Define a condição que deve existir para essa definição a ser usado.</span><span class="sxs-lookup"><span data-stu-id="9e75f-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="9e75f-119">Elemento SelectionSetName para EntrySelectedBy controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9e75f-119">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="9e75f-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9e75f-120">Optional element.</span></span><br /><br /> <span data-ttu-id="9e75f-121">Especifica um conjunto de tipos do .NET que usam essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="9e75f-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="9e75f-122">Elemento TypeName para EntrySelectedBy controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9e75f-122">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="9e75f-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9e75f-123">Optional element.</span></span><br /><br /> <span data-ttu-id="9e75f-124">Especifica um tipo .NET que usa essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="9e75f-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9e75f-125">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9e75f-125">Parent Elements</span></span>

|<span data-ttu-id="9e75f-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e75f-126">Element</span></span>|<span data-ttu-id="9e75f-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e75f-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e75f-128">Elemento CustomEntry para CustomEntries controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9e75f-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="9e75f-129">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="9e75f-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9e75f-130">Comentários</span><span class="sxs-lookup"><span data-stu-id="9e75f-130">Remarks</span></span>

<span data-ttu-id="9e75f-131">Condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usado, como quando um objeto tem uma propriedade específica ou quando um valor de propriedade específica ou script avalia para `true`.</span><span class="sxs-lookup"><span data-stu-id="9e75f-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="9e75f-132">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou o Item está sendo usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9e75f-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e75f-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9e75f-133">See Also</span></span>

[<span data-ttu-id="9e75f-134">Elemento CustomEntry para CustomEntries controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9e75f-134">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="9e75f-135">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e75f-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
