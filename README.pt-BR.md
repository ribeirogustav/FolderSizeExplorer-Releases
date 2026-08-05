# Folder Size Explorer

[English](README.md) | **Português (Brasil)**

Folder Size Explorer é um aplicativo desktop proprietário para Windows x64 que combina navegação de arquivos com cálculo recursivo de tamanho de pastas, barra de favoritos no estilo Chrome e FTP/FTPS.

Este repositório é o canal oficial de distribuição pública. O código-fonte é privado e não é distribuído aqui.

<p align="center">
  <img src="assets/folder-size-explorer.webp" alt="Folder Size Explorer — visualização Detalhes, treemap e barra de favoritos" width="100%">
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

| Detalhes + treemap + barra de favoritos | Painel duplo |
| --- | --- |
| ![Modo Detalhes](assets/folder-size-explorer.webp) | ![Painel duplo](assets/dual-pane.webp) |

| Modo colunas | Grade |
| --- | --- |
| ![Modo colunas](assets/columns.webp) | ![Modo grade](assets/grid.webp) |

| Conexão FTP |
| --- |
| ![Conexão FTP](assets/ftp-connection.webp) |

## Recursos

- Cálculo assíncrono de tamanho de pastas
- Cache em memória e SQLite
- Visualizações Detalhes, Colunas, Grade e Painel duplo
- Mapa de tamanho (treemap)
- Abas, recentes e **barra de favoritos estilo Chrome** (pastas/grupos, ícones, overflow)
- Busca por nome na pasta e em subpastas
- Operações locais e drag-and-drop
- Exportação CSV/JSON e comparação de tamanho
- Interface em 21 idiomas
- **FTP/FTPS**: navegar, enviar, baixar e transferir local↔remoto  
  (modo Automático tenta FTPS e, se falhar, usa FTP)

## Novidades da 1.0.1

- Barra de favoritos estilo Chrome (sugestão de [u/testednation](https://www.reddit.com/user/testednation/))
- FTP/FTPS completo (não é mais só listagem)
- Segurança FTP Automática e janela de conexão mais clara
- Abertura mais segura: caminhos FTP/ausentes/lentos abrem em **Este Computador**

Veja o [CHANGELOG.md](CHANGELOG.md) para a lista completa.

## Segurança e privacidade

- Sem telemetria no executável
- Configurações, cache e perfis FTP ficam no perfil local do Windows
- Senhas FTP usam DPAPI do Windows quando “Lembrar senha” está ativo
- FTPS usa a validação de certificado padrão do Windows

Reporte vulnerabilidades em privado: `gustavo@grcx.com.br`.  
Veja [SECURITY.md](SECURITY.md) e [PRIVACY.md](PRIVACY.md).

## Suporte

- Suporte: `support@grcx.com.br`
- Privacidade / jurídico: `contact@grcx.com.br`
- Segurança: `gustavo@grcx.com.br`
- Site: <https://www.grcx.com.br/>
- Issues (não sensíveis): <https://github.com/ribeirogustav/FolderSizeExplorer-Releases/issues>

## Licença

Copyright © 2026 Gustavo Ribeiro de Carvalho, atuando sob a marca GRCX. Todos os direitos reservados.

Freeware proprietário: uso pessoal e empresarial interno permitidos. Redistribuição pública, mirrors, modificação e engenharia reversa não são autorizados sem permissão escrita.

Veja [LICENSE](LICENSE) e [EULA.md](EULA.md).
