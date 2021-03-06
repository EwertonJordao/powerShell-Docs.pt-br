---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Recurso User de DSC
ms.openlocfilehash: 04543351df19160a2da05ccea96e5d392d8c55bf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076882"
---
# <a name="dsc-user-resource"></a>Recurso User de DSC

Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0

O recurso **User** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para contas de usuário locais no nó de destino.

## <a name="syntax"></a>Sintaxe

```
User [string] #ResourceName
{
    UserName = [string]
    [ Description = [string] ]
    [ Disabled = [bool] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ FullName = [string] ]
    [ Password = [PSCredential] ]
    [ PasswordChangeNotAllowed = [bool] ]
    [ PasswordChangeRequired = [bool] ]
    [ PasswordNeverExpires = [bool] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a>Propriedades

|  Propriedade  |  Descrição   |
|---|---|
| UserName| Indica o nome da conta para a qual você deseja garantir um estado específico.|
| Descrição| Indica a descrição que você deseja usar para a conta de usuário.|
| Desabilitado| Indica se a conta está habilitada. Defina essa propriedade como `$true` para garantir que essa conta esteja desabilitada e defina-a como `$false` para garantir que esteja habilitada.|
| Ensure| Indica se a conta existe. Defina essa propriedade como "Present" para garantir que a conta exista e defina-o como "Absent" para garantir que a conta não exista.|
| FullName| Representa uma cadeia de caracteres com o nome completo que você deseja usar para a conta de usuário.|
| Senha| Indica a senha que você deseja usar para essa conta. |
| PasswordChangeNotAllowed| Indica se o usuário pode alterar a senha. Defina essa propriedade como `$true` para garantir que o usuário não possa alterar a senha e defina-a como `$false` para permitir que o usuário altere a senha. O valor padrão é `$false`.|
| PasswordChangeRequired| Indica se o usuário deve alterar a senha na próxima entrada. Defina essa propriedade como `$true` se o usuário precisar alterar a senha. O valor padrão é `$true`.|
| PasswordNeverExpires| Indica se a senha vai expirar. Para garantir que a senha para essa conta nunca expire, defina essa propriedade como `$true`; defina-a como `$false` caso a senha vá expirar. O valor padrão é `$false`.|
| DependsOn | Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for **ResourceName** e seu tipo for **ResourceType**, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.|

## <a name="example"></a>Exemplo

```powershell
User UserExample
{
    Ensure = "Present"  # To ensure the user account does not exist, set Ensure to "Absent"
    UserName = "SomeName"
    Password = $passwordCred # This needs to be a credential object
    DependsOn = "[Group]GroupExample" # Configures GroupExample first
}
```