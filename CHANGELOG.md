# Changelog

Todas as mudanças relevantes do Folder Size Explorer devem ser registradas neste arquivo.

O formato segue os princípios de [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/) e o projeto pretende usar versionamento semântico.

## [Não publicado]

### Adicionado

- Licença proprietária de freeware e EULA.
- Declaração formal de titularidade e autoria.
- Políticas de privacidade, suporte, segurança e métricas sem telemetria.
- Estratégia de distribuição por repositório privado de fonte, GitHub Releases público e site GRCX.
- Documentação técnica e contexto factual de produto.

### Segurança

- Documentados bloqueadores conhecidos para a primeira release oficial: validação FTPS, FTP simples, dependência SQLite vulnerável, reparse points em transferências, rename, CSV formula injection e assinatura de código.

## [1.0.0] - 2026-07-30

### Implementado no código auditado

- Navegação local, Este Computador e unidades de rede/removíveis.
- Cálculo assíncrono e cache SQLite de tamanhos de pastas.
- Modos Detalhes, Colunas, Grade e Painel duplo.
- Treemap, abas, favoritos, recentes e busca profunda.
- Operações locais, drag-and-drop e exportação CSV/JSON.
- Comparação de tamanho de dois caminhos.
- Navegação FTP/FTPS somente para listagem.
- Temas, 21 culturas e suporte a gamepad XInput.
- Apoio opcional por canais externos e identificadores de pagamento.

### Limitações relevantes

- O executável portable para Windows x64 não possui assinatura digital e pode acionar um aviso do Windows SmartScreen.
- FTP/FTPS está limitado a navegação e listagem; operações remotas ainda não estão disponíveis.
- Consulte `SECURITY.md` e `DISTRIBUTION.md` para os riscos e requisitos de distribuição conhecidos.
