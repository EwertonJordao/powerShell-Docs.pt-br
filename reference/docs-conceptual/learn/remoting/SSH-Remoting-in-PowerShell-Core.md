---
title: Comunicação remota do PowerShell por SSH
description: Comunicação remota no PowerShell Core usando SSH
ms.date: 08/14/2018
ms.openlocfilehash: 1d7bcb69c7e784bf745cb5c2633106ea53f6226a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086384"
---
# <a name="powershell-remoting-over-ssh"></a><span data-ttu-id="46809-103">Comunicação remota do PowerShell por SSH</span><span class="sxs-lookup"><span data-stu-id="46809-103">PowerShell Remoting Over SSH</span></span>

## <a name="overview"></a><span data-ttu-id="46809-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="46809-104">Overview</span></span>

<span data-ttu-id="46809-105">Normalmente, a comunicação remota do PowerShell usa WinRM para negociação de conexão e transporte de dados.</span><span class="sxs-lookup"><span data-stu-id="46809-105">PowerShell remoting normally uses WinRM for connection negotiation and data transport.</span></span> <span data-ttu-id="46809-106">Agora, o SSH está disponível para plataformas Linux e Windows, e permite a verdadeira comunicação remota multiplataforma do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46809-106">SSH is now available for Linux and Windows platforms and allows true multiplatform PowerShell remoting.</span></span>

<span data-ttu-id="46809-107">O WinRM fornece um modelo de hospedagem robusto para sessões remotas do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46809-107">WinRM provides a robust hosting model for PowerShell remote sessions.</span></span> <span data-ttu-id="46809-108">No momento, a comunicação remota baseada em SSH não oferece suporte à configuração de ponto de extremidade remoto e JEA (Just Enough Administration).</span><span class="sxs-lookup"><span data-stu-id="46809-108">SSH-based remoting doesn't currently support remote endpoint configuration and JEA (Just Enough Administration).</span></span>

<span data-ttu-id="46809-109">A comunicação remota do SSH permite que você faça a comunicação remota de sessão básica do PowerShell entre máquinas Windows e Linux.</span><span class="sxs-lookup"><span data-stu-id="46809-109">SSH remoting lets you do basic PowerShell session remoting between Windows and Linux machines.</span></span> <span data-ttu-id="46809-110">A comunicação remota do SSH cria um processo de hospedagem do PowerShell no computador de destino como um subsistema de SSH.</span><span class="sxs-lookup"><span data-stu-id="46809-110">SSH Remoting creates a PowerShell host process on the target machine as an SSH subsystem.</span></span>
<span data-ttu-id="46809-111">Eventualmente, implementaremos um modelo de hospedagem geral, semelhante ao WinRM, para dar suporte à configuração de ponto de extremidade e JEA.</span><span class="sxs-lookup"><span data-stu-id="46809-111">Eventually we'll implement a general hosting model, similar to WinRM, to support endpoint configuration and JEA.</span></span>

