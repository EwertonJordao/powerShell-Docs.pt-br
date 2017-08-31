---
ms.date: 2017-06-05T00:00:00.000Z
keywords: PowerShell, cmdlet
title: Ajuda da linha de comando do PowerShell.exe
ms.assetid: 1ab7b93b-6785-42c6-a1c9-35ff686a958f
ms.openlocfilehash: 4a14223dd024d967810a90dec10e416e4e35d6a2
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2017
---
# <a name="powershellexe-command-line-help"></a>Ajuda da linha de comando do PowerShell.exe
Inicia uma sessão do Windows PowerShell. Você pode usar o PowerShell.exe para iniciar uma sessão do Windows PowerShell na linha de comando de outra ferramenta, como Cmd.exe, ou usá-lo na linha de comando do Windows PowerShell para iniciar uma nova sessão. Use os parâmetros para personalizar a sessão.

## <a name="syntax"></a>Sintaxe

```
PowerShell[.exe]
       [-EncodedCommand <Base64EncodedCommand>]
       [-ExecutionPolicy <ExecutionPolicy>]
       [-InputFormat {Text | XML}] 
       [-Mta]
       [-NoExit]
       [-NoLogo]
       [-NonInteractive] 
       [-NoProfile] 
       [-OutputFormat {Text | XML}] 
       [-PSConsoleFile <FilePath> | -Version <Windows PowerShell version>]
       [-Sta]
       [-WindowStyle <style>]
       [-File <FilePath> [<Args>]]
       [-Command { - | <script-block> [-args <arg-array>]
                     | <string> [<CommandParameters>] } ]

PowerShell[.exe] -Help | -? | /?
```

## <a name="parameters"></a>Parâmetros

### <a name="-encodedcommand-base64encodedcommand"></a>-EncodedCommand <Base64EncodedCommand>
Aceita uma versão de cadeia de caracteres com codificação de base 64 de um comando. Use esse parâmetro para enviar comandos ao Windows PowerShell que exigem aspas complexas ou chaves.

