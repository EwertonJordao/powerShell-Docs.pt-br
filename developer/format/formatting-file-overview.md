---
title: Visão geral do arquivo de formatação | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe888fee-1fe9-459f-9d62-35732c19a7f8
caps.latest.revision: 13
ms.openlocfilehash: d418cff70c1197aa3c331eed909f49198da139e9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065726"
---
# <a name="formatting-file-overview"></a><span data-ttu-id="7294a-102">Visão geral do arquivo de formatação</span><span class="sxs-lookup"><span data-stu-id="7294a-102">Formatting File Overview</span></span>

<span data-ttu-id="7294a-103">O formato de exibição para os objetos que são retornados pelos comandos (cmdlets, funções e scripts) são definidas usando arquivos de formatação (format.ps1xml arquivos).</span><span class="sxs-lookup"><span data-stu-id="7294a-103">The display format for the objects that are returned by commands (cmdlets, functions, and scripts) are defined by using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="7294a-104">Vários desses arquivos são fornecidos pelo PowerShell para definir o formato de exibição para os objetos retornados por comandos fornecidos pelo PowerShell, como o [Diagnostics](/dotnet/api/System.Diagnostics.Process) objeto retornado pelo `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7294a-104">Several of these files are provided by PowerShell to define the display format for those objects returned by PowerShell-provided commands, such as the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object returned by the `Get-Process` cmdlet.</span></span> <span data-ttu-id="7294a-105">No entanto, você também pode criar seus próprios arquivos de formatação personalizados para substituir os formatos de exibição padrão, ou você pode escrever um arquivo de formatação personalizado para definir a exibição de objetos retornados pelos seus próprios comandos.</span><span class="sxs-lookup"><span data-stu-id="7294a-105">However, you can also create your own custom formatting files to overwrite the default display formats or you can write a custom formatting file to define the display of objects returned by your own commands.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7294a-106">Arquivos de formatação não determinam os elementos de um objeto que são retornados para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="7294a-106">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="7294a-107">Quando um objeto é retornado para o pipeline, todos os membros desse objeto estão disponíveis, mesmo se alguns não são exibidos.</span><span class="sxs-lookup"><span data-stu-id="7294a-107">When an object is returned to the pipeline, all members of that object are available even if some are not displayed.</span></span>

<span data-ttu-id="7294a-108">PowerShell usa os dados nesses arquivos de formatação para determinar o que é exibido e como os dados exibidos são formatados.</span><span class="sxs-lookup"><span data-stu-id="7294a-108">PowerShell uses the data in these formatting files to determine what is displayed and how the displayed data is formatted.</span></span> <span data-ttu-id="7294a-109">Os dados exibidos podem incluir as propriedades de um objeto ou o valor de um script.</span><span class="sxs-lookup"><span data-stu-id="7294a-109">The displayed data can include the properties of an object or the value of a script.</span></span> <span data-ttu-id="7294a-110">Scripts são usados se você quiser exibir algum valor que não está disponível diretamente das propriedades de um objeto, como a adição do valor de duas propriedades de um objeto e, em seguida, exibindo a soma como uma parte dos dados.</span><span class="sxs-lookup"><span data-stu-id="7294a-110">Scripts are used if you want to display some value that is not available directly from the properties of an object, such as adding the value of two properties of an object and then displaying the sum as a piece of data.</span></span> <span data-ttu-id="7294a-111">Formatação dos dados exibidos é feita com a definição de modos de exibição para os objetos que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="7294a-111">Formatting of the displayed data is done by defining views for the objects that you want to display.</span></span> <span data-ttu-id="7294a-112">Você pode definir uma exibição única para cada objeto, você pode definir uma exibição única para vários objetos, ou você pode definir vários modos de exibição para o mesmo objeto.</span><span class="sxs-lookup"><span data-stu-id="7294a-112">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="7294a-113">Não há nenhum limite para o número de modos de exibição que você pode definir.</span><span class="sxs-lookup"><span data-stu-id="7294a-113">There is no limit to the number of views that you can define.</span></span>

## <a name="common-features-of-formatting-files"></a><span data-ttu-id="7294a-114">Recursos comuns de arquivos de formatação</span><span class="sxs-lookup"><span data-stu-id="7294a-114">Common Features of Formatting Files</span></span>

<span data-ttu-id="7294a-115">Cada arquivo de formatação pode definir os seguintes componentes que podem ser compartilhados entre todas as exibições definidas pelo arquivo:</span><span class="sxs-lookup"><span data-stu-id="7294a-115">Each formatting file can define the following components that can be shared across all the views defined by the file:</span></span>

- <span data-ttu-id="7294a-116">O padrão de definição de configuração, como se os dados exibidos nas linhas das tabelas serão exibidos na próxima linha se os dados são maiores que a largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="7294a-116">Default configuration setting, such as whether the data displayed in the rows of tables will be displayed on the next line if the data is longer than the width of the column.</span></span> <span data-ttu-id="7294a-117">Para obter mais informações sobre essas configurações, consulte [definindo as configurações comuns](./defining-common-configuration-features.md).</span><span class="sxs-lookup"><span data-stu-id="7294a-117">For more information about these settings, see [Defining Common Configuration Settings](./defining-common-configuration-features.md).</span></span>

- <span data-ttu-id="7294a-118">Conjuntos de objetos que podem ser exibidos por qualquer um dos modos de exibição do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="7294a-118">Sets of objects that can be displayed by any of the views of the formatting file.</span></span> <span data-ttu-id="7294a-119">Para obter mais informações sobre esses conjuntos (conhecido como *conjuntos de seleção*), consulte [definindo define de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="7294a-119">For more information about these sets (referred to as *selection sets*), see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

- <span data-ttu-id="7294a-120">Controles comuns que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="7294a-120">Common controls that can be used by all the views of the formatting file.</span></span> <span data-ttu-id="7294a-121">Controles oferecem maior controle sobre como os dados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="7294a-121">Controls give you finer control on how data is displayed.</span></span> <span data-ttu-id="7294a-122">Para obter mais informações sobre controles, consulte [definindo Custom Controls](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="7294a-122">For more information about controls, see [Defining Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="formatting-views"></a><span data-ttu-id="7294a-123">As exibições de formatação</span><span class="sxs-lookup"><span data-stu-id="7294a-123">Formatting Views</span></span>

<span data-ttu-id="7294a-124">Formatação de modos de exibição podem exibir objetos em um formato de tabela, o formato de lista, o formato amplo e o formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="7294a-124">Formatting views can display objects in a table format, list format, wide format, and custom format.</span></span> <span data-ttu-id="7294a-125">Geralmente, cada definição de formatação é descrita por um conjunto de marcas XML que descrevem o modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="7294a-125">For the most part, each formatting definition is described by a set of XML tags that describe the view.</span></span> <span data-ttu-id="7294a-126">Cada modo de exibição contém o nome da exibição, os objetos que usam o modo de exibição e os elementos da exibição, como as informações de linha e coluna para uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="7294a-126">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="7294a-127">Modo de exibição lista as propriedades de um objeto ou um valor de bloco de script em uma ou mais colunas da tabela.</span><span class="sxs-lookup"><span data-stu-id="7294a-127">Table View Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="7294a-128">Cada coluna representa uma única propriedade do objeto ou um valor de script.</span><span class="sxs-lookup"><span data-stu-id="7294a-128">Each column represents a single property of the object or a script value.</span></span> <span data-ttu-id="7294a-129">Você pode definir uma exibição de tabela que exibe todas as propriedades de um objeto, um subconjunto das propriedades de um objeto ou uma combinação de propriedades e valores de script.</span><span class="sxs-lookup"><span data-stu-id="7294a-129">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script values.</span></span> <span data-ttu-id="7294a-130">Cada linha da tabela representa um objeto retornado.</span><span class="sxs-lookup"><span data-stu-id="7294a-130">Each row of the table represents a returned object.</span></span> <span data-ttu-id="7294a-131">Criar uma exibição de tabela é muito semelhante a quando você direciona um objeto para o `Format-Table` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7294a-131">Creating a table view is very similar to when you pipe an object to the `Format-Table` cmdlet.</span></span> <span data-ttu-id="7294a-132">Para obter mais informações sobre este modo de exibição, consulte [exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="7294a-132">For more information about this view, see [Table View](./creating-a-table-view.md).</span></span>

<span data-ttu-id="7294a-133">Liste o modo de exibição lista as propriedades de um objeto ou um valor de script em uma única coluna.</span><span class="sxs-lookup"><span data-stu-id="7294a-133">List View Lists the properties of an object or a script value in a single column.</span></span> <span data-ttu-id="7294a-134">Cada linha da lista exibe um rótulo opcional ou o nome da propriedade seguido pelo valor da propriedade ou do script.</span><span class="sxs-lookup"><span data-stu-id="7294a-134">Each row of the list displays an optional label or the property name followed by the value of the property or script.</span></span> <span data-ttu-id="7294a-135">Criar uma exibição de lista é muito semelhante ao canalizar um objeto para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7294a-135">Creating a list view is very similar to piping an object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="7294a-136">Para obter mais informações sobre este modo de exibição, consulte [exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="7294a-136">For more information about this view, see [List View](./creating-a-list-view.md).</span></span>

<span data-ttu-id="7294a-137">Exibição ampla com a lista de uma única propriedade de um objeto ou um valor de script em uma ou mais colunas.</span><span class="sxs-lookup"><span data-stu-id="7294a-137">Wide View Lists a single property of an object or a script value in one or more columns.</span></span> <span data-ttu-id="7294a-138">Não há nenhum rótulo ou o cabeçalho para este modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="7294a-138">There is no label or header for this view.</span></span> <span data-ttu-id="7294a-139">Criar uma exibição ampla é muito semelhante ao canalizar um objeto para o `Format-Wide` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7294a-139">Creating a wide view is very similar to piping an object to the `Format-Wide` cmdlet.</span></span> <span data-ttu-id="7294a-140">Para obter mais informações sobre este modo de exibição, consulte [exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="7294a-140">For more information about this view, see [Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="7294a-141">Exibição personalizada mostra uma exibição personalizável de propriedades do objeto ou valores de script que não seguem a estrutura rígida de modos de exibição de tabela, exibições de lista ou exibições amplas.</span><span class="sxs-lookup"><span data-stu-id="7294a-141">Custom View Displays a customizable view of object properties or script values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="7294a-142">Você pode definir uma exibição personalizada autônoma, ou você pode definir uma exibição personalizada que é usada por outro modo de exibição, como uma exibição de tabela ou exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="7294a-142">You can define a stand-alone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="7294a-143">Criar um modo de exibição personalizado é muito semelhante ao canalizar um objeto para o `Format-Custom` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7294a-143">Creating a custom view is very similar to piping an object to the `Format-Custom` cmdlet.</span></span> <span data-ttu-id="7294a-144">Para obter mais informações sobre este modo de exibição, consulte [modo de exibição personalizado](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="7294a-144">For more information about this view, see [Custom View](./creating-custom-controls.md).</span></span>

## <a name="components-of-a-view"></a><span data-ttu-id="7294a-145">Componentes de uma exibição</span><span class="sxs-lookup"><span data-stu-id="7294a-145">Components of a View</span></span>

<span data-ttu-id="7294a-146">Os exemplos XML a seguir mostram os componentes básicos do XML de uma exibição.</span><span class="sxs-lookup"><span data-stu-id="7294a-146">The following XML examples show the basic XML components of a view.</span></span> <span data-ttu-id="7294a-147">Os elementos XML individuais variam, dependendo de qual modo você deseja criar, mas os componentes básicos dos modos de exibição são todas iguais.</span><span class="sxs-lookup"><span data-stu-id="7294a-147">The individual XML elements vary depending on which view you want to create, but the basic components of the views are all the same.</span></span>

<span data-ttu-id="7294a-148">Para começar, cada exibição tem um `Name` elemento que especifica um nome de usuário amigável que é usado para referenciar o modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="7294a-148">To start with, each view has a `Name` element that specifies a user friendly name that is used to reference the view.</span></span> <span data-ttu-id="7294a-149">uma `ViewSelectedBy` elemento que define quais objetos .NET são exibidos pelo modo de exibição, e uma *controle* elemento que define o modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="7294a-149">a `ViewSelectedBy` element that defines which .NET objects are displayed by the view, and a *control* element that defines the view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <ListControl>...</ListControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <WideControl>...</WideControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <CustomControl>...</CustomControl>
  </View>
</ViewDefinitions>

```

