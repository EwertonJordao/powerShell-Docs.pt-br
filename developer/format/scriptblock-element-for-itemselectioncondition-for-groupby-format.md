---
title: Elemento ScriptBlock para ItemSelectionCondition para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58d25835-4636-4c58-9f6c-0332b9318051
caps.latest.revision: 6
ms.openlocfilehash: 4045196e306e766cd805b3e7ae31bfcb3de184ee
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860942"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="fa6a9-102">Elemento ScriptBlock para ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fa6a9-102">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="fa6a9-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="fa6a9-104">Quando esse script é avaliado para `true`, a condição é atendida e o controle é usado.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="fa6a9-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="fa6a9-106">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomEntry GroupBy (formato) CustomControl para elemento de GroupBy (formato) CustomItem CustomEntry para elemento de GroupBy (formato) ExpressionBinding CustomItem para elemento de GroupBy (formato) ItemSelectionCondition ExpressionBinding para elemento de ScriptBlock GroupBy (formato) ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fa6a9-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fa6a9-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fa6a9-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fa6a9-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="fa6a9-108">Attributes and Elements</span></span>

<span data-ttu-id="fa6a9-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fa6a9-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="fa6a9-110">Attributes</span></span>

<span data-ttu-id="fa6a9-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fa6a9-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="fa6a9-112">Child Elements</span></span>

<span data-ttu-id="fa6a9-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fa6a9-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="fa6a9-114">Parent Elements</span></span>

|<span data-ttu-id="fa6a9-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa6a9-115">Element</span></span>|<span data-ttu-id="fa6a9-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="fa6a9-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fa6a9-117">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fa6a9-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="fa6a9-118">Define a condição que deve existir para esse controle a ser usado.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fa6a9-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="fa6a9-119">Text Value</span></span>

<span data-ttu-id="fa6a9-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa6a9-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="fa6a9-121">Remarks</span></span>

<span data-ttu-id="fa6a9-122">Se esse elemento é usado, não é possível especificar o [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) elemento ao definir a condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="fa6a9-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa6a9-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fa6a9-123">See Also</span></span>

[<span data-ttu-id="fa6a9-124">Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fa6a9-124">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="fa6a9-125">Elemento PropertyName para ItemSelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fa6a9-125">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="fa6a9-126">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa6a9-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)