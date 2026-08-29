# Folder Size Explorer 1.0.3

## English

Release date: 2026-08-29

Version 1.0.3 expands preview support and improves language presentation, file organization, and session persistence.

### Highlights

- Preview text, configuration, markup, and source-code files in a selectable, read-only viewer.
- Text reads are bounded to 256 KB or 5,000 lines, detect common encodings, reject binary content, and read only a prefix over FTP.
- Modern video previews open the original file directly by default. Classic mode uses silent 10-second H.264 proxies at 360p, 540p, or 720p; Settings can enable the same lightweight preparation in Modern mode.
- Video proxies are cached locally up to 128 MB and expire after seven days. Unsupported codecs use a static Windows thumbnail.
- WebP images now preview locally, and SVG artwork with explicit dimensions and a `viewBox` fills and aligns correctly in the bottom-right preview.
- Full-width saved windows restore correctly on monitors with negative fractional coordinates.
- Text previews fill the available Classic preview pane while remaining compact and floating in Modern mode.
- Controller help fades after 10 seconds, Escape dismisses Modern previews until the next explicit file click, language flags are truly circular, and Dark/Light choices show moon/sun icons.
- The language selector now uses circular SVG flags, with paired flags for English, Spanish, Arabic, and Bengali.
- Urdu uses the bundled Noto Nastaliq Urdu font and includes corrected interface coverage.
- Window placement and Details column order and widths persist between sessions.
- Multi-select file-type filters and persistent type grouping work across Details, Grid, Columns, and Dual views.

### Download

- Portable executable: `FolderSizeExplorer-1.0.3-win-x64.exe`
- SHA-256: `FolderSizeExplorer-1.0.3-win-x64.exe.sha256`
- Package: `FolderSizeExplorer-1.0.3-win-x64.zip`
- Package SHA-256: `FolderSizeExplorer-1.0.3-win-x64.zip.sha256`
- Platform: Windows 10/11 x64
- Runtime: self-contained; no separate .NET installation is required

**Executable SHA-256**

```text
f42557fe84444fdd1e6db295e250184e8c8b290c1352d7d07941fde16e0d2d3d  FolderSizeExplorer-1.0.3-win-x64.exe
```

Verify the ZIP with the published `FolderSizeExplorer-1.0.3-win-x64.zip.sha256` sidecar before extracting it.

### Update

Close the previous version, extract the new package to a local folder, and replace the earlier executable. Settings and cache stored in the Windows user profile are preserved.

### Privacy and security

- Text, document, image, and media previews are processed locally.
- Video proxies do not contain audio and are kept in a bounded local cache.
- No FFmpeg or external media service is used; codec support depends on Windows Media Foundation.
- FTP/FTPS connection security and credential protection are unchanged.
- The executable is not digitally signed. Windows SmartScreen may display a warning.

### Validation

- Release and portable single-file builds completed successfully.
- A functional media test produced a silent `640×358`, 10-second proxy from an `854×480` source.
- All 299 automated tests pass.
- Restored NuGet packages report no known vulnerabilities.
- Clean Windows environment and applicable FTP/FTPS validation were confirmed by the release owner.

### Resources

- [Changelog](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/CHANGELOG.md)
- [Privacy](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/PRIVACY.md)
- [Support](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SUPPORT.md)
- [Security](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SECURITY.md)
- [License](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/LICENSE)

---

## Português (Brasil)

Data da release: 2026-08-29

A versão 1.0.3 amplia o suporte a pré-visualizações e melhora a apresentação dos idiomas, a organização dos arquivos e a persistência da sessão.

### Destaques

- Pré-visualize arquivos de texto, configuração, marcação e código-fonte em um visor selecionável e somente leitura.
- A leitura de texto é limitada a 256 KB ou 5.000 linhas, detecta encodings comuns, rejeita conteúdo binário e lê apenas um prefixo via FTP.
- No modo Modern, o vídeo original abre diretamente por padrão. O modo Classic usa proxies H.264 sem áudio, com 10 segundos em 360p, 540p ou 720p; uma opção nas Configurações ativa a mesma preparação leve no Modern.
- Os proxies de vídeo usam um cache local limitado a 128 MB e expiram após sete dias. Codecs não suportados usam uma miniatura estática do Windows.
- Imagens WebP agora são pré-visualizadas localmente, e SVGs com dimensões explícitas e `viewBox` preenchem e se alinham corretamente no preview inferior direito.
- Janelas salvas ocupando toda a largura são restauradas corretamente em monitores com coordenadas fracionárias negativas.
- Pré-visualizações de texto preenchem o painel disponível no modo Classic e permanecem compactas e flutuantes no Modern.
- A ajuda do controle desaparece em fade após 10 segundos, Esc fecha previews Modern até o próximo clique explícito, as bandeiras ficam realmente circulares e as opções Escuro/Claro exibem ícones de lua/sol.
- O seletor de idioma agora usa bandeiras SVG circulares, incluindo pares para inglês, espanhol, árabe e bengali.
- O urdu usa a fonte Noto Nastaliq Urdu incorporada e recebeu correções de cobertura da interface.
- Posição da janela e ordem/largura das colunas em Detalhes persistem entre sessões.
- Filtro com seleção múltipla e agrupamento persistente por tipo funcionam em Detalhes, Grade, Colunas e Painel duplo.

### Download

- Executável portable: `FolderSizeExplorer-1.0.3-win-x64.exe`
- SHA-256: `FolderSizeExplorer-1.0.3-win-x64.exe.sha256`
- Pacote: `FolderSizeExplorer-1.0.3-win-x64.zip`
- SHA-256 do pacote: `FolderSizeExplorer-1.0.3-win-x64.zip.sha256`
- Plataforma: Windows 10/11 x64
- Runtime: self-contained; não é necessário instalar o .NET separadamente

**SHA-256 do executável**

```text
f42557fe84444fdd1e6db295e250184e8c8b290c1352d7d07941fde16e0d2d3d  FolderSizeExplorer-1.0.3-win-x64.exe
```

Confira o ZIP com o arquivo `FolderSizeExplorer-1.0.3-win-x64.zip.sha256` publicado antes de extraí-lo.

### Atualização

Feche a versão anterior, extraia o novo pacote em uma pasta local e substitua o executável anterior. Configurações e cache armazenados no perfil do usuário Windows são preservados.

### Privacidade e segurança

- Pré-visualizações de texto, documentos, imagens e mídia são processadas localmente.
- Proxies de vídeo não contêm áudio e permanecem em um cache local limitado.
- FFmpeg e serviços externos de mídia não são usados; o suporte a codecs depende do Windows Media Foundation.
- A segurança das conexões FTP/FTPS e a proteção das credenciais não mudaram.
- O executável não possui assinatura digital. O Windows SmartScreen pode exibir um aviso.

### Validação

- Os builds Release e portable single-file foram concluídos com sucesso.
- Um teste funcional gerou um proxy sem áudio de `640×358` e 10 segundos a partir de uma origem `854×480`.
- Todos os 299 testes automatizados passam.
- Os pacotes NuGet restaurados não apresentam vulnerabilidades conhecidas.
- A validação em ambiente Windows limpo e os testes aplicáveis de FTP/FTPS foram confirmados pelo titular da release.

### Recursos

- [Histórico de mudanças](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/CHANGELOG.md)
- [Privacidade](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/PRIVACY.md)
- [Suporte](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SUPPORT.md)
- [Segurança](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SECURITY.md)
- [Licença](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/LICENSE)
