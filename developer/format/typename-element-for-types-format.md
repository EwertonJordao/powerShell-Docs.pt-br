---
title: Elemento TypeName para tipos (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0595b99e-b438-4240-b47b-555cf0316f33
caps.latest.revision: 15
ms.openlocfilehash: bd5baa03c2050b2c3bbe1d7697c253d923175d39
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083783"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="c60c9-102">Elemento TypeName para Types (formato)</span><span class="sxs-lookup"><span data-stu-id="c60c9-102">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="c60c9-103">Especifica o tipo de .NET de um objeto que pertence ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="c60c9-103">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="c60c9-104">Tipos de configuração (formato) elemento SelectionSets (formato) SelectionSet elemento (formato) (formato) TypeName do elemento de tipos (formato)</span><span class="sxs-lookup"><span data-stu-id="c60c9-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c60c9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c60c9-105">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c60c9-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="c60c9-106">Attributes and Elements</span></span>

<span data-ttu-id="c60c9-107">As seções a seguir descrevem os atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="c60c9-107">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="c60c9-108">Pelo menos um `TypeName` elemento deve ser incluído no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="c60c9-108">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="c60c9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="c60c9-109">Attributes</span></span>

<span data-ttu-id="c60c9-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c60c9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c60c9-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="c60c9-111">Child Elements</span></span>

<span data-ttu-id="c60c9-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c60c9-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c60c9-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="c60c9-113">Parent Elements</span></span>

|<span data-ttu-id="c60c9-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="c60c9-114">Element</span></span>|<span data-ttu-id="c60c9-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="c60c9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c60c9-116">Tipos de elemento (formato)</span><span class="sxs-lookup"><span data-stu-id="c60c9-116">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="c60c9-117">Define os objetos .NET na seleção definidos.</span><span class="sxs-lookup"><span data-stu-id="c60c9-117">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c60c9-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="c60c9-118">Text Value</span></span>

<span data-ttu-id="c60c9-119">Especifique o nome totalmente qualificado para o tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="c60c9-119">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="c60c9-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="c60c9-120">Remarks</span></span>

<span data-ttu-id="c60c9-121">Você pode usar conjuntos de seleção quando você tem um conjunto de objetos relacionados que você deseja referenciar, usando um nome único, como um conjunto de objetos que estão relacionadas por meio da herança.</span><span class="sxs-lookup"><span data-stu-id="c60c9-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="c60c9-122">Ao definir seus modos de exibição, você pode especificar o conjunto de objetos usando o nome da seleção definida em vez de listar todos os objetos dentro de cada modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="c60c9-122">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="c60c9-123">Conjuntos de seleção comuns são especificados por seu nome ao definir os modos de exibição do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="c60c9-123">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="c60c9-124">Nesses casos, o `SelectionSetName` elemento filho do `ViewSelectedBy` elemento para o modo de exibição Especifica o conjunto.</span><span class="sxs-lookup"><span data-stu-id="c60c9-124">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="c60c9-125">No entanto, diferentes entradas de uma exibição também podem especificar um conjunto de seleção se aplica a apenas a entrada do modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="c60c9-125">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="c60c9-126">Para obter mais informações sobre conjuntos de seleção, consulte [definindo define de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="c60c9-126">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="c60c9-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c60c9-127">Example</span></span>

<span data-ttu-id="c60c9-128">A exemplo a seguir mostra um `SelectionSet` elemento que define quatro tipos de .NET.</span><span class="sxs-lookup"><span data-stu-id="c60c9-128">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

```
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a><span data-ttu-id="c60c9-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c60c9-129">See Also</span></span>

[<span data-ttu-id="c60c9-130">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="c60c9-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="c60c9-131">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="c60c9-131">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="c60c9-132">Elemento SelectionSets (formato)</span><span class="sxs-lookup"><span data-stu-id="c60c9-132">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="c60c9-133">Tipos de elemento (formato)</span><span class="sxs-lookup"><span data-stu-id="c60c9-133">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="c60c9-134">Gravar um arquivo de formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c60c9-134">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
