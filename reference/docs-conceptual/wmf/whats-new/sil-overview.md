---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: SIL (Log de Inventário de Software)
ms.openlocfilehash: b12cfc4ae1e505bbc4d47596bed9352ce53a98f2
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71147776"
---
# <a name="software-inventory-logging-sil"></a>SIL (Log de Inventário de Software)

> [!IMPORTANT]
> Ao instalar o WMF 5.x em um Windows Server 2012 R2 que já esteja executando o SIL, é necessário executar o cmdlet Start-SilLogging uma vez após a instalação do WMF, pois o processo de instalação interrompe incorretamente o recurso de Log de Inventário de Software.

O Log de Inventário de Software ajuda a reduzir os custos operacionais da obtenção de informações precisas sobre o software Microsoft instalado localmente em um servidor, mas especialmente em vários servidores em um ambiente de TI (presumindo-se que ele foi instalado e está em execução em todo o ambiente de TI). Desde que um esteja configurado, é possível encaminhar esses dados para um servidor de agregação e coletar os dados de log em um único local usando um processo uniforme e automático.

Embora também seja possível registrar em log os dados de inventário de software consultando cada computador diretamente, o Log de Inventário de Software, ao utilizar uma arquitetura de encaminhamento (pela rede) iniciada por cada servidor, pode superar os desafios comuns da descoberta de servidor para muitos cenários de gerenciamento de ativos e de inventário de software. O Log de Inventário de Software usa o SSL para proteger os dados que são encaminhados por HTTPS para um servidor de agregação. Armazenar os dados em um único local torna os dados mais fáceis de analisar, manipular e compartilhar, quando necessário.

Nenhum desses dados são enviados à Microsoft como parte da funcionalidade do recurso. Os dados e a funcionalidade do Log de Inventário de Software destinam-se para utilização exclusiva do proprietário e administradores autorizados do software do servidor.

Para saber mais e obter a documentação sobre os cmdlets do Log de Inventário de Software, confira [Gerenciar o Log de Inventário de Software no Windows Server 2012 R2](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383584(v=ws.11)).