<span data-ttu-id="46809-112">Agora, os cmdlets `New-PSSession`, `Enter-PSSession` e `Invoke-Command` têm um novo parâmetro definido para dar suporte a essa nova conexão de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="46809-112">The `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets now have a new parameter set to support this new remoting connection.</span></span>

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="46809-113">Para criar uma sessão remota, especifique o computador de destino com o parâmetro `HostName` e forneça o nome de usuário com `UserName`.</span><span class="sxs-lookup"><span data-stu-id="46809-113">To create a remote session, you specify the target machine with the `HostName` parameter and provide the user name with `UserName`.</span></span> <span data-ttu-id="46809-114">Ao executar os cmdlets interativamente, você receberá uma solicitação de senha.</span><span class="sxs-lookup"><span data-stu-id="46809-114">When running the cmdlets interactively, you're prompted for a password.</span></span> <span data-ttu-id="46809-115">Você também pode usar a autenticação de chave SSH usando um arquivo de chave privada com o parâmetro `KeyFilePath`.</span><span class="sxs-lookup"><span data-stu-id="46809-115">You can also, use SSH key authentication using a private key file with the `KeyFilePath` parameter.</span></span>

## <a name="general-setup-information"></a><span data-ttu-id="46809-116">Informações gerais de configuração</span><span class="sxs-lookup"><span data-stu-id="46809-116">General setup information</span></span>

<span data-ttu-id="46809-117">O SSH deve ser instalado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="46809-117">SSH must be installed on all machines.</span></span> <span data-ttu-id="46809-118">Instale o cliente SSH (`ssh.exe`) e o servidor (`sshd.exe`) para que possa fazer comunicação remota entre os computadores.</span><span class="sxs-lookup"><span data-stu-id="46809-118">Install both the SSH client (`ssh.exe`) and server (`sshd.exe`) so that you can remote to and from the machines.</span></span> <span data-ttu-id="46809-119">Agora, o OpenSSH para Windows está disponível no build 1809 do Windows 10 e no Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="46809-119">OpenSSH for Windows is now availabe in Windows 10 build 1809 and Windows Server 2019.</span></span> <span data-ttu-id="46809-120">Para obter mais informações, confira [OpenSSH para Windows](/windows-server/administration/openssh/openssh_overview).</span><span class="sxs-lookup"><span data-stu-id="46809-120">For more information, see [OpenSSH for Windows](/windows-server/administration/openssh/openssh_overview).</span></span> <span data-ttu-id="46809-121">No Linux, instale o SSH (incluindo sshd server) apropriado à sua plataforma.</span><span class="sxs-lookup"><span data-stu-id="46809-121">For Linux, install SSH (including sshd server) appropriate to your platform.</span></span> <span data-ttu-id="46809-122">Você também precisará instalar o PowerShell Core no GitHub para obter o recurso de comunicação remota do SSH.</span><span class="sxs-lookup"><span data-stu-id="46809-122">You also need to install PowerShell Core from GitHub to get the SSH remoting feature.</span></span> <span data-ttu-id="46809-123">O servidor SSH deve ser configurado para criar um subsistema de SSH para hospedar um processo do PowerShell no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="46809-123">The SSH server must be configured to create an SSH subsystem to host a PowerShell process on the remote machine.</span></span> <span data-ttu-id="46809-124">Você também deve configurar autenticação baseada em chave ou habilitação por senha.</span><span class="sxs-lookup"><span data-stu-id="46809-124">You also must configure enable password or key-based authentication.</span></span>

## <a name="set-up-on-windows-machine"></a><span data-ttu-id="46809-125">Configuração no computador Windows</span><span class="sxs-lookup"><span data-stu-id="46809-125">Set up on Windows Machine</span></span>

1. <span data-ttu-id="46809-126">Instale a versão mais recente do [PowerShell Core para Windows](../../install/installing-powershell-core-on-windows.md#msi)</span><span class="sxs-lookup"><span data-stu-id="46809-126">Install the latest version of [PowerShell Core for Windows](../../install/installing-powershell-core-on-windows.md#msi)</span></span>

   - <span data-ttu-id="46809-127">Você saberá se ele tem o suporte de comunicação remota do SSH examinando os conjuntos de parâmetros para `New-PSSession`</span><span class="sxs-lookup"><span data-stu-id="46809-127">You can tell if it has the SSH remoting support by looking at the parameter sets for `New-PSSession`</span></span>

   ```powershell
   Get-Command New-PSSession -syntax
   ```

   ```output
   New-PSSession [-HostName] <string[]> [-Name <string[]>] [-UserName <string>] [-KeyFilePath <string>] [-SSHTransport] [<CommonParameters>]
   ```

2. <span data-ttu-id="46809-128">Instale o OpenSSH Win32 mais recente.</span><span class="sxs-lookup"><span data-stu-id="46809-128">Install the latest Win32 OpenSSH.</span></span> <span data-ttu-id="46809-129">Para obter instruções de instalação, confira [Instalação do OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse).</span><span class="sxs-lookup"><span data-stu-id="46809-129">For installation instructions, see [Installation of OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse).</span></span>
3. <span data-ttu-id="46809-130">Edite o arquivo `sshd_config` localizado em `$env:ProgramData\ssh`.</span><span class="sxs-lookup"><span data-stu-id="46809-130">Edit the `sshd_config` file located at `$env:ProgramData\ssh`.</span></span>

   - <span data-ttu-id="46809-131">Verifique se a autenticação de senha está habilitada</span><span class="sxs-lookup"><span data-stu-id="46809-131">Make sure password authentication is enabled</span></span>

     ```
     PasswordAuthentication yes
     ```

     ```
     Subsystem    powershell c:/program files/powershell/6/pwsh.exe -sshs -NoLogo -NoProfile
     ```

     > [!NOTE]
     > <span data-ttu-id="46809-132">Há um bug no OpenSSH para Windows que impede que os espaços trabalhem em caminhos executáveis do subsistema.</span><span class="sxs-lookup"><span data-stu-id="46809-132">There is a bug in OpenSSH for Windows that prevents spaces from working in subsystem executable paths.</span></span> <span data-ttu-id="46809-133">Saiba mais neste [tópico do GitHub](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span><span class="sxs-lookup"><span data-stu-id="46809-133">For more information, see [this GitHub issue](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span></span>

     <span data-ttu-id="46809-134">Uma solução é criar um symlink para o diretório de instalação do PowerShell que não contenha espaços:</span><span class="sxs-lookup"><span data-stu-id="46809-134">One solution is to create a symlink to the PowerShell installation directory that doesn't have spaces:</span></span>

     ```powershell
     mklink /D c:\pwsh "C:\Program Files\PowerShell\6"
     ```

     <span data-ttu-id="46809-135">e, em seguida, inseri-lo no subsistema:</span><span class="sxs-lookup"><span data-stu-id="46809-135">and then enter it in the subsystem:</span></span>

     ```
     Subsystem    powershell c:\pwsh\pwsh.exe -sshs -NoLogo -NoProfile
     ```

   - <span data-ttu-id="46809-136">Como alternativa, habilite a autenticação de chave</span><span class="sxs-lookup"><span data-stu-id="46809-136">Optionally enable key authentication</span></span>

     ```
     PubkeyAuthentication yes
     ```

4. <span data-ttu-id="46809-137">Reinicie o serviço sshd</span><span class="sxs-lookup"><span data-stu-id="46809-137">Restart the sshd service</span></span>

   ```powershell
   Restart-Service sshd
   ```

5. <span data-ttu-id="46809-138">Adicione o caminho no qual o OpenSSH está instalado à sua variável de ambiente Path.</span><span class="sxs-lookup"><span data-stu-id="46809-138">Add the path where OpenSSH is installed to your Path environment variable.</span></span> <span data-ttu-id="46809-139">Por exemplo, `C:\Program Files\OpenSSH\`.</span><span class="sxs-lookup"><span data-stu-id="46809-139">For example, `C:\Program Files\OpenSSH\`.</span></span> <span data-ttu-id="46809-140">Essa entrada permite que ssh.exe seja localizado.</span><span class="sxs-lookup"><span data-stu-id="46809-140">This entry allows for the ssh.exe to be found.</span></span>

## <a name="set-up-on-linux-ubuntu-1404-machine"></a><span data-ttu-id="46809-141">Configuração no computador com Linux (Ubuntu 14.04)</span><span class="sxs-lookup"><span data-stu-id="46809-141">Set up on Linux (Ubuntu 14.04) Machine</span></span>

1. <span data-ttu-id="46809-142">Instale o build mais recente do [PowerShell Core para Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1404) do GitHub</span><span class="sxs-lookup"><span data-stu-id="46809-142">Install the latest [PowerShell Core for Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1404) build from GitHub</span></span>
2. <span data-ttu-id="46809-143">Instale o [Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html) conforme necessário</span><span class="sxs-lookup"><span data-stu-id="46809-143">Install [Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html) as needed</span></span>

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

3. <span data-ttu-id="46809-144">Edite o arquivo sshd_config no local /etc/ssh</span><span class="sxs-lookup"><span data-stu-id="46809-144">Edit the sshd_config file at location /etc/ssh</span></span>

   - <span data-ttu-id="46809-145">Verifique se a autenticação de senha está habilitada</span><span class="sxs-lookup"><span data-stu-id="46809-145">Make sure password authentication is enabled</span></span>

   ```
   PasswordAuthentication yes
   ```

   - <span data-ttu-id="46809-146">Adicione uma entrada do subsistema PowerShell</span><span class="sxs-lookup"><span data-stu-id="46809-146">Add a PowerShell subsystem entry</span></span>

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo -NoProfile
   ```

   - <span data-ttu-id="46809-147">Como alternativa, habilite a autenticação de chave</span><span class="sxs-lookup"><span data-stu-id="46809-147">Optionally enable key authentication</span></span>

   ```
   PubkeyAuthentication yes
   ```

