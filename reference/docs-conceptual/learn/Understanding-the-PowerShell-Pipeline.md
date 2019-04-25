---
ms.date: 08/23/2018
keywords: powershell, cmdlet
title: Noções básicas dos pipelines do PowerShell
ms.assetid: 6be50926-7943-4ef7-9499-4490d72a63fb
ms.openlocfilehash: 05ab98b7261f4d41ade1788a924193eccda6318c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086435"
---
# <a name="understanding-pipelines"></a><span data-ttu-id="1c6ae-103">Noções básicas dos pipelines</span><span class="sxs-lookup"><span data-stu-id="1c6ae-103">Understanding pipelines</span></span>

<span data-ttu-id="1c6ae-104">Pipelines atuam como uma série de segmentos conectados do pipe.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-104">Pipelines act like a series of connected segments of pipe.</span></span> <span data-ttu-id="1c6ae-105">Itens que se movem pelo pipeline passam por cada segmento.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-105">Items moving along the pipeline pass through each segment.</span></span> <span data-ttu-id="1c6ae-106">Para criar um pipeline no PowerShell, você conectar comandos com o operador de barra vertical "|".</span><span class="sxs-lookup"><span data-stu-id="1c6ae-106">To create a pipeline in PowerShell, you connect commands together with the pipe operator "|".</span></span> <span data-ttu-id="1c6ae-107">A saída de cada comando é usada como entrada para o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-107">The output of each command is used as input to the next command.</span></span>

<span data-ttu-id="1c6ae-108">A notação usada para pipelines é semelhante à notação usada em outros shells.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-108">The notation used for pipelines is similar to the notation used in other shells.</span></span> <span data-ttu-id="1c6ae-109">À primeira vista, talvez seja aparente como os pipelines são diferentes no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-109">At first glance, it may not be apparent how pipelines are different in PowerShell.</span></span> <span data-ttu-id="1c6ae-110">Embora você veja o texto na tela, o PowerShell redireciona objetos, e não o texto, entre comandos.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-110">Although you see text on the screen, PowerShell pipes objects, not text, between commands.</span></span>

## <a name="the-powershell-pipeline"></a><span data-ttu-id="1c6ae-111">O pipeline do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c6ae-111">The PowerShell pipeline</span></span>

<span data-ttu-id="1c6ae-112">Pipelines são possivelmente o conceito mais valioso usado nas interfaces de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-112">Pipelines are arguably the most valuable concept used in command-line interfaces.</span></span> <span data-ttu-id="1c6ae-113">Quando usada corretamente, pipelines reduzem o esforço do uso de comandos complexos facilitam a visualização do fluxo de trabalho dos comandos.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-113">When used properly, pipelines reduce the effort of using complex commands and make it easier to see the flow of work for the commands.</span></span> <span data-ttu-id="1c6ae-114">Cada comando em um pipeline (chamado de um elemento de pipeline) passa sua saída para o próximo comando do pipeline, item por item.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-114">Each command in a pipeline (called a pipeline element) passes its output to the next command in the pipeline, item-by-item.</span></span> <span data-ttu-id="1c6ae-115">Os comandos não precisam lidar com mais de um item por vez.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-115">Commands don't have to handle more than one item at a time.</span></span> <span data-ttu-id="1c6ae-116">O resultado é o consumo de recursos reduzido e a capacidade de começar obtendo saída imediatamente.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-116">The result is reduced resource consumption and the ability to begin getting the output immediately.</span></span>

<span data-ttu-id="1c6ae-117">Por exemplo, se você usar o cmdlet `Out-Host` para forçar uma exibição de página a página da saída de outro comando, a saída parecerá ser apenas o texto normal exibido na tela, dividida em páginas:</span><span class="sxs-lookup"><span data-stu-id="1c6ae-117">For example, if you use the `Out-Host` cmdlet to force a page-by-page display of output from another command, the output looks just like the normal text displayed on the screen, broken up into pages:</span></span>

```powershell
Get-ChildItem -Path C:\WINDOWS\System32 | Out-Host -Paging
```

```Output
    Directory: C:\WINDOWS\system32

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        4/12/2018   2:15 AM                0409
d-----        5/13/2018  11:31 PM                1033
d-----        4/11/2018   4:38 PM                AdvancedInstallers
d-----        5/13/2018  11:13 PM                af-ZA
d-----        5/13/2018  11:13 PM                am-et
d-----        4/11/2018   4:38 PM                AppLocker
d-----        5/13/2018  11:31 PM                appmgmt
d-----        7/11/2018   2:05 AM                appraiser
d---s-        4/12/2018   2:20 AM                AppV
d-----        5/13/2018  11:10 PM                ar-SA
d-----        5/13/2018  11:13 PM                as-IN
d-----        8/14/2018   9:03 PM                az-Latn-AZ
d-----        5/13/2018  11:13 PM                be-BY
d-----        5/13/2018  11:10 PM                BestPractices
d-----        5/13/2018  11:10 PM                bg-BG
d-----        5/13/2018  11:13 PM                bn-BD
d-----        5/13/2018  11:13 PM                bn-IN
d-----        8/14/2018   9:03 PM                Boot
d-----        8/14/2018   9:03 PM                bs-Latn-BA
d-----        4/11/2018   4:38 PM                Bthprops
d-----        4/12/2018   2:19 AM                ca-ES
d-----        8/14/2018   9:03 PM                ca-ES-valencia
d-----        5/13/2018  10:46 PM                CatRoot
d-----        8/23/2018   5:07 PM                catroot2
<SPACE> next page; <CR> next line; Q quit
...
```

