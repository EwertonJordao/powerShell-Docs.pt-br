---
ms.date: 2017-06-05T00:00:00.000Z
keywords: PowerShell, cmdlet
title: "Usando variáveis para armazenar objetos"
ms.assetid: b1688d73-c173-491e-9ba6-6d0c1cc852de
ms.openlocfilehash: 067948d7c234fb70c7cf9966c9ae3e8df1f99757
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2017
---
# <a name="using-variables-to-store-objects"></a>Usando variáveis para armazenar objetos
O Windows PowerShell funciona com objetos. O Windows PowerShell permite criar variáveis (que são basicamente objetos nomeados) a fim de preservar a saída para uso futuro. Se você está acostumado a trabalhar com variáveis em outros shells, lembre-se de que variáveis do Windows PowerShell são objetos, não texto.

Variáveis sempre são especificadas com o caractere inicial $ e podem incluir qualquer caractere alfanumérico ou sublinhado em seus nomes.

### <a name="creating-a-variable"></a>Criando uma variável
Você pode criar uma variável digitando um nome de variável válido:

```
PS> $loc
PS>
```

Isso não retornará nenhum resultado porque **$loc** não tem um valor. Você pode criar uma variável e atribuir a ela um valor na mesma etapa. O Windows PowerShell criará a variável somente se ela não existir; caso contrário, ele atribuirá o valor especificado para a variável existente. Para armazenar seu local atual na variável **$loc**, digite:

```
$loc = Get-Location
```

Não há nenhuma saída exibida quando você digitar esse comando porque a saída é enviada para $loc. No Windows PowerShell, a saída exibida é um efeito colateral do fato de que os dados que não são direcionados sempre são enviados para a tela. Digitar $loc mostrará o local atual:

```
PS> $loc

Path
----
C:\temp
```

Você pode usar o **Get-Member** para exibir informações sobre o conteúdo de variáveis. Direcionar $loc para Get-Member mostrará que ele é um objeto **PathInfo**, bem como a saída de Get-Location:

```
PS> $loc | Get-Member -MemberType Property

   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   System.String Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {...
ProviderPath Property   System.String ProviderPath {get;}
```

### <a name="manipulating-variables"></a>Manipulação de variáveis
O Windows PowerShell fornece vários comandos para manipular variáveis. Você pode ver uma listagem completa em um formato legível digitando:

```
Get-Command -Noun Variable | Format-Table -Property Name,Definition -AutoSize -Wrap
```

Além de variáveis criadas na sessão atual do Windows PowerShell, há diversas variáveis definidas pelo sistema. Você pode usar o cmdlet **Remove-Variable** para limpar todas as variáveis que não são controladas pelo Windows PowerShell. Digite o seguinte comando a seguir para limpar todas as variáveis:

```
Remove-Variable -Name * -Force -ErrorAction SilentlyContinue
```

Isso produzirá o prompt de confirmação que você vê abaixo.

```
Confirm
Are you sure you want to perform this action?
Performing operation "Remove Variable" on Target "Name: Error".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):A
```

Se executar o cmdlet **Get-Variable**, você verá as variáveis restantes do Windows PowerShell. Como também há uma variável de unidade do Windows PowerShell, você também pode exibir todas as variáveis do Windows PowerShell digitando:

```
Get-ChildItem variable:
```

### <a name="using-cmdexe-variables"></a>Usando variáveis do Cmd.exe
Embora o Windows PowerShell não seja o Cmd.exe, ele é executado em um ambiente de shell de comando e pode usar as mesmas variáveis disponíveis em qualquer ambiente no Windows. Essas variáveis são expostas por meio de uma unidade chamada **env**:. Você pode exibir essas variáveis digitando:

```
Get-ChildItem env:
```

Embora os cmdlets de variável padrão não sejam projetados para trabalhar com variáveis **env:**, você ainda pode usá-las especificando o prefixo **env:**. Por exemplo, para ver o diretório raiz do sistema operacional, você pode usar a variável do shell de comando **%SystemRoot%** dentro do Windows PowerShell digitando:

```
PS> $env:SystemRoot
C:\WINDOWS
```

Você também pode criar e modificar variáveis de ambiente do Windows PowerShell. Variáveis de ambiente acessadas do Windows PowerShell estão em conformidade com as regras normais de variáveis de ambiente em outros lugares no Windows.
