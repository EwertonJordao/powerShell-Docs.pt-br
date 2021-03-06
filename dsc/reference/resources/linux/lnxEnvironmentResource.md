---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Recurso nxEnvironment de DSC para Linux
ms.openlocfilehash: 763ec560faa6adaf42aef3c21c9045be95f780bc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078003"
---
# <a name="dsc-for-linux-nxenvironment-resource"></a>Recurso nxEnvironment de DSC para Linux

O recurso **nxEnvironment** na Configuração de Estado Desejado (DSC) do PowerShell fornece um mecanismo para gerenciar as variáveis de ambiente do sistema em um nó do Linux.

## <a name="syntax"></a>Sintaxe

```
nxEnvironment <string> #ResourceName
{
    Name = <string>
    [ Value = <string>
    [ Ensure = <string> { Absent | Present }  ]
    [ Path = <bool> }
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a>Propriedades

|  Propriedade |  Descrição |
|---|---|
| Nome| Indica o nome da variável de ambiente para a qual você deseja garantir um estado específico.|
| Valor| O valor que será atribuído à variável de ambiente.|
| Ensure| Determina se é necessário verificar se a variável existe. Defina essa propriedade como "Present" para garantir que a variável exista. Defina-a como "Absent" para garantir que a variável não exista. O valor padrão é "Present".|
| Caminho| Define a variável de ambiente que está sendo configurada. Defina essa propriedade como **$true** se a variável for a variável **Path**; caso contrário, defina-a como **$false**. O padrão é **$false**. Se a variável que estiver sendo configurada for a variável **Path**, o valor fornecido por meio da propriedade **Value** será acrescentado ao valor existente.|
| DependsOn | Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a **ID** do bloco de script de configuração do recurso que você deseja executar primeiro for **ResourceName** e seu tipo for **ResourceType**, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.|

## <a name="additional-information"></a>Informações adicionais

* Se **Path** estiver ausente ou configurado como **$false**, as variáveis de ambiente serão gerenciadas em `/etc/environment`. Seus programas ou scripts poderão exigir uma configuração para fornecer o arquivo `/etc/environment` para acessar as variáveis de ambiente gerenciadas.
* Se **Path** estiver definido como **$true**, a variável de ambiente será gerenciada no arquivo `/etc/profile.d/DSCenvironment.sh`. Esse arquivo será criado se não existir. Se **Ensure** estiver definido com "Absent" e **Path** estiver definido como **$true**, uma variável de ambiente existente será removida apenas de `/etc/profile.d/DSCenvironment.sh` e não de outros arquivos.

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como usar o recurso **nxEnvironment** para garantir que **TestEnvironmentVariable** esteja presente e tenha o valor "Test-Value". Se **TestEnvironmentVariable** não estiver presente, será criado.

```
Import-DSCResource -Module nx


nxEnvironment EnvironmentExample
{
    Ensure = “Present”
    Name = “TestEnvironmentVariable”
    Value = “TestValue”
}
```