4. <span data-ttu-id="46809-148">Reinicie o serviço sshd</span><span class="sxs-lookup"><span data-stu-id="46809-148">Restart the sshd service</span></span>

   ```bash
   sudo service sshd restart
   ```

## <a name="set-up-on-macos-machine"></a><span data-ttu-id="46809-149">Configuração no computador MacOS</span><span class="sxs-lookup"><span data-stu-id="46809-149">Set up on MacOS Machine</span></span>

1. <span data-ttu-id="46809-150">Instale o build mais recente do [PowerShell Core para MacOS](../../install/installing-powershell-core-on-macos.md)</span><span class="sxs-lookup"><span data-stu-id="46809-150">Install the latest [PowerShell Core for MacOS](../../install/installing-powershell-core-on-macos.md) build</span></span>

   - <span data-ttu-id="46809-151">Verifique se a comunicação remota do SSH está habilitada, seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="46809-151">Make sure SSH Remoting is enabled by following these steps:</span></span>
     - <span data-ttu-id="46809-152">Abra `System Preferences`</span><span class="sxs-lookup"><span data-stu-id="46809-152">Open `System Preferences`</span></span>
     - <span data-ttu-id="46809-153">Clique em `Sharing`</span><span class="sxs-lookup"><span data-stu-id="46809-153">Click on `Sharing`</span></span>
     - <span data-ttu-id="46809-154">Verifique `Remote Login` – deve dizer `Remote Login: On`</span><span class="sxs-lookup"><span data-stu-id="46809-154">Check `Remote Login` - Should say `Remote Login: On`</span></span>
     - <span data-ttu-id="46809-155">Permita o acesso a usuários apropriados</span><span class="sxs-lookup"><span data-stu-id="46809-155">Allow access to appropriate users</span></span>

