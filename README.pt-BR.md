# Folder Size Explorer

[English](README.md) | **Português (Brasil)**

O Folder Size Explorer é um aplicativo desktop proprietário para Windows x64 que combina navegação e gerenciamento de arquivos com análise recursiva do tamanho de pastas.

Este repositório é o canal público oficial de distribuição. O código-fonte é privado e não é distribuído aqui.

<p align="center">
  <img src="assets/folder-size-explorer.webp" alt="Folder Size Explorer exibindo a visualização em colunas e o mapa de tamanhos" width="100%">
</p>

## Download

- [Baixe a versão mais recente](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/releases/latest)
- Versão atual: `1.0.0`
- Arquivo: `FolderSizeExplorer-1.0.0-win-x64.exe`
- Plataforma: Windows 10/11 x64

O executável portable é self-contained e não exige uma instalação separada do .NET.

## Instalação

1. Baixe `FolderSizeExplorer-1.0.0-win-x64.exe` na página oficial da release.
2. Opcionalmente, confira o checksum SHA-256 com o valor publicado junto da release.
3. Mova o executável para uma pasta local e execute-o.

O aplicativo é executado como o usuário atual e não solicita automaticamente privilégios de administrador. O executável atual não possui assinatura digital, portanto o Windows SmartScreen pode exibir um aviso.

## Recursos

- Cálculo assíncrono e recursivo do tamanho de pastas
- Cache de tamanhos em memória e SQLite
- Visualizações Detalhes, Colunas, Grade e Painel duplo
- Mapa visual dos maiores itens visíveis
- Abas, favoritos e locais recentes
- Busca local e recursiva por nome
- Operações locais de arquivos e drag-and-drop
- Exportação CSV/JSON e comparação de tamanhos
- Interface disponível em 21 idiomas e culturas
- Navegação FTP/FTPS para listagens remotas

O suporte a FTP está limitado a navegação e listagem. Download, upload, renomeação e exclusão remotos ainda não estão disponíveis.

## Privacidade e segurança

O aplicativo não inclui telemetria. Configurações, histórico, cache e perfis FTP são armazenados no perfil local do usuário do Windows. Consulte [PRIVACY.md](PRIVACY.md) para mais detalhes.

Reporte vulnerabilidades de segurança em privado para `gustavo@grcx.com.br`. Não publique credenciais nem provas de conceito destrutivas em issues públicas. Consulte [SECURITY.md](SECURITY.md).

## Suporte

- Bugs públicos não sensíveis: [GitHub Issues](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/issues)
- Suporte: `support@grcx.com.br`
- Privacidade e assuntos legais: `contact@grcx.com.br`
- Segurança: `gustavo@grcx.com.br`
- Site: <https://www.grcx.com.br/>

Consulte [SUPPORT.md](SUPPORT.md) para conhecer a política de suporte.

## Licença

Copyright (c) 2026 Gustavo Ribeiro de Carvalho, atuando sob a marca GRCX. Todos os direitos reservados.

O Folder Size Explorer é um freeware proprietário. O uso pessoal e empresarial interno é permitido. Redistribuição pública ou a terceiros, mirrors, modificação e engenharia reversa não são autorizados sem permissão por escrito.

Consulte [LICENSE](LICENSE) e [EULA.md](EULA.md) para conhecer os termos completos.