<span data-ttu-id="7294a-150">Dentro do elemento de controle, você pode definir um ou mais *entrada* elementos.</span><span class="sxs-lookup"><span data-stu-id="7294a-150">Within the control element, you can define one or more *entry* elements.</span></span> <span data-ttu-id="7294a-151">Se você usar várias definições, você deve especificar quais objetos .NET usam cada definição.</span><span class="sxs-lookup"><span data-stu-id="7294a-151">If you use multiple definitions, you must specify which .NET objects use each definition.</span></span> <span data-ttu-id="7294a-152">Normalmente, apenas uma entrada, com apenas uma definição, é necessário para cada controle.</span><span class="sxs-lookup"><span data-stu-id="7294a-152">Typically only one entry, with only one definition, is needed for each control.</span></span>

```xml
<ListControl>
  <ListEntries>
    <ListEntry>
      <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
  </ListEntries>
</ListControl>

```

<span data-ttu-id="7294a-153">Dentro de cada elemento de entrada de uma exibição, você deve especificar o *item* elementos que definem as propriedades .NET ou scripts que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="7294a-153">Within each entry element of a view, you specify the *item* elements that define the .NET properties or scripts that are displayed by that view.</span></span>

```xml

<ListItems>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
</ListItems>

```

<span data-ttu-id="7294a-154">Conforme mostrado nos exemplos anteriores, o arquivo de formatação pode conter vários modos de exibição, um modo de exibição pode conter várias definições e cada definição pode conter vários itens.</span><span class="sxs-lookup"><span data-stu-id="7294a-154">As shown in the preceding examples, the formatting file can contain multiple views, a view can contain multiple definitions, and each definition can contain multiple items.</span></span>

