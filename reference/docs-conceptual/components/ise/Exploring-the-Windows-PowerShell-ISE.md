---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Explorando o ISE do Windows PowerShell
ms.openlocfilehash: 8c47e236e2e345a887fc3af281e429f440e176ff
ms.sourcegitcommit: a6f13c16a535acea279c0ddeca72f1f0d8a8ce4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67031037"
---
# <a name="exploring-the-windows-powershell-ise"></a>Explorando o ISE do Windows PowerShell

Você pode usar o ISE (Ambiente de Script Integrado) do Windows PowerShell® para criar, executar e depurar scripts e comandos. O ISE do Windows PowerShell é composto por uma barra de menus, guias do Windows PowerShell, a barra de ferramentas, guias de script, um Painel de Script, um Painel Console, uma barra de status, um controle deslizante de tamanho de texto e a Ajuda contextual.

> [!NOTE]
> No ISE do Windows PowerShell 3.0 os Painéis de Comando e de Saída foram combinados em um único Painel de Console.

## <a name="menu-bar"></a>Barra de menu

A barra de menus contém os menus **Arquivo**, **Editar**, **Exibir**, **Ferramentas**, **Depurar**, **Complementos** e **Ajuda**. Os botões nos menus permitem executar tarefas relacionadas à escrita e execução de scripts e execução de comandos no ISE do Windows PowerShell. Além disso, é possível colocar uma [ferramenta complementar](../../core-powershell/ise/The-ISEAddOnTool-Object.md) na barra de menus executando os scripts que usam a [hierarquia de modelo de objeto do ISE](../../core-powershell/ise/The-ISE-Object-Model-Hierarchy.md).

> [!NOTE]
> No ISE do Windows PowerShell 2.0, os menus **Ferramentas** e **Complementos** não existiam.

## <a name="windows-powershell-tabs"></a>Guias do Windows PowerShell

Uma guia do Windows PowerShell é o ambiente em que um script do Windows PowerShell é executado. Você pode abrir novas guias do Windows PowerShell no ISE do Windows PowerShell para criar ambientes separados em seu computador local ou em computadores remotos. Você pode ter um máximo de oito guias do PowerShell abertas simultaneamente.

## <a name="toolbar"></a>Barra de ferramentas

Os seguintes botões estão localizados na barra de ferramentas.

|Botão|Função|
|----------|------------|
|**Novo**|Abre um novo script.|
|**Abrir**|Abre um arquivo ou um script existente.|
|**Salvar**|Salva um script ou um arquivo.|
|**Recortar**|Recorta o texto selecionado e o copia para a área de transferência.|
|**Copiar**|Copia o texto selecionado para a área de transferência.|
|**Colar**|Cola o conteúdo da área de transferência na posição do cursor.|
|**Limpar Painel de Saída**|Limpa todo o conteúdo no Painel de Saída.|
|**Desfazer**|Reverte a ação que acabou de ser executada.|
|**Refazer**|Realiza a ação que acabou de ser desfeita.|
|**Executar Script**|Executa um script.|
|**Executar seleção**|Executa uma parte selecionada de um script.|
|**Parar execução**|Interrompe um script que está em execução.|
|**Nova Guia do PowerShell Remota**|Cria uma nova Guia do PowerShell que estabelece uma sessão em um computador remoto. Uma caixa de diálogo é exibida e solicita que você insira os detalhes necessários para estabelecer a conexão remota.|
|**Inicia o PowerShell.exe**|Abre o Console do Windows PowerShell.|
|**Mostrar o Painel de Script Acima**|Move o Painel de Script para cima na exibição.|
|**Mostrar o Painel de Script à Direita**|Move o Painel de Script para a direita na exibição.|
|**Mostrar o Painel de Script Maximizado**|Maximiza o Painel de Script.|

## <a name="script-tab"></a>Guia de Script

Exibe o nome do script que você está editando. Você pode clicar em uma guia de script para selecionar o script que deseja editar.

Ao apontar para a guia do script, o caminho totalmente qualificado para o arquivo de script é exibido em uma dica de ferramenta.

## <a name="script-pane"></a>Painel de Script

Permite criar e executar scripts. Você pode abrir, editar e executar scripts existentes no Painel de Script.

## <a name="output-pane"></a>Painel de Saída

Exibe os resultados dos comandos e scripts executados por você. Você também pode copiar e limpar o conteúdo do Painel de Saída.

## <a name="command-pane"></a>Painel de Comando

Permite gravar comandos. Você pode executar um comando de uma ou várias linhas no Painel de Comando. Pressione Shift+Enter para inserir cada linha de comando de várias linhas e pressione Enter após a última linha para executá-lo. O prompt exibido na parte superior do Painel de Comando mostra o caminho para o diretório de trabalho atual.

## <a name="status-bar"></a>Barra de Status

Permite que você veja se os comandos e scripts que você executou foram concluídos. A barra de status localiza-se na parte mais inferior da tela. Partes selecionadas de mensagens de erro são exibidas na barra de status.

## <a name="text-size-slider"></a>Controle deslizante de tamanho de texto

Aumenta ou diminui o tamanho do texto na tela.

## <a name="help"></a>Ajuda

A Ajuda para o ISE do Windows PowerShell está disponível na Web na Biblioteca do TechNet. Você pode abrir a Ajuda clicando em **Ajuda do ISE do Windows PowerShell** no menu **Ajuda** ou pressionando a tecla F1 em qualquer lugar, exceto quando o cursor estiver em um nome de cmdlet no Painel de Script ou no Painel de Console. No menu **Ajuda**, você também pode executar o cmdlet Update-Help e exibir a Janela Comando que auxilia na construção de comandos, mostrando todos os parâmetros para um cmdlet e permitindo preencher os parâmetros em um formulário de fácil utilização.

## <a name="see-also"></a>Consulte Também

- [Apresentando o ISE do Windows PowerShell](../../core-powershell/ise/Introducing-the-Windows-PowerShell-ISE.md)