2. <span data-ttu-id="46809-156">Edite o arquivo `sshd_config` no local `/private/etc/ssh/sshd_config`</span><span class="sxs-lookup"><span data-stu-id="46809-156">Edit the `sshd_config` file at location `/private/etc/ssh/sshd_config`</span></span>

   - <span data-ttu-id="46809-157">Usar seu editor favorito ou</span><span class="sxs-lookup"><span data-stu-id="46809-157">Use your favorite editor or</span></span>

     ```bash
     sudo nano /private/etc/ssh/sshd_config
     ```

   - <span data-ttu-id="46809-158">Verifique se a autenticação de senha está habilitada</span><span class="sxs-lookup"><span data-stu-id="46809-158">Make sure password authentication is enabled</span></span>

     ```
     PasswordAuthentication yes
     ```

   - <span data-ttu-id="46809-159">Adicione uma entrada do subsistema PowerShell</span><span class="sxs-lookup"><span data-stu-id="46809-159">Add a PowerShell subsystem entry</span></span>

     ```
     Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo -NoProfile
     ```

   - <span data-ttu-id="46809-160">Como alternativa, habilite a autenticação de chave</span><span class="sxs-lookup"><span data-stu-id="46809-160">Optionally enable key authentication</span></span>

     ```
     PubkeyAuthentication yes
     ```

3. <span data-ttu-id="46809-161">Reinicie o serviço sshd</span><span class="sxs-lookup"><span data-stu-id="46809-161">Restart the sshd service</span></span>

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="authentication"></a><span data-ttu-id="46809-162">Autenticação</span><span class="sxs-lookup"><span data-stu-id="46809-162">Authentication</span></span>

