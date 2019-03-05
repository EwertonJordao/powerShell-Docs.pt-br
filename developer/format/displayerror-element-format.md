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
ms.openlocfilehash: 431e5d8407b9f689a5224b329d8c7b52802e19e1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854912"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="32105-102">Elemento DisplayError (formato)</span><span class="sxs-lookup"><span data-stu-id="32105-102">DisplayError Element (Format)</span></span>

<span data-ttu-id="32105-103">Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro exibindo uma parte dos dados.</span><span class="sxs-lookup"><span data-stu-id="32105-103">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="32105-104">Configuração (formato) elemento DefaultSettings (formato) DisplayError elemento (Frmat)</span><span class="sxs-lookup"><span data-stu-id="32105-104">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Frmat)</span></span>

## <a name="syntax"></a><span data-ttu-id="32105-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="32105-105">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="32105-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="32105-106">Attributes and Elements</span></span>

<span data-ttu-id="32105-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `DisplayError` elemento.</span><span class="sxs-lookup"><span data-stu-id="32105-107">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="32105-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="32105-108">Attributes</span></span>

<span data-ttu-id="32105-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="32105-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="32105-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="32105-110">Child Elements</span></span>

<span data-ttu-id="32105-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="32105-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="32105-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="32105-112">Parent Elements</span></span>

|<span data-ttu-id="32105-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="32105-113">Element</span></span>|<span data-ttu-id="32105-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="32105-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="32105-115">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="32105-115">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="32105-116">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="32105-116">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="32105-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="32105-117">Remarks</span></span>

<span data-ttu-id="32105-118">Por padrão, quando ocorre um erro ao tentar exibir uma parte dos dados, o local dos dados for deixado em branco.</span><span class="sxs-lookup"><span data-stu-id="32105-118">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="32105-119">Quando esse elemento é definido como true, a cadeia de caracteres #ERR será exibido.</span><span class="sxs-lookup"><span data-stu-id="32105-119">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="32105-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32105-120">See Also</span></span>

[<span data-ttu-id="32105-121">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="32105-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="32105-122">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="32105-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)