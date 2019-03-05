---
title: Elemento TableControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1550b068-dfbc-4ae0-9aa1-72c9a680ec59
caps.latest.revision: 15
ms.openlocfilehash: dd48e82452e83f93e2e005c9db53bbc51d8b2eb4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858912"
---
# <a name="tablecontrol-element-format"></a><span data-ttu-id="555a8-102">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-102">TableControl Element (Format)</span></span>

<span data-ttu-id="555a8-103">Define um formato de tabela para um modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="555a8-103">Defines a table format for a view.</span></span>

<span data-ttu-id="555a8-104">Elemento ViewDefinitions (formato) modo de exibição (formato) TableControl elemento (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="555a8-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="555a8-105">Syntax</span></span>

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="555a8-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="555a8-106">Attributes and Elements</span></span>

<span data-ttu-id="555a8-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TableControl` elemento.</span><span class="sxs-lookup"><span data-stu-id="555a8-107">The following sections describe attributes, child elements, and parent element of the `TableControl` element.</span></span> <span data-ttu-id="555a8-108">Você deve especificar as linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="555a8-108">You must specify the rows of the table.</span></span> <span data-ttu-id="555a8-109">Todos os outros elementos filho são opcionais.</span><span class="sxs-lookup"><span data-stu-id="555a8-109">All other child elements are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="555a8-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="555a8-110">Attributes</span></span>

<span data-ttu-id="555a8-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="555a8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="555a8-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="555a8-112">Child Elements</span></span>

|<span data-ttu-id="555a8-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="555a8-113">Element</span></span>|<span data-ttu-id="555a8-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="555a8-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="555a8-115">Elemento AutoSize para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-115">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)|<span data-ttu-id="555a8-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="555a8-116">Optional element.</span></span><br /><br /> <span data-ttu-id="555a8-117">Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.</span><span class="sxs-lookup"><span data-stu-id="555a8-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="555a8-118">Elemento HideTableHeaders para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-118">HideTableHeaders Element for TableControl (Format)</span></span>](./hidetableheaders-element-format.md)|<span data-ttu-id="555a8-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="555a8-119">Optional element.</span></span><br /><br /> <span data-ttu-id="555a8-120">Indica se o cabeçalho da tabela não é exibido.</span><span class="sxs-lookup"><span data-stu-id="555a8-120">Indicates whether the header of the table is not displayed.</span></span>|
|[<span data-ttu-id="555a8-121">Elemento TableHeaders para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-121">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="555a8-122">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="555a8-122">Required element.</span></span><br /><br /> <span data-ttu-id="555a8-123">Define os rótulos, as larguras e o alinhamento dos dados para as colunas da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="555a8-123">Defines the labels, the widths, and the alignment of the data for the columns of the table view.</span></span>|
|[<span data-ttu-id="555a8-124">Elemento TableRowEntries para TableCotrol (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-124">TableRowEntries Element for TableCotrol (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="555a8-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="555a8-125">Optional element.</span></span><br /><br /> <span data-ttu-id="555a8-126">Fornece as definições da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="555a8-126">Provides the definitions of the table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="555a8-127">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="555a8-127">Parent Elements</span></span>

|<span data-ttu-id="555a8-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="555a8-128">Element</span></span>|<span data-ttu-id="555a8-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="555a8-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="555a8-130">Elemento de exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-130">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="555a8-131">Define uma exibição que é usada para exibir os membros de um ou mais objetos.</span><span class="sxs-lookup"><span data-stu-id="555a8-131">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="555a8-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="555a8-132">Remarks</span></span>

<span data-ttu-id="555a8-133">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="555a8-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="555a8-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="555a8-134">Example</span></span>

<span data-ttu-id="555a8-135">Este exemplo mostra uma `TableControl` que é usado para exibir as propriedades do elemento de [ServiceProcess](/dotnet/api/System.ServiceProcess.ServiceController) objeto.</span><span class="sxs-lookup"><span data-stu-id="555a8-135">This example shows a `TableControl` element that is used to display the properties of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>...</TableHeaders>
    <TableRowEntries>...</TableRowEntries>
  </TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="555a8-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="555a8-136">See Also</span></span>

[<span data-ttu-id="555a8-137">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="555a8-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="555a8-138">Elemento de exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-138">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="555a8-139">Elemento AutoSize para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-139">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)

[<span data-ttu-id="555a8-140">Elemento HideTableHeaders (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-140">HideTableHeaders Element (Format)</span></span>](./hidetableheaders-element-format.md)

[<span data-ttu-id="555a8-141">Elemento TableHeaders (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-141">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="555a8-142">Elemento TableRowEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="555a8-142">TableRowEntries Element (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="555a8-143">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="555a8-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)