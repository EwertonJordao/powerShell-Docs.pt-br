---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Recurso nxGroup de DSC para Linux
ms.openlocfilehash: c61b6ab4a8c56d085b5297dcfc7582187d54f946
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077850"
---
# <a name="dsc-for-linux-nxgroup-resource"></a>Recurso nxGroup de DSC para Linux

O recurso **nxGroup** na Configuração de Estado Desejado (DSC) do PowerShell fornece um mecanismo para gerenciar grupos locais em um nó do Linux.

## <a name="syntax"></a>Sintaxe

```
nxGroup <string> #ResourceName
{
    GroupName = <string>
    [ Ensure = <string> { Absent | Present } ]
    [ Members = <string[]> ]
    [ MembersToInclude = <string[]> ]
    [ MembersToExclude = <string[]> ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a>Propriedades

|  Propriedade |  Descrição |
|---|---|
| GroupName| Especifica o nome do grupo para o qual você deseja garantir um estado específico.|
| Ensure| Determina se é necessário verificar se o grupo existe. Defina essa propriedade como "Present" para garantir que o grupo exista. Defina-a como "Absent" para garantir que o grupo não exista. O valor padrão é "Present".|
| Membros| Especifica os membros que formam o grupo.|
| MembersToInclude| Especifica os usuários que você deseja garantir que sejam membros do grupo.|
| MembersToExclude| Especifica os usuários que você deseja garantir que não sejam membros do grupo.|
| PreferredGroupID| Define a ID do grupo para o valor fornecido, se possível. Se a ID do grupo estiver em uso no momento, a próxima ID de grupo disponível será usada.|
| DependsOn | Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a **ID** do bloco de script de configuração do recurso que você deseja executar primeiro for **ResourceName** e seu tipo for **ResourceType**, a sintaxe para usar essa propriedade será `DependsOn = '[ResourceType]ResourceName'`.|

## <a name="example"></a>Exemplo

O exemplo a seguir garante que o usuário 'monuser' exista e seja membro do grupo 'DBusers'.

```powershell
Import-DSCResource -Module nx

Node $node {
    nxUser UserExample {
       UserName = 'monuser'
       Description = 'Monitoring user'
       Password = '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
       Ensure = 'Present'
       HomeDirectory = '/home/monuser'
    }

    nxGroup GroupExample {
       GroupName = 'DBusers'
       Ensure = 'Present'
       MembersToInclude = 'monuser'
       DependsOn = '[nxUser]UserExample'
    }
}
```