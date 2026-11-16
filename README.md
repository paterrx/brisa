
<div align="center">
  <img src="src/Brisa/Assets/Brisa.png" width="112" alt="Brisa">
  
  <h1>Brisa VPN</h1>
  
  <p><strong>O Discord passa pelo WireGuard e você tem tela de novo.</strong></p>
  
  <p>
    <a href="https://github.com/paterrx/brisa/releases"><img src="https://img.shields.io/github/v/release/paterrx/brisa?style=flat-square&label=vers%C3%A3o" alt="versão"></a>
    <a href="LICENSE"><img src="https://img.shields.io/github/license/paterrx/brisa?style=flat-square&label=licen%C3%A7a" alt="licença"></a>
    <a href="#requisitos"><img src="https://img.shields.io/badge/plataforma-Windows%20x64-blue?style=flat-square" alt="plataforma"></a>
    <a href="docs/development.md"><img src="https://img.shields.io/badge/feito%20com-.NET%2010-512BD4?style=flat-square" alt="feito com"></a>
  </p>
  
  [Baixar](https://github.com/paterrx/brisa/releases) · [Instalar](#instalar) · [Recursos](#recursos) · [Uso](#uso) · [Requisitos](#requisitos) · [Documentação](#documentação) · [Licença](#licença) · [English](README.en.md)
</div>

## Comece aqui (2 minutos)

Para quem nunca usou. Siga na ordem.

<p align="center">
  <a href="https://github.com/paterrx/brisa/releases/latest/download/Brisa-win-Setup.exe"><img src="https://img.shields.io/badge/%E2%AC%87%20Baixar%20o%20Brisa-Windows-2ea44f?style=for-the-badge" alt="Baixar o Brisa" height="48"></a>
</p>

<p align="center"><strong><a href="https://github.com/paterrx/brisa/releases/latest/download/Brisa-win-Setup.exe">Baixar o Brisa</a></strong></p>

1. Crie uma conta grátis da Proton em <https://account.protonvpn.com/signup?plan=free>. Guarde o e-mail e a senha.
2. Clique em **Baixar o Brisa** e abra o arquivo. Se aparecer a tela azul **"O Windows protegeu o computador"**, clique em **Mais informações** e depois em **Executar assim mesmo**. Esse aviso aparece porque o app é gratuito e não tem assinatura paga.
3. Abra o menu Iniciar, procure **Brisa**, clique com o botão direito e escolha **Executar como administrador**.
4. No Brisa, preencha **Usuário da Proton** e **Senha da Proton** e clique em **Entrar**. Se aparecer **Verifique sua conta**, conclua a verificação.
5. Saia de qualquer chamada e clique em **Conectar**. Na primeira vez abre o instalador do WireSock: avance, aceite e clique em **Sim** nos avisos do Windows. O Discord fecha e abre sozinho. Pronto.

**Para desligar:** clique em **Desconectar**. O X só esconde o app perto do relógio.<br>
**Só o Discord passa pela VPN.** O resto do PC fica normal.<br>
**Deu erro?** Me manda um print.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://i.imgur.com/8YCDiqr.png" />
    <img src="https://i.imgur.com/8YCDiqr.png" alt="Website do Brisa https://insxnsive.github.io/brisa/ explicando a lógica do tunelamento dívido." width="460" />
  </picture>
</p>

## Instalar

Baixe o **`Brisa-win-Setup.exe`** em [Releases](https://github.com/paterrx/brisa/releases).

O instalador ainda não tem assinatura digital, então o SmartScreen pode avisar sobre editor desconhecido. Se o arquivo veio das Releases deste repositório, clique em **Mais informações → Executar assim mesmo**.

O Brisa se instala por usuário, sem precisar de administrador; os instaladores do WebView2 e do WireSock que ele abrir podem pedir. Nada é instalado às escondidas.

Prefere um script que confere o download antes? No Windows PowerShell (não no Prompt de Comando):

```powershell
irm https://raw.githubusercontent.com/paterrx/brisa/brisa/scripts/install.ps1 | iex
```

Ele confere a assinatura da Microsoft no WebView2 e o SHA-256 do instalador do Brisa antes de rodar qualquer um dos dois. O script fixado em um commit, e o que cada verificação garante ou não: [verificações de instalação](docs/install.md).

## Recursos

- Só o Discord entra no túnel. Navegador, jogos e o resto seguem pela rota normal.
- Entre com a sua conta Proton, ou importe um `.conf` que você já tem.
- Fechar a janela mantém o Brisa e a conexão na bandeja.
- As atualizações são baixadas em segundo plano e instaladas quando você sai do Brisa.

## Uso

1. Abra o Brisa pelo menu Iniciar. Para conectar é preciso ser administrador; para só abrir o app, não.
2. Entre na sua conta Proton, ou importe o seu perfil em Configurações → Avançado.
3. Escolha a rota se quiser, e clique em Conectar.

Conectar e desconectar fecham e reabrem o Discord, em qualquer versão. Saia de qualquer chamada antes; ao desconectar, o Brisa reabre o Discord na rota normal.

Se o WireSock não estiver instalado, o Brisa abre o instalador oficial na primeira conexão e segue com a conexão em seguida. Mais em [configuração](docs/setup.md).

## Requisitos

- Windows x64, feito para o Windows 11.
- Permissão de administrador para conectar ou desconectar.
- [WireSock Secure Connect SDK](https://wiresock.net/wiresock-sdk), baixado na primeira conexão se faltar.
- [WebView2 Runtime](https://developer.microsoft.com/microsoft-edge/webview2/) para a página de verificação da Proton.
- Uma conta Proton ou o seu próprio `.conf` do WireGuard.
- Nenhum outro túnel do WireSock ou do GoLiveBypass ativo. O Brisa nunca assume o túnel de outro app.

## Documentação

| | |
| --- | --- |
| [Verificações de instalação](docs/install.md) | Instalação fixada em um commit, verificação de hash |
| [Configuração](docs/setup.md) | Requisitos, instalador, versão portátil, primeira conexão, [janela e bandeja](docs/setup.md#window-and-tray), dados salvos |
| [Desenvolvimento](docs/development.md) | Compilar, testar, empacotar, branch do macOS |
| [Verificação](docs/verification.md) | O que foi testado e como |
| [Privacidade](docs/privacy.md) | O que o Brisa guarda e o que ele nunca envia |
| [Publicação de versões](docs/releasing.md) | Versões, tags e feed de atualização |
| [Avisos de terceiros](THIRD-PARTY-NOTICES.md) | Licenças de tudo que vem dentro |

## Contribuir

Bugs e sugestões vão nas [Issues](https://github.com/paterrx/brisa/issues). Nunca publique senhas, códigos de verificação, arquivos de sessão ou perfis de VPN. O log gerado em Avançado → Gerar log pode ser compartilhado: nomes de conta, caminhos e endereços são removidos antes de o log ser escrito.

## Licença

[GPL-3.0-or-later](LICENSE), sem garantia. O Brisa é um fork nativo do [GoLiveBypass](https://github.com/bezumiya/GoLiveBypass). A interface Electron e o plugin foram removidos, e os avisos de direitos autorais originais foram mantidos. A ferramenta que gera os perfis da Proton vem do [hatemosphere/protonvpn-wg-confgen](https://github.com/hatemosphere/protonvpn-wg-confgen).

O Brisa não tem vínculo com Discord, Proton ou WireSock.
