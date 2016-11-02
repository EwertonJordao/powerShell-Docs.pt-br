---
title: Recurso do WindowsOptionalFeature DSC
ms.date: 2016-05-24
keywords: powershell,DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: 97714d3fa9a1c00fb3d2e79cc873280ca945a840
ms.openlocfilehash: 1254037b655a3160c90e69971c9faf061f205917

---

# Recurso do WindowsOptionalFeature DSC

> Aplica-se a: Windows PowerShell 5.0

O recurso **WindowsOptionalFeature** na DSC (Configuração de Estado Desejado) do Windows PowerShell oferece um mecanismo para garantir que os recursos opcionais sejam habilitados em um nó de destino.

## Sintaxe

```
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ Ensure = [string] { Absent | Present }  ]
    [ Source = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    
}
```

## Propriedades

|  Propriedade  |  Descrição   | 
|---|---| 
| Nome| Indica o nome do recurso que você deseja garantir que esteja habilitado ou desabilitado.| 
| Ensure| Especifica se o recurso está habilitado. Para garantir que o recurso esteja habilitado, defina essa propriedade para "Presente"; para garantir que o recurso esteja desabilitado, defina a propriedade como "Ausente".|
| Origem| Não foi implementado.|
| NoWindowsUpdateCheck| Especifica se o DISM contata o WU (Windows Update) ao procurar os arquivos de origem para habilitar um recurso. Se $true, DISM não contatará WU.|
| RemoveFilesOnDisable| Definido como **$true** para remover todos os arquivos associados ao recurso quando estiver desabilitado (isto é, quando **Garantir** estiver definido como "Ausente").|
| LogLevel| O nível máximo de saída mostrado nos logs. Os valores aceitos são: "ErrorsOnly" (somente erros são registrados), "ErrorsAndWarning" (erros e avisos são registrados) e "ErrorsAndWarningAndInformation" (erros, avisos e informações de depuração são registrados).|
| LogPath| O caminho até um arquivo de log em que você deseja que o provedor de recursos registre a operação.| 
| DependsOn| Especifica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for __ResourceName__ e seu tipo for __ResourceType__, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.| 
 






<!--HONumber=Aug16_HO3-->

