---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: PowerShell, cmdlet, galeria
ms.date: 2016-10-14
contributor: manikb
title: script psget_find
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6c526d1074f61154d03b92b6bf6f599976f5936
ms.openlocfilehash: 5651989acde9d47a7a07fac9284aebae84f28174

---

# Find-Script

Localiza os arquivos de script do PowerShell de uma galeria online que correspondem aos critérios especificados.

## Descrição

Find-Script descobre os arquivos de script de repositórios registrados que correspondem aos critérios especificados.
Para cada script encontrado, Find-Script retorna um objeto PSRepositoryItemInfo que pode, opcionalmente, ser redirecionado para Install-Script para instalar os scripts.
O cmdlet Find-Script permite descobrir os arquivos de script com critérios de pesquisa diferentes, como nome, marca, filtro, nome do comando, intervalo de versão, a versão exata, todas as versões, incluindo suas dependências e de repositórios específicos ou de todos os repositórios.

- Find-Script pode filtrar com base no conteúdo do script com os parâmetros -Command e -Includes.
- Find-Script pode filtrar segundo os parâmetros de versão: MinimumVersion, MaximumVersion, RequiredVersion, AllVersions.
  - Esses parâmetros são mutuamente exclusivos, exceto MinmimumVersion e MaximumVersion.
  - Esses parâmetros de versão são permitidos apenas com o nome exclusivo do script, sem curingas.
  - Se o parâmetro RequiredVersion não for especificado, Find-Script retorna a versão mais recente do script que for igual ou maior que a versão mínima especificada ou a versão mais recente do script se nenhuma versão mínima tiver sido especificada. 
  - Se o parâmetro RequiredVersion for especificado, Find-Script retornará apenas a versão do script que corresponde exatamente à versão especificada.
- Find-Script pode filtrar os metadados do script com o parâmetro -Tag.
- Find-Script pode filtrar a linguagem de pesquisa específica do repositório com o parâmetro -Filter.
- Find-Script pode filtrar scripts de todos ou de alguns dos repositórios registrados.

**OBSERVAÇÃO:** PSRepository registrado deve ter um ScriptSourceLocation válido. Você pode usar Set-PSRepository para definir o valor de ScriptSourceLocation.

## Sintaxe do cmdlet

```powershell
Get-Command -Name Find-Script -Module PowerShellGet -Syntax
```

## Referência da ajuda online sobre cmdlets

[Find-Script](http://go.microsoft.com/fwlink/?LinkId=619785)

## Comandos de exemplo

```powershell
# Find a script from the registered repository with ScriptSourceLocation
Find-Script Connect-AzureVM

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.0        Connect-AzureVM                     PSGallery            This runbook sets up a connection to an Azure vi...

# Find multiple scripts
Find-Script -Name Connect-AzureVM, Show-Tree, Connect-O365

# Find scripts with wildcards in -Name
Find-Script -Name *Azure*

# Find all versions of a script
Find-Script -Name Connect-O365 -AllVersions

# Find a script with -MinimumVersion. 
# With MinimumVersion we can find a script whose version is greate than or equal to the specified MinimumVersion value.
Find-Script Connect-O365 -MinimumVersion 1.4

# Find a script with MaximumVersion
Find-Script -Name Connect-O365 -MaximumVersion 1.6.2

# Find a script with both MinimumVersion and MaximumVersion range.
Find-Script -Name Connect-O365 -MinimumVersion 1.1 -MaximumVersion 1.6.2

# Find a script with exact version
Find-Script -Name Connect-O365 -RequiredVersion 1.5.7

# Find a script from the specified repository
Find-Script -Name Fabrikam-ServerScript -Repository MyLocalRepo

# Find available scripts from all registered repositories
Find-Script

# Find available scripts from few registered repositories
Find-Script -Repository PSGallery, PrivatePSGallery

# Find a script along with its dependent modules and scripts
Find-Script -Name Connect-AzureVM -IncludeDependencies

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.0        Connect-AzureVM                     PSGallery            This runbook sets up a connection to an Azure vi...
1.4.0      Azure                               PSGallery            Microsoft Azure PowerShell - Service Management
1.1.2      Azure.Storage                       PSGallery            Microsoft Azure PowerShell - Storage service cmd...
1.0.8      AzureRM.profile                     PSGallery            Microsoft Azure PowerShell - Profile credential ...

# Find all scripts with workflows
Find-Script -Includes Workflow

# Find all scripts with functions
Find-Script -Includes Function

# Find scripts with specific commands
Find-Script -Command Log-Message
Find-Script -Command Log-Message, Show-Tree -Includes Function
Find-Script -Command Connect-AzureVM -Includes Workflow

# Find scripts with -Filter based search. -Filter searches in description and names
Find-Script -Filter Windows
Find-Script -Filter Azure

# Find all scripts with tags O365 or Nano
Find-Script -Tag O365, Nano

# Properties of Find-Script returned object
Find-Script Show-Tree | Format-List * -Force
Name                       : Show-Tree
Version                    : 1.0.0
Type                       : Script
Description                : Script to show the layout of PowerShell namespaces (Trees) using ASCII
Author                     : Jeffrey Snover
CompanyName                : jsnover
Copyright                  : (C) Microsoft Corporation. All rights reserved.
PublishedDate              : 2/15/2016 10:15:35 PM
InstalledDate              :
UpdatedDate                :
LicenseUri                 :
ProjectUri                 :
IconUri                    :
Tags                       : {Nano, PSScript}
Includes                   : {Function, RoleCapability, Command, DscResource...}
PowerShellGetFormatVersion :
ReleaseNotes               :
Dependencies               : {}
RepositorySourceLocation   : https://www.powershellgallery.com/api/v2/
Repository                 : PSGallery
PackageManagementProvider  : NuGet
AdditionalMetadata         : {versionDownloadCount, ItemType, copyright, PackageManagementProvider...}


# Includes property on PSRepositoryItemInfo object
$t = Find-Script -Includes Workflow -Repository INT -Name Fabrikam-ClientScript
$t.Includes

Name                           Value
----                           -----
Function                       {Test-FunctionFromScript_Fabrikam-ClientScript}
RoleCapability                 {}
Command                        {Test-FunctionFromScript_Fabrikam-ClientScript, Test-WorkflowFromScript_Fabrikam-Clie...
DscResource                    {}
Workflow                       {Test-WorkflowFromScript_Fabrikam-ClientScript}
Cmdlet                         {}


```




<!--HONumber=Oct16_HO2-->

