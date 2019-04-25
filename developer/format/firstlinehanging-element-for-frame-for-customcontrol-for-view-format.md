---
title: Elemento FirstLineHanging de quadro para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6ac3d86-0529-4b93-9bc7-ee94fcef9618
caps.latest.revision: 8
ms.openlocfilehash: ea43e025f5f653ff000e1d7591b535e73da5c9e5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065964"
---
# <a name="firstlinehanging-element-for-frame-for-customcontrol-for-view-format"></a><span data-ttu-id="302e1-102">Elemento FirstLineHanging para Frame para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="302e1-102">FirstLineHanging Element for Frame for CustomControl for View (Format)</span></span>

<span data-ttu-id="302e1-103">Especifica quantos caracteres, a primeira linha de dados é deslocada para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="302e1-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="302e1-104">Esse elemento é usado ao definir uma exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="302e1-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="302e1-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento CustomControl (formato) CustomEntries elemento de configuração para CustomControl para elemento de exibição (formato) CustomEntry CustomEntries para elemento CustomItem de exibição (formato) CustomEntry para elemento de quadro CustomControlView (formato) CustomItem para CustomControl para exibição (formato) FirstLineHanging elemento de quadro para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="302e1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format) FirstLineHanging Element for Frame for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="302e1-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="302e1-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="302e1-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="302e1-107">Attributes and Elements</span></span>

<span data-ttu-id="302e1-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `FirstLineHanging` elemento.</span><span class="sxs-lookup"><span data-stu-id="302e1-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="302e1-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="302e1-109">Attributes</span></span>

<span data-ttu-id="302e1-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="302e1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="302e1-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="302e1-111">Child Elements</span></span>

<span data-ttu-id="302e1-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="302e1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="302e1-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="302e1-113">Parent Elements</span></span>

|<span data-ttu-id="302e1-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="302e1-114">Element</span></span>|<span data-ttu-id="302e1-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="302e1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="302e1-116">Elemento de quadro para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="302e1-116">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="302e1-117">Define como os dados são exibidos, como o deslocamento de dados para a esquerda ou direita.</span><span class="sxs-lookup"><span data-stu-id="302e1-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="302e1-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="302e1-118">Text Value</span></span>

<span data-ttu-id="302e1-119">Especifique o número de caracteres que você deseja deslocar a primeira linha dos dados.</span><span class="sxs-lookup"><span data-stu-id="302e1-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="302e1-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="302e1-120">Remarks</span></span>

<span data-ttu-id="302e1-121">Se esse elemento for especificado, não é possível especificar o [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="302e1-121">If this element is specified, you cannot specify the [FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="302e1-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="302e1-122">See Also</span></span>

[<span data-ttu-id="302e1-123">Elemento FirstLineIndent de quadro para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="302e1-123">FirstLineIndent Element for Frame for CustomControl for View (Format)</span></span>](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="302e1-124">Elemento de quadro para CustomItem para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="302e1-124">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="302e1-125">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="302e1-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