<span data-ttu-id="46809-163">A comunicação remota do PowerShell por SSH depende da troca de autenticação entre o cliente do SSH e o serviço de SSH; ela própria não implementa nenhum esquema de autenticação.</span><span class="sxs-lookup"><span data-stu-id="46809-163">PowerShell remoting over SSH relies on the authentication exchange between the SSH client and SSH service and does not implement any authentication schemes itself.</span></span>
<span data-ttu-id="46809-164">Isso significa que os esquemas de autenticação configurada, incluindo a autenticação multifator, são manipulados por SSH e são independentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46809-164">This means that any configured authentication schemes including multi-factor authentication is handled by SSH and independent of PowerShell.</span></span>
<span data-ttu-id="46809-165">Por exemplo, você pode configurar o serviço SSH para exigir autenticação de chave pública, bem como uma senha única para aumentar a segurança.</span><span class="sxs-lookup"><span data-stu-id="46809-165">For example, you can configure the SSH service to require public key authentication as well as a one-time password for added security.</span></span>
<span data-ttu-id="46809-166">A configuração da autenticação multifator está fora do escopo desta documentação.</span><span class="sxs-lookup"><span data-stu-id="46809-166">Configuration of multi-factor authentication is outside the scope of this documentation.</span></span>
<span data-ttu-id="46809-167">Consulte a documentação para o SSH sobre como configurar a autenticação multifator corretamente e validar seu trabalho fora do PowerShell antes de tentar usá-la com a comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46809-167">Refer to documentation for SSH on how to correctly configure multi-factor authentication and validate it works outside of PowerShell before attempting to use it with PowerShell remoting.</span></span>

## <a name="powershell-remoting-example"></a><span data-ttu-id="46809-168">Exemplo de comunicação remota do PowerShell</span><span class="sxs-lookup"><span data-stu-id="46809-168">PowerShell Remoting Example</span></span>

<span data-ttu-id="46809-169">A maneira mais fácil de testar a comunicação remota é experimentá-la em um único computador.</span><span class="sxs-lookup"><span data-stu-id="46809-169">The easiest way to test remoting is to try it on a single machine.</span></span> <span data-ttu-id="46809-170">Neste exemplo, criamos uma sessão remota para o mesmo computador com Linux.</span><span class="sxs-lookup"><span data-stu-id="46809-170">In this example, we create a remote session back to the same Linux machine.</span></span> <span data-ttu-id="46809-171">Estamos usando cmdlets do PowerShell de forma interativa para que possamos ver avisos do SSH para verificar o computador host, bem como solicitar uma senha.</span><span class="sxs-lookup"><span data-stu-id="46809-171">We are using PowerShell cmdlets interactively so we see prompts from SSH asking to verify the host computer and prompting for a password.</span></span> <span data-ttu-id="46809-172">Você pode fazer a mesma coisa em um computador com Windows para garantir ao funcionamento da comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="46809-172">You can do the same thing on a Windows machine to ensure remoting is working.</span></span> <span data-ttu-id="46809-173">Em seguida, realize a comunicação remota entre máquinas alterando o nome do host.</span><span class="sxs-lookup"><span data-stu-id="46809-173">Then remote between machines by changing the host name.</span></span>

```powershell
#
# Linux to Linux
#
$session = New-PSSession -HostName UbuntuVM1 -UserName TestUser
```

```output
The authenticity of host 'UbuntuVM1 (9.129.17.107)' cannot be established.
ECDSA key fingerprint is SHA256:2kCbnhT2dUE6WCGgVJ8Hyfu1z2wE4lifaJXLO7QJy0Y.
Are you sure you want to continue connecting (yes/no)?
TestUser@UbuntuVM1s password:
```

```powershell
$session
```

```output
 Id Name   ComputerName    ComputerType    State    ConfigurationName     Availability
 -- ----   ------------    ------------    -----    -----------------     ------------
  1 SSH1   UbuntuVM1       RemoteMachine   Opened   DefaultShell             Available
```

```powershell
Enter-PSSession $session
```

