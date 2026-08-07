<p align="center">
  <img src="assets/foldersizeexplorer.svg" width="300" alt="Folder Size Explorer" />
</p>

<p align="center">
  <strong>Veja suas pastas. Saiba o tamanho delas.</strong>
</p>

<p align="center">
  <img alt="versão" src="https://img.shields.io/badge/version-1.0.1-11b3ad?style=for-the-badge&labelColor=111" />
  <img alt="licença" src="https://img.shields.io/badge/license-Freeware-545b61?style=for-the-badge&labelColor=111" />
  <img alt="plataforma" src="https://img.shields.io/badge/Windows%2010%20%7C%2011-555?style=for-the-badge&labelColor=111&label=platform" />
</p>

<p align="center">
  <a href="README.md">English</a> · <strong>Português (Brasil)</strong>
</p>

<p>
  Folder Size Explorer é um gerenciador de arquivos gratuito e portátil para Windows 10 e Windows 11 que mostra o tamanho real das pastas diretamente enquanto você navega. Ele combina análise recursiva de tamanho com gerenciamento de arquivos, navegação em colunas no estilo Finder, treemap visual, abas, favoritos, vários modos de visualização e FTP/FTPS.
</p>

<p>
  Eu criei o Folder Size Explorer originalmente para uso próprio porque queria que a análise recursiva do tamanho das pastas fizesse parte natural da navegação diária, e não fosse uma ferramenta separada. A ideia é ter um gerenciador leve em que descobrir o que está ocupando espaço seja parte do próprio fluxo de navegação.
</p>

<p>
  Folder Size Explorer é <strong>freeware proprietário</strong>: o uso pessoal e empresarial interno é gratuito, sem versão Pro, recursos bloqueados, assinatura ou telemetria. Este repositório é o canal oficial de distribuição pública; o código-fonte é privado.
</p>

<p align="center">
  <a href="#download">Download</a>
  ·
  <a href="#recursos">Recursos</a>
  ·
  <a href="#capturas-de-tela">Capturas de tela</a>
  ·
  <a href="#suporte">Suporte</a>
  ·
  <a href="#licença">Licença</a>
</p>

<p align="center">
  <a href="https://www.buymeacoffee.com/ribeirogustav"><img src="https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&emoji=&slug=ribeirogustav&button_colour=FFDD00&font_colour=000000&font_family=Lato&outline_colour=000000&coffee_colour=ffffff" alt="Buy me a coffee" height="36" /></a>
</p>

<p align="center">
  <img src="assets/folder-size-explorer.webp" alt="Folder Size Explorer — visualização Detalhes, treemap e barra de favoritos" width="100%"><br>
  <em>Folder Size Explorer no Windows 11.</em>
</p>

## Download

- [Baixar a release mais recente](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/releases/latest)
- Versão atual: `1.0.1`
- Arquivo: `FolderSizeExplorer-1.0.1-win-x64.exe`
- Plataforma: Windows 10/11 x64

O executável portable é self-contained e não exige instalação separada do .NET.

## Instalação

1. Baixe `FolderSizeExplorer-1.0.1-win-x64.exe` na página oficial de releases.
2. Opcionalmente confira o SHA-256 com o arquivo publicado na release.
3. Coloque o EXE em uma pasta local e execute.

O aplicativo roda como o usuário atual e não pede administrador automaticamente. O executável atual **não tem assinatura digital**; o Windows SmartScreen pode exibir um aviso.

## Capturas de tela

| Detalhes + treemap + barra de favoritos | Pasta de favoritos aberta |
| --- | --- |
| ![Modo Detalhes](assets/folder-size-explorer.webp) | ![Pasta de favoritos](assets/dual-pane.webp) |

| Interface em árabe (RTL) | Conexão FTP |
| --- | --- |
| ![Interface RTL em árabe](assets/columns.webp) | ![Conexão FTP](assets/grid.webp) |

| Configuração de idioma |
| --- |
| ![Lista de idiomas](assets/ftp-connection.webp) |

## Recursos

- Cálculo assíncrono de tamanho de pastas
- Cache em memória e SQLite
- Modos de visualização: Detalhes, Colunas (estilo Miller/Finder), Grade e Painel duplo
- Mapa de tamanho (treemap)
- Abas, recentes e **barra de favoritos estilo Chrome** (pastas/grupos, ícones, overflow)
- Busca por nome na pasta e em subpastas
- Operações locais e drag-and-drop
- Exportação CSV/JSON e comparação de tamanho
- Interface em 21 idiomas
- Atalhos de navegação com gamepad XInput
- **FTP/FTPS**: navegar, enviar, baixar e transferir local↔remoto  
  (modo Automático tenta FTPS e, se falhar, usa FTP)

## Novidades da 1.0.1

- Barra de favoritos estilo Chrome (sugestão de [u/testednation](https://www.reddit.com/user/testednation/))
- FTP/FTPS completo (não é mais só listagem)
- Segurança FTP Automática e janela de conexão mais clara
- Abertura mais segura: caminhos FTP/ausentes/lentos abrem em **Este Computador**

Veja o [CHANGELOG.md](CHANGELOG.md) para a lista completa.

## Arquitetura

A interface WPF conversa com um coordenador central que usa serviços dedicados para o sistema de arquivos, cálculo de tamanho de pastas, transferências, FTP/FTPS opcional e configurações locais. Os resultados de tamanho podem ser armazenados em cache SQLite no seu PC.

```mermaid
flowchart TD
    User[Mouse, teclado, arrastar e soltar ou gamepad] --> UI[Interface WPF]
    UI --> Core[Coordenador do app]
    Core --> FS[Serviço de arquivos]
    Core --> Size[Cálculo de tamanho]
    Core --> Transfer[Transferências]
    Core --> FTP[Serviço FTP/FTPS]
    Core --> Settings[Configurações, tema, ícones]
    FS --> Windows[Arquivos e unidades do Windows]
    Size --> Cache[Cache local de tamanhos]
    Cache --> SQLite[(SQLite no seu PC)]
    FTP --> Remote[Servidor FTP/FTPS que você configura]
    Settings --> LocalData[Preferências locais em JSON]
```

## Segurança e privacidade

- Sem telemetria no executável
- Configurações, cache e perfis FTP ficam no perfil local do Windows
- Senhas FTP usam DPAPI do Windows quando “Lembrar senha” está ativo
- FTPS usa a validação de certificado padrão do Windows

Reporte vulnerabilidades em privado: `gustavo@grcx.com.br`.  
Veja [SECURITY.md](docs/SECURITY.md) e [PRIVACY.md](docs/PRIVACY.md).

## Suporte

| Assunto | Canal |
| --- | --- |
| Suporte | `support@grcx.com.br` |
| Bugs não sensíveis | <https://github.com/ribeirogustav/FolderSizeExplorer-Releases/issues> |
| Privacidade / jurídico | `contact@grcx.com.br` |
| Segurança | `gustavo@grcx.com.br` |
| Doações | `billing@grcx.com.br` |
| Site | <https://www.grcx.com.br/> |
| Apoio externo | <https://buymeacoffee.com/ribeirogustav> |

Consulte também [SUPPORT.md](docs/SUPPORT.md).

## Licença

Copyright © 2026 Gustavo Ribeiro de Carvalho, atuando sob a marca GRCX. Todos os direitos reservados.

Freeware proprietário: uso pessoal e empresarial interno permitidos. Redistribuição pública, mirrors, modificação e engenharia reversa não são autorizados sem permissão escrita.

Veja [LICENSE](LICENSE) e [EULA.md](docs/EULA.md).
