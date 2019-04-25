---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: fcf2adf67f36edb534df3e2a849459fb20e1c2de
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085336"
---
# <a name="extract-and-parse-structured-objects-out-of-string"></a>Extrair e analisar objetos estruturados fora da cadeia de caracteres

Isso também introduz algumas funcionalidades adicionais ao cmdlet `ConvertFrom-String`:

- Por padrão, remove a propriedade de texto de extensão. É possível incluí-la com o parâmetro -IncludeExtent.

- Muitas correções de bug do algoritmo de aprendizado de acordo com os comentários da comunidade e do MVP.

- Um novo parâmetro -UpdateTemplate para salvar os resultados do algoritmo de aprendizado em um comentário no arquivo de modelo. Isso faz com que o processo de aprendizado (a etapa mais lenta) seja de custo único. A execução de Convert-String com um modelo que contém o algoritmo de aprendizado codificado agora é quase instantânea.

## <a name="extract-and-parse-structured-objects-out-of-string-content"></a>Extrair e analisar objetos estruturados fora do conteúdo da cadeia de caracteres

Em colaboração com o [Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F), um novo cmdlet `ConvertFrom-String` foi adicionado.

Esse cmdlet dá suporte a dois modos: análise delimitada básica e análise orientada por exemplo gerada automaticamente.

A análise delimitada, por padrão, divide a entrada no espaço em branco e atribui nomes de propriedade aos grupos resultantes. É possível personalizar o delimitador:

```powershell
"Hello World" | ConvertFrom-String | Format-Table -Auto
```

```output
P1     P2
--     --
Hello  World
```

O cmdlet também dá suporte à análise orientada por exemplo gerada automaticamente com base no trabalho de pesquisa [FlashExtract](https://www.microsoft.com/en-us/research/publication/flashextract-framework-data-extraction-examples/?from=http%3A%2F%2Fresearch.microsoft.com%2Fen-us%2Fum%2Fpeople%2Fsumitg%2Fflashextract.html) no [Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F).

Para começar, considere um catálogo de endereços baseado em texto:

```
    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA

    Thomas Hardy

    Seattle, WA

    Christina Berglund

    Redmond, WA

    Hanna Moos

    Puyallup, WA
```

Faça uma cópia de alguns exemplos em um arquivo, que você usará como o modelo:

```
    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA
```

Coloque chaves em torno dos dados que deseja extrair, nomeando-os. Como a propriedade **Name** (e suas outras propriedades associadas) pode aparecer várias vezes, use um asterisco (\*) para indicar que isso resultará em vários registros (em vez de extrair várias propriedades em um registro):

```
    {Name\*:Ana Trujillo}

    {City:Redmond}, {State:WA}

    {Name\*:Antonio Moreno}

    {City:Renton}, {State:WA}
```

Desse conjunto de exemplos, `ConvertFrom-String` agora pode extrair automaticamente a saída com base no objeto de arquivos de entrada com uma estrutura semelhante.

```powershell
Get-Content .\addresses.output.txt | ConvertFrom-String -TemplateFile .\addresses.template.txt | Format-Table -Auto
```

```output
ExtentText                     Name               City     State
----------                     ----               ----     -----
Ana Trujillo...                Ana Trujillo       Redmond  WA
Antonio Moreno...              Antonio Moreno     Renton   WA
Thomas Hardy...                Thomas Hardy       Seattle  WA
Christina Berglund...          Christina Berglund Redmond  WA
Hanna Moos...                  Hanna Moos         Puyallup WA
```

A fim de realizar a manipulação de dados adicional no texto extraído, a propriedade **ExtentText** captura o texto não processado do qual o registro foi extraído. Para fornecer comentários sobre este recurso ou compartilhar conteúdo para o qual você está com dificuldades para escrever exemplos, envie um email para <psdmfb@microsoft.com>.