<span data-ttu-id="1c6ae-118">A paginação também reduz a utilização da CPU, pois o processamento muda para o cmdlet `Out-Host` quando há uma página completa pronta para exibição.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-118">Paging also reduces CPU utilization because processing transfers to the `Out-Host` cmdlet when it has a complete page ready to display.</span></span> <span data-ttu-id="1c6ae-119">Os cmdlets que a precedem no pipeline pausam a execução até que a próxima página de saída esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-119">The cmdlets that precede it in the pipeline pause execution until the next page of output is available.</span></span>

<span data-ttu-id="1c6ae-120">Veja a diferença entre o Gerenciador de Tarefas do Windows para monitorar o uso de CPU e da memória e o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-120">You can see the difference Windows Task Manager to monitor CPU and memory used by PowerShell.</span></span> <span data-ttu-id="1c6ae-121">Execute o seguinte comando: `Get-ChildItem C:\Windows -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-121">Run the following command: `Get-ChildItem C:\Windows -Recurse`.</span></span> <span data-ttu-id="1c6ae-122">Compare o uso de CPU e de memória deste comando: `Get-ChildItem C:\Windows -Recurse | Out-Host -Paging`.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-122">Compare the CPU and memory usage to this command: `Get-ChildItem C:\Windows -Recurse | Out-Host -Paging`.</span></span>

> [!NOTE]
> <span data-ttu-id="1c6ae-123">O parâmetro **Paging** não tem suporte de todos os hosts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-123">The **Paging** parameter is not supported by all PowerShell hosts.</span></span> <span data-ttu-id="1c6ae-124">Por exemplo, ao tentar usar o parâmetro **Paging** no ISE do PowerShell, você verá o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="1c6ae-124">For example, when you try to use the **Paging** parameter in the PowerShell ISE, you see the following error:</span></span>
>
> ```Output
> out-lineoutput : The method or operation is not implemented.
> At line:1 char:1
> + Get-ChildItem C:\Windows -Recurse | Out-Host -Paging
> + ~~~~~~~~~~~~~~~~~~~~~~~~~~~
>     + CategoryInfo          : NotSpecified: (:) [out-lineoutput], NotImplementedException
>     + FullyQualifiedErrorId : System.NotImplementedException,Microsoft.PowerShell.Commands.OutLineOutputCommand
> ```

## <a name="objects-in-the-pipeline"></a><span data-ttu-id="1c6ae-125">Objetos no pipeline</span><span class="sxs-lookup"><span data-stu-id="1c6ae-125">Objects in the pipeline</span></span>

<span data-ttu-id="1c6ae-126">Quando você executa um cmdlet no PowerShell, vê a saída de texto porque é necessário representar objetos como texto em uma janela de console.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-126">When you run a cmdlet in PowerShell, you see text output because it is necessary to represent objects as text in a console window.</span></span> <span data-ttu-id="1c6ae-127">A saída de texto não pode exibir todas as propriedades do objeto mostrado.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-127">The text output may not display all of the properties of the object being output.</span></span>

<span data-ttu-id="1c6ae-128">Por exemplo, considere o cmdlet `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-128">For example, consider the `Get-Location` cmdlet.</span></span> <span data-ttu-id="1c6ae-129">Se você executar `Get-Location` enquanto seu local atual for a raiz da unidade C, você verá a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="1c6ae-129">If you run `Get-Location` while your current location is the root of the C drive, you see the following output:</span></span>

```
PS> Get-Location

Path
----
C:\
```

<span data-ttu-id="1c6ae-130">A saída de texto é um resumo das informações, não uma representação completa do objeto retornado por `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-130">The text output is a summary of information, not a complete representation of the object returned by `Get-Location`.</span></span> <span data-ttu-id="1c6ae-131">O título na saída é adicionado pelo processo que formata os dados para exibição na tela.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-131">The heading in the output is added by the process that formats the data for onscreen display.</span></span>

<span data-ttu-id="1c6ae-132">Quando você direciona a saída para o cmdlet `Get-Member`, obtém informações sobre o objeto retornado por `Get-Location`.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-132">When you pipe the output to the `Get-Member` cmdlet you get information about the object returned by `Get-Location`.</span></span>

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

<span data-ttu-id="1c6ae-133">`Get-Location` retorna um objeto **PathInfo** que contém o caminho atual e outras informações.</span><span class="sxs-lookup"><span data-stu-id="1c6ae-133">`Get-Location` returns a **PathInfo** object that contains the current path and other information.</span></span>
