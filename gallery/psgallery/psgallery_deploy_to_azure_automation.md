---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: PowerShell, cmdlet, galeria
ms.date: 2016-10-14
contributor: manikb
title: psgallery_deploy_to_azure_automation
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6c526d1074f61154d03b92b6bf6f599976f5936
ms.openlocfilehash: c028bf6145b41c13bccda9543a782b838bd730ff

---

Implantar na Automação do Azure
===========================

O botão Implantar na Automação do Azure na página de detalhes do item implantará o item da Galeria do PowerShell para a Automação do Azure.

![Botão Implantar na Automação do Azure](Images/DeployToAzureAutomationButton.png)

Quando acionado, ele redirecionará você para o Portal de Gerenciamento do Azure, em que você entra usando as credenciais de sua conta do Azure.
Se o item incluir dependências, todas as dependências serão implantadas também na Automação do Azure.

AVISO: se o mesmo item e a versão já existirem na sua conta de Automação, implantá-lo novamente da Galeria PowerShell substituirá o item na sua conta de Automação.

Se você implantar um módulo, ele será exibido na seção Módulos da Automação do Azure.  Se você implantar um script, ele será exibido na seção Runbooks da Automação do Azure.

O botão Implantar na Automação do Azure pode ser desabilitado adicionando a marca AzureAutomationNotSupported aos metadados do item.

Para saber mais sobre a Automação do Azure, consulte o site da Automação do Azure [Site da Automação do Azure](http://azure.microsoft.com/en-us/services/automation/).




<!--HONumber=Oct16_HO2-->

