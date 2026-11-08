# Folder Size Explorer 1.0.5

## English

Release date: 2026-11-08

Version 1.0.5 preserves system regional date formatting, routes deletions through a dedicated STA Windows Shell worker, improves FTP download conflict resolution, and enhances background calculation responsiveness and cache consistency.

### Highlights

- Preserved Windows system regional date and time patterns (System Locale) independently of the selected application interface language (Issue #1).
- Added ISO 8601 fallback for invariant regional formats and support for custom date patterns from Windows Control Panel.
- Routed local deletions through a dedicated STA Windows Shell worker, ensuring accurate Recycle Bin interaction, non-blocking UI, and per-item status reporting (success, failed, canceled).
- Corrected deletion context for deep-search results, column panes (Miller columns), and dual-pane views, preventing accidental or stale-target deletions.
- Improved FTP transfer reliability: Skip and Resume policies preserve destinations without premature deletion; collision detection for file/directory type mismatches.
- Throttled FTP progress notifications to keep the interface smooth and avoid transfer state overwrites.
- Concurrency limit changes now apply dynamically to folder-size calculation during active sessions.
- Moved size-cache database queries off the UI thread and ordered SQLite write, invalidate, and clear operations sequentially.
- Local file copy operations now use cancelable chunks and staged temporary files.
- Resizable Settings and FTP dialogs now adapt to monitor work areas and multi-monitor DPI changes.

### Download

- Portable executable: `FolderSizeExplorer-1.0.5-win-x64.exe`
- SHA-256: `FolderSizeExplorer-1.0.5-win-x64.exe.sha256`
- Package: `FolderSizeExplorer-1.0.5-win-x64.zip`
- Package SHA-256: `FolderSizeExplorer-1.0.5-win-x64.zip.sha256`
- Platform: Windows 10/11 x64
- Runtime: self-contained; no separate .NET installation is required

**Executable SHA-256**

```text
b82dd3eba3431cf84054caa676a99ebe0ee7ffded6ee95a5e9b0184597e17062  FolderSizeExplorer-1.0.5-win-x64.exe
```

Verify the ZIP with the published `FolderSizeExplorer-1.0.5-win-x64.zip.sha256` sidecar before extracting it.

### Update

Close the previous version, extract the new package to a local folder, and replace the earlier executable. Settings and cache stored in the Windows user profile are preserved.

### Privacy and security

- Local and remote operations remain strictly private with no telemetry.
- FTP/FTPS connection security and credential protection (Windows DPAPI) are unchanged.
- The executable is not digitally signed. Windows SmartScreen may display a warning; verify the SHA-256 checksum against the sidecar published with this release.

### Validation

- Release and portable single-file builds completed successfully.
- All 348 automated tests pass.
- Restored NuGet packages report no known vulnerabilities.
- File version: `1.0.5.0`; source revision: `a465114e5829d9c861190379ada47c0a28bde451`.

### Resources

- [Changelog](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/CHANGELOG.md)
- [Privacy](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/PRIVACY.md)
- [Support](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SUPPORT.md)
- [Security](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SECURITY.md)
- [License](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/LICENSE)

---

## Português (Brasil)

Data da release: 2026-11-08

A versão 1.0.5 preserva o formato regional de datas do sistema, executa exclusões em thread STA dedicada com a API nativa do Shell do Windows, aperfeiçoa a resolução de conflitos em downloads FTP e melhora a responsividade do cálculo de tamanhos em background e a consistência do cache.

### Destaques

- Preservação do formato regional de data e hora do Windows (System Locale), independentemente do idioma selecionado para a interface (Issue #1).
- Fallback para ISO 8601 em culturas invariáveis e suporte a formatos de data customizados definidos no Painel de Controle do Windows.
- Exclusão local executada em thread STA dedicada com a API nativa do Shell do Windows, garantindo envio seguro à Lixeira, interface responsiva e relatório detalhado por item (sucesso, falhas e cancelamentos).
- Correção de contexto de exclusão em resultados de busca profunda, modo Colunas (Miller columns) e painel duplo, prevenindo operações em alvos desatualizados.
- Maior confiabilidade em transferências FTP: opções Pular e Retomar preservam o destino sem exclusão prematura; detecção de colisões entre tipos arquivo e diretório.
- Notificações de progresso FTP com taxa controlada (~10 por segundo) para evitar travamentos da interface e sobreposição de status.
- Controle dinâmico do limite de concorrência no cálculo de tamanho de pastas durante a sessão.
- Consultas ao cache SQLite movidas para segundo plano e ordenação sequencial estrita de operações de gravação, invalidação e limpeza.
- Cópia local com blocos canceláveis e promoção atômica via arquivo temporário.
- Janelas de Configurações e FTP agora redimensionáveis e ajustadas à área útil do monitor e ao DPI.

### Download

- Executável portable: `FolderSizeExplorer-1.0.5-win-x64.exe`
- SHA-256: `FolderSizeExplorer-1.0.5-win-x64.exe.sha256`
- Pacote: `FolderSizeExplorer-1.0.5-win-x64.zip`
- SHA-256 do pacote: `FolderSizeExplorer-1.0.5-win-x64.zip.sha256`
- Plataforma: Windows 10/11 x64
- Runtime: self-contained; não é necessário instalar o .NET separadamente

**SHA-256 do executável**

```text
b82dd3eba3431cf84054caa676a99ebe0ee7ffded6ee95a5e9b0184597e17062  FolderSizeExplorer-1.0.5-win-x64.exe
```

Confira o ZIP com o arquivo `FolderSizeExplorer-1.0.5-win-x64.zip.sha256` publicado antes de extrair.

### Atualização

Feche a versão anterior, extraia o novo pacote em uma pasta local e substitua o executável anterior. Configurações e cache armazenados no perfil do usuário Windows são preservados.

### Privacidade e segurança

- As operações locais e remotas permanecem estritamente privadas, sem telemetria.
- A segurança das conexões FTP/FTPS e a proteção das credenciais (Windows DPAPI) não mudaram.
- O executável não possui assinatura digital. O Windows SmartScreen pode exibir um aviso; confira o SHA-256 com o sidecar publicado nesta release.

### Validação

- Os builds Release e portable single-file foram concluídos com sucesso.
- Todos os 348 testes automatizados passam.
- Os pacotes NuGet restaurados não apresentam vulnerabilidades conhecidas.
- Versão do arquivo: `1.0.5.0`; revisão fonte: `a465114e5829d9c861190379ada47c0a28bde451`.

### Recursos

- [Histórico de mudanças](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/CHANGELOG.md)
- [Privacidade](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/PRIVACY.md)
- [Suporte](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SUPPORT.md)
- [Segurança](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SECURITY.md)
- [Licença](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/LICENSE)
