---
title: Como nomear um arquivo CAB de ajuda atualizável | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de302da0-c17a-4d31-a8ef-14a626738993
caps.latest.revision: 7
ms.openlocfilehash: 0b58d5ee19a85bed26bc6549ced48b890cd62f64
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082355"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a>Como nomear um arquivo CAB de ajuda atualizável

Este tópico explica o formato de nome necessário para o arquivo de gabinete de ajuda atualizável (. Arquivos CAB).

## <a name="how-to-name-an-updatable-help-cab-file"></a>Como nomear um arquivo CAB de ajuda atualizável

Atualizável é um gabinete (. Arquivo CAB) deve ter um nome com o seguinte formato.

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

Os elementos do nome são da seguinte maneira.

ModuleName o valor da **nome** propriedade da **ModuleInfo** do objeto que o [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet retorna.

ModuleGUID o valor da **GUID** chave no manifesto de módulo.

Cultura de UICulture a interface do usuário dos arquivos de Ajuda no arquivo CAB. Esse valor deve corresponder ao valor de um dos **UICulture** elementos no arquivo XML HelpInfo para o módulo.

Por exemplo, se o nome do módulo é "TestModule", o GUID do módulo é 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 e a cultura de interface do usuário é "en-US", o nome do arquivo CAB seria:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`