```output
[UbuntuVM1]: PS /home/TestUser> uname -a
Linux TestUser-UbuntuVM1 4.2.0-42-generic 49~14.04.1-Ubuntu SMP Wed Jun 29 20:22:11 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

[UbuntuVM1]: PS /home/TestUser> Exit-PSSession
```

```powershell
Invoke-Command $session -ScriptBlock { Get-Process powershell }
```

```output
Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName                    PSComputerName
-------  ------    -----      -----     ------     --  -- -----------                    --------------
      0       0        0         19       3.23  10635 635 powershell                     UbuntuVM1
      0       0        0         21       4.92  11033 017 powershell                     UbuntuVM1
      0       0        0         20       3.07  11076 076 powershell                     UbuntuVM1
```

```powershell
#
# Linux to Windows
#
Enter-PSSession -HostName WinVM1 -UserName PTestName
```

```output
PTestName@WinVM1s password:
```

```powershell
[WinVM1]: PS C:\Users\PTestName\Documents> cmd /c ver
```

```output
Microsoft Windows [Version 10.0.10586]
```

```powershell
#
# Windows to Windows
#
C:\Users\PSUser\Documents>pwsh.exe
```

```output
PowerShell
Copyright (c) Microsoft Corporation. All rights reserved.
```

```powershell
$session = New-PSSession -HostName WinVM2 -UserName PSRemoteUser
```

```output
The authenticity of host 'WinVM2 (10.13.37.3)' can't be established.
ECDSA key fingerprint is SHA256:kSU6slAROyQVMEynVIXAdxSiZpwDBigpAF/TXjjWjmw.
Are you sure you want to continue connecting (yes/no)?
Warning: Permanently added 'WinVM2,10.13.37.3' (ECDSA) to the list of known hosts.
PSRemoteUser@WinVM2's password:
```

```powershell
$session
```

```output
 Id Name            ComputerName    ComputerType    State         ConfigurationName     Availability
 -- ----            ------------    ------------    -----         -----------------     ------------
  1 SSH1            WinVM2          RemoteMachine   Opened        DefaultShell             Available
```

```powershell
Enter-PSSession -Session $session
```

```output
[WinVM2]: PS C:\Users\PSRemoteUser\Documents> $PSVersionTable

Name                           Value
----                           -----
PSEdition                      Core
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
SerializationVersion           1.1.0.1
BuildVersion                   3.0.0.0
CLRVersion
PSVersion                      6.0.0-alpha
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
GitCommitId                    v6.0.0-alpha.17


[WinVM2]: PS C:\Users\PSRemoteUser\Documents>
```

### <a name="known-issues"></a><span data-ttu-id="46809-174">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="46809-174">Known Issues</span></span>

<span data-ttu-id="46809-175">O comando sudo não funciona em uma sessão remota para computador com Linux.</span><span class="sxs-lookup"><span data-stu-id="46809-175">The sudo command doesn't work in remote session to Linux machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="46809-176">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46809-176">See Also</span></span>

[<span data-ttu-id="46809-177">PowerShell Core para Windows</span><span class="sxs-lookup"><span data-stu-id="46809-177">PowerShell Core for Windows</span></span>](../../install/installing-powershell-core-on-windows.md#msi)

[<span data-ttu-id="46809-178">PowerShell Core para Linux</span><span class="sxs-lookup"><span data-stu-id="46809-178">PowerShell Core for Linux</span></span>](../../install/installing-powershell-core-on-linux.md#ubuntu-1404)

[<span data-ttu-id="46809-179">PowerShell Core para MacOS</span><span class="sxs-lookup"><span data-stu-id="46809-179">PowerShell Core for MacOS</span></span>](../../install/installing-powershell-core-on-macos.md)

[<span data-ttu-id="46809-180">OpenSSH para Windows</span><span class="sxs-lookup"><span data-stu-id="46809-180">OpenSSH for Windows</span></span>](/windows-server/administration/openssh/openssh_overview)

[<span data-ttu-id="46809-181">Ubuntu SSH</span><span class="sxs-lookup"><span data-stu-id="46809-181">Ubuntu SSH</span></span>](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
