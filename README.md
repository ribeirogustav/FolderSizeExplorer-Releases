# Folder Size Explorer

Folder Size Explorer é um aplicativo desktop proprietário para Windows x64 que combina navegação de arquivos com cálculo recursivo do tamanho de pastas, treemap, abas e múltiplos modos de visualização.

Este documento é destinado ao repositório público de releases. O código-fonte é privado e não é distribuído neste repositório.

## Status

A primeira release pública oficial ainda não foi publicada. Não baixe builds `OLD`, Debug ou executáveis obtidos em mirrors.

## Downloads oficiais

- GitHub Releases: <https://github.com/ribeirogustav/FolderSizeExplorer-Releases/releases>
- Site GRCX: <https://www.grcx.com.br/>

Cada release pública, inclusive pré-release, deve incluir um ZIP versionado, checksum SHA-256, assinatura Authenticode válida e documentação legal.

## Plataforma

- Windows 10/11 x64 como alvo declarado.
- Executável self-contained; não requer instalação separada do .NET.
- Execução como usuário atual, sem solicitação automática de administrador.

A compatibilidade por edição/build do Windows deve ser consultada nas notas da release correspondente.

## Principais recursos

- cálculo assíncrono de tamanho de pastas;
- cache local em memória e SQLite;
- visualizações Detalhes, Colunas, Grade e Painel duplo;
- treemap dos maiores itens visíveis;
- abas, favoritos e caminhos recentes;
- busca por nome na pasta atual e em subpastas;
- operações locais de arquivos e drag-and-drop;
- exportação CSV/JSON e comparação de tamanho;
- interface em 21 culturas; e
- navegação FTP/FTPS somente para listagem.

Consulte as notas da release para limitações e riscos corrigidos/pendentes.

## Segurança importante

Não será considerada oficial uma release pública sem os gates de segurança e integridade definidos pela GRCX.

Reporte vulnerabilidades em privado para `gustavo@grcx.com.br`. Não publique credenciais ou provas de conceito destrutivas em issues.

## Privacidade

A versão atual não implementa telemetria no executável. Configurações, histórico, cache e perfis FTP são armazenados no perfil local do Windows. Recursos de rede e provedores externos seguem as políticas dos respectivos serviços.

Consulte `PRIVACY.md` no pacote/repositório da release.

## Suporte

- Suporte: `support@grcx.com.br`
- Privacidade e assuntos legais: `contact@grcx.com.br`
- Segurança: `gustavo@grcx.com.br`
- Doações: `billing@grcx.com.br`

Issues públicas para bugs não sensíveis ficarão disponíveis depois da inicialização deste repositório.

## Licença

Copyright © 2026 Gustavo Ribeiro de Carvalho, atuando sob a marca GRCX. Todos os direitos reservados.

O aplicativo é freeware proprietário. A licença permite uso pessoal e empresarial interno e a implantação dentro da mesma organização. Redistribuição pública ou a terceiros, mirrors, modificação e engenharia reversa não são autorizados sem permissão escrita.

Consulte `LICENSE` e `EULA.md` no pacote/repositório da release.

Doações são opcionais e não ampliam direitos de licença.
