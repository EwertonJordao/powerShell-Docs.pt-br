---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Recurso nxService de DSC para Linux
ms.openlocfilehash: fe8043995205649378725f2ab0a78e19313739c9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077680"
---
# <a name="dsc-for-linux-nxservice-resource"></a>Recurso nxService de DSC para Linux

O recurso **nxService** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar serviços em um nó do Linux.

## <a name="syntax"></a>Sintaxe

```
nxService <string> #ResourceName
{
    Name = <string>
    [ Controller = <string> { init | upstart | systemd } ]
    [ Enabled = <bool> ]
    [ State = <string> { Running | Stopped } ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a>Propriedades

| Propriedade | Descrição |
|---|---|
| Nome| O nome do serviço/daemon que será configurado.|
| Controlador| O tipo de controlador de serviço que deve ser usado ao configurar o serviço.|
| Habilitada| Indica se o serviço começa na inicialização.|
| Estado| Indica se o serviço está em execução. Defina essa propriedade como "Stopped" para garantir que o serviço não esteja em execução. Defina-a como "Running" para garantir que o serviço esteja em execução.|
| DependsOn | Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a **ID** do bloco de script de configuração do recurso que você deseja executar primeiro for **ResourceName** e seu tipo for **ResourceType**, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.|

## <a name="additional-information"></a>Informações adicionais

O recurso **nxService** não criará uma definição de serviço ou um script para o serviço se não existir. É possível usar o recurso **nxFile** de Configuração de Estado Desejado do PowerShell para gerenciar a existência ou o conteúdo do arquivo ou script de definição de serviço.

## <a name="example"></a>Exemplo

O exemplo a seguir mostra a configuração do serviço 'httpd' (para o Apache HTTP Server), registrado com o controlador de serviço **SystemD**.

```powershell
Import-DSCResource -Module nx

Node $node {
    #Apache Service
    nxService ApacheService {
        Name = 'httpd'
        State = 'running'
        Enabled = $true
        Controller = 'systemd'
    }
}
```