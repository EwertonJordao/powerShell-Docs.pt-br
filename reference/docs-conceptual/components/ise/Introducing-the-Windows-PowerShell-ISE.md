---
ms.date: 08/14/2018
keywords: powershell, cmdlet
title: 'Apresentando o ISE do Windows PowerShell '
ms.openlocfilehash: 729c8535dbcfcd2c51070b8beac5d328375f36ae
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057389"
---
# <a name="the-windows-powershell-ise"></a>O ISE do Windows PowerShell

O ISE (Ambiente de Script Integrado) do Windows PowerShell é um aplicativo host do Windows PowerShell. No ISE, você pode executar comandos e escrever, testar e depurar scripts em uma interface gráfica de usuário única baseada no Windows. A ISE fornece edição em várias linhas, preenchimento com tabulação, coloração de sintaxe, execução seletiva, ajuda contextual e suporte para idiomas da direita para esquerda. Itens de menu e atalhos de teclado são mapeados para executar muitas das mesmas tarefas que você executaria no console do Windows PowerShell. Por exemplo, quando você depura um script no ISE, é possível clicar com botão direito do mouse em uma linha de código no painel de edição para definir um ponto de interrupção.

## <a name="support"></a>Suporte

O ISE foi introduzido pela primeira vez com o Windows PowerShell V2 e foi reformulado com o PowerShell V3. Há suporte para o ISE em todas as versões compatíveis do Windows PowerShell até e incluindo a versão do Windows PowerShell v 5.1. No entanto, o ISE está no modo de manutenção e nenhum recurso novo deve ser adicionado.
Além disso, não há suporte para o ISE com o PowerShell v6 e posterior. Os usuários que desejam uma ferramenta gráfica para gerenciar os scripts do PowerShell devem usar o [Visual Studio Code](https://code.visualstudio.com/).

## <a name="key-features"></a>Principais recursos

Novos recursos no ISE do Windows PowerShell:

- Edição em várias linhas: para inserir uma linha em branco abaixo da linha atual no painel de comando, pressione SHIFT+ENTER.
- Execução seletiva: Para executar parte de um script, selecione o texto que você deseja executar e clique no botão **Executar Script**. Ou pressione F5.
- Ajuda contextual: Digite **Invoke-Item** e pressione F1. O arquivo de Ajuda é aberto no artigo para o cmdlet **Invoke-Item**.

O ISE do Windows PowerShell permite personalizar alguns aspectos de sua aparência. Ele também tem seu próprio script de perfil do Windows PowerShell.

## <a name="to-start-the-windows-powershell-ise"></a>Para iniciar o ISE do Windows PowerShell

Clique em **Iniciar**, selecione **Windows PowerShell** e clique em **ISE do Windows PowerShell**.
Como alternativa, você pode digitar `powershell_ise.exe` em qualquer shell de comando ou na caixa Executar.

## <a name="to-get-help-in-the-windows-powershell-ise"></a>Para obter ajuda no ISE do Windows PowerShell

No menu **Ajuda**, clique em **Ajuda do Windows PowerShell**. Ou pressione F1. O arquivo aberto descreve o ISE do Windows PowerShell e o Windows PowerShell, incluindo toda a ajuda disponível para no cmdlet Get-Help.