## <a name="example-of-a-table-view"></a><span data-ttu-id="7294a-155">Exemplo de uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="7294a-155">Example of a Table View</span></span>

<span data-ttu-id="7294a-156">O exemplo a seguir mostra as marcas XML usadas para definir uma exibição de tabela que contém duas colunas.</span><span class="sxs-lookup"><span data-stu-id="7294a-156">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="7294a-157">O [ViewDefinitions](./viewdefinitions-element-format.md) é o elemento de contêiner para todas as exibições definidas no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="7294a-157">The [ViewDefinitions](./viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="7294a-158">O [exibição](./view-element-format.md) elemento define a tabela específica, a lista, o modo de exibição amplo ou personalizado.</span><span class="sxs-lookup"><span data-stu-id="7294a-158">The [View](./view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="7294a-159">Dentro de cada [modo de exibição](./view-element-format.md) elemento, o [nome](./name-element-for-view-format.md) elemento Especifica o nome da exibição, o [ViewSelectedBy](./viewselectedby-element-format.md) elemento define os objetos que usam o modo de exibição e os diferentes elementos de controle (como o `TableControl` elemento mostrado no exemplo a seguir) definem o tipo de exibição.</span><span class="sxs-lookup"><span data-stu-id="7294a-159">Within each [View](./view-element-format.md) element, the [Name](./name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element shown in the following example) define the type of the view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>Name of View</Name>
    <ViewSelectedBy>
      <TypeName>Object to display using this view</TypeName>
      <TypeName>Object to display using this view</TypeName>
    </ViewSelectedBy>
    <TableControl>
      <TableHeaders>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
      </TableHeaders>
      <TableRowEntries>
        <TableRowEntry>
          <TableColumnItems>
            <TableColumnItem>
              <PropertyName>Header for column 1</PropertyName>
            </TableColumnItem>
            <TableColumnItem>
              <PropertyName>Header for column 2</PropertyName>
            </TableColumnItem>
          </TableColumnItems>
        </TableRowEntry>
      </TableRowEntries>
    </TableControl)
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="7294a-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7294a-160">See Also</span></span>

[<span data-ttu-id="7294a-161">Criando uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="7294a-161">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7294a-162">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="7294a-162">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7294a-163">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="7294a-163">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="7294a-164">Criação de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="7294a-164">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="7294a-165">Escrevendo uma formatação de PowerShell e tipos de arquivo</span><span class="sxs-lookup"><span data-stu-id="7294a-165">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