### <a name="-executionpolicy-executionpolicy"></a>-ExecutionPolicy <ExecutionPolicy>
Define a política de execução padrão para a sessão atual e o salva-a na variável de ambiente $env:PSExecutionPolicyPreference. Esse parâmetro não altera a política de execução do Windows PowerShell que está definida no Registro. Para saber mais sobre as políticas de execução do Windows PowerShell, incluindo uma lista de valores válidos, confira about_Execution_Policies (http://go.microsoft.com/fwlink/?LinkID=135170).

### <a name="-file-filepath-parameters"></a>-File <FilePath> \[<Parameters>]
Executa o script especificado no escopo local ("dot-sourced") para que as funções e variáveis que o script criar estejam disponíveis na sessão atual. Insira o caminho do arquivo de script e quaisquer parâmetros. **File** deve ser o último parâmetro no comando, pois todos os caracteres digitados após nome do parâmetro **File** são interpretados como o caminho do arquivo de script seguido pelos parâmetros do script e seus valores.

Você pode incluir os parâmetros de um script e os valores de parâmetro no valor do parâmetro **File**. Por exemplo: `-File .\Get-Script.ps1 -Domain Central` Observe que os parâmetros passados para o script são passados como cadeias de caracteres literais (após a interpretação do shell atual).
Por exemplo, se você estiver no cmd.exe e quiser para passar um valor de variável de ambiente, use a sintaxe do cmd.exe: `powershell -File .\test.ps1 -Sample %windir%` Se você usar a sintaxe do PowerShell, neste exemplo, o script receberá o literal "$env:windir" e não o valor dessa variável de ambiente: `powershell -File .\test.ps1 -Sample $env:windir`

Normalmente, os parâmetros de opção de um script são incluídos ou omitidos. Por exemplo, o comando a seguir usa o parâmetro **All** do arquivo de script Get-Script.ps1: `-File .\Get-Script.ps1 -All`

### <a name="-inputformat-text--xml"></a>\-InputFormat {Texto | XML}
Descreve o formato dos dados enviados ao Windows PowerShell. Os valores válidos são "Text" (cadeias de caracteres de texto) ou "XML" (formato CLIXML serializado).

### <a name="-mta"></a>-Mta
Inicia o Windows PowerShell usando um multi-threaded apartment. Este parâmetro é introduzido no Windows PowerShell 3.0. No Windows PowerShell 3.0, o STA (Single-Threaded Apartment) é o padrão. No Windows PowerShell 2.0, o MTA (Multi-Threaded Apartment) é o padrão.

### <a name="-noexit"></a>-NoExit
Não é encerrado depois de executar comandos de inicialização.

### <a name="-nologo"></a>-NoLogo
Oculta a faixa de direitos autorais na inicialização.

### <a name="-noninteractive"></a>-NonInteractive
Não exibe um prompt interativo para o usuário.

### <a name="-noprofile"></a>-NoProfile
Não carrega o perfil do Windows PowerShell.

### <a name="-outputformat-text--xml"></a>-OutputFormat {Text | XML}
Determina como a saída do Windows PowerShell é formatada. Os valores válidos são "Text" (cadeias de caracteres de texto) ou "XML" (formato CLIXML serializado).

### <a name="-psconsolefile-filepath"></a>-PSConsoleFile <FilePath>
Carrega o arquivo do console do Windows PowerShell especificado. Insira o caminho e o nome do arquivo de console. Para criar um arquivo de console, use o cmdlet [Export-Console](https://technet.microsoft.com/en-us/library/4bab1c02-9e61-4aaf-9957-11d1934ef4ef) do Windows PowerShell.

### <a name="-sta"></a>-Sta
Inicia o Windows PowerShell usando um single-threaded apartment. No Windows PowerShell 3.0, o STA (Single-Threaded Apartment) é o padrão. No Windows PowerShell 2.0, o MTA (Multi-Threaded Apartment) é o padrão.

### <a name="-version-windows-powershell-version"></a>-Version <Windows PowerShell Version>
Inicia a versão especificada do Windows PowerShell. A versão que você especificar deve estar instalada no sistema. Se o Windows PowerShell 3.0 estiver instalado no computador, os valores válidos serão "3.0" e "2.0". O valor padrão é “3.0”.

Se o Windows PowerShell 3.0 não estiver instalado, o único valor válido será "2.0". Outros valores são ignorados.

Para obter mais informações, consulte "Instalar o Windows PowerShell" na [Introdução ao Fluxo de Trabalho do Windows PowerShell [MSDN ANTIGO]](https://technet.microsoft.com/en-us/library/69555d95-b481-43e1-86e7-b46d68b3e2dd).

### <a name="-windowstyle-window-style"></a>-WindowStyle <Window style>
Define o estilo da janela da sessão. Os valores válidos são Normal, Minimized, Maximized e Hidden.

### <a name="-command"></a>-Command
Executa os comandos especificados (e quaisquer parâmetros) da maneira como eles foram digitados no prompt de comando do Windows PowerShell e, em seguida, encerra a sessão, a menos que o parâmetro NoExit seja especificado.
Basicamente, qualquer texto após `-Command` é enviado como uma única linha de comando para o PowerShell (que é diferente de como `-File` manipula os parâmetros enviados para um script).

O valor do Comando pode ser "-", uma cadeia de caracteres. ou um bloco de script. Se o valor do comando for "-", o texto do comando será lido da entrada padrão.

Blocos de script devem ser colocados entre chaves ({}). Você pode especificar um bloco de script apenas quando o PowerShell.exe no Windows PowerShell estiver em execução. Os resultados do script são retornados para o shell pai como objetos XML desserializados, não objetos vivos.

Se o valor do comando for uma cadeia de caracteres, **Command** deverá ser o último parâmetro no comando, pois qualquer caractere digitado depois do comando será interpretado como os argumentos do comando.

Para gravar uma cadeia de caracteres que executa um comando do Windows PowerShell, use o formato:

```
"& {<command>}"
```

no qual as aspas indicam uma cadeia de caracteres e o operador de invocação (&) faz com que o comando seja executado.

### <a name="-help---"></a>-Help, -?, /?
Mostra esta mensagem. Se você estiver digitando um comando do PowerShell.exe no Windows PowerShell, adicione um hífen (-) ao início dos parâmetros do comando, não uma barra (/). Você pode usar um hífen ou uma barra "/" no Cmd.exe.

> [!NOTE]
> Observação de solução de problemas: no Windows PowerShell 2.0, a inicialização de alguns programas no console do Windows PowerShell falha com um LastExitCode 0xc0000142.

## <a name="examples"></a>EXEMPLOS

```
PowerShell -PSConsoleFile sqlsnapin.psc1

PowerShell -Version 2.0 -NoLogo -InputFormat text -OutputFormat XML

PowerShell -Command "Get-EventLog -LogName security"

# in an existing PowerShell session that understands the curly braces mean a script block
PowerShell -Command {Get-EventLog -LogName security}

PowerShell -Command "& {Get-EventLog -LogName security}"

# To use the -EncodedCommand parameter:
$command = "dir 'c:\program files' "
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
powershell.exe -encodedCommand $encodedCommand
```
