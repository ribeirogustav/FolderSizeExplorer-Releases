# FolderSizeExplorerDX 1.0.7

## English

Release date: 2026-11-19

Version 1.0.7 makes `Ctrl+C`, `Ctrl+X`, and `Ctrl+V` keyboard shortcuts work reliably across all four view modes (Details, Columns, Grid, and Dual) and all folder types (same folder, subfolders, empty folders, cross-volume, and FTP ↔ Local).

### Highlights

- Added preview `CommandBindings` for `ApplicationCommands.Cut`, `Copy`, and `Paste` on the main window so WPF's `DataGrid` cannot hijack `Ctrl+C` while preserving native text editing whenever a `TextBox` or `PasswordBox` is focused (Issue #2).
- Tracked the active column pane in Columns (Miller columns) view (`ResolveColumnPasteTarget`) and keyboard focus on Dual panes so `Ctrl+V` always pastes into the intended folder—whether pasting into a child column opened from a single folder selection, an intermediate column with a file or multi-selection, or empty column space.
- Made `Ctrl+X` followed by `Ctrl+V` in the same parent folder a safe no-op instead of renaming the item to `(1)`, while keeping `Ctrl+C` + `Ctrl+V` numbered duplication in the same folder.
- Paused `FileWatcherService` before moving a folder that matches or contains the currently watched directory so Windows does not lock the directory handle during `Ctrl+X` / `Ctrl+V`.
- Added FTP clipboard support (`Ctrl+C` / `Ctrl+X` in FTP folders to `Ctrl+V` in local folders) and clipboard read retries with in-memory `Cut` fallback on Windows 11.
- Restored full `DataGrid` column headers and cell rendering in Details view while keeping themed scrollbars.
- Updated the Size Map (treemap) to follow the active pane in Dual and Columns views, show formatted sizes on blocks and tooltips, and navigate the active pane on click.
- Eliminated column-view flicker and selection resets by synchronizing `ColumnPanes` and `ColumnPaneViewModel.Items` in-place, reusing loaded icons and calculated folder sizes, preloading new columns before insertion, and suppressing duplicate `FileWatcherService` refreshes after file operations.
- Fixed right-column folder click navigation and added fallback active-column selection resolution so keyboard shortcuts (`Ctrl+C`, `Ctrl+X`, `Ctrl+V`, `Del`, `F2`, `Enter`, and arrows) remain responsive while folder sizes calculate in the background.
- Updated product branding to `FolderSizeExplorerDX` while preserving existing user settings and SQLite size cache.

### Download

- Portable executable: `FolderSizeExplorer-1.0.7-win-x64.exe` (`FolderSizeExplorerDX.exe`)
- SHA-256: `FolderSizeExplorer-1.0.7-win-x64.exe.sha256`
- Package: `FolderSizeExplorer-1.0.7-win-x64.zip`
- Package SHA-256: `FolderSizeExplorer-1.0.7-win-x64.zip.sha256`
- Platform: Windows 10/11 x64
- Runtime: self-contained; no separate .NET installation is required

**Executable SHA-256**

```text
4f75ea454a88f88d5b8b80df6f0f3a93f4d48a37fc4b8f861bfe13ba46defa41  FolderSizeExplorer-1.0.7-win-x64.exe
```

Verify the ZIP with the published `FolderSizeExplorer-1.0.7-win-x64.zip.sha256` sidecar before extracting it.

### Update

Close the previous version and replace the earlier executable in your local folder. Settings and cache stored in the Windows user profile are preserved.

### Privacy and security

- Local and remote operations remain strictly private with no telemetry.
- FTP/FTPS connection security and credential protection (Windows DPAPI) are unchanged.
- The executable is not digitally signed. Windows SmartScreen may display a warning; verify the SHA-256 checksum above before running.

### Validation

- Release and portable single-file (`win-x64`) builds completed successfully.
- All 359 automated tests pass.
- File version: `1.0.7.0`; source revision: `f37483ce59b7884eb23c93673c69244afb580e88`.

### Resources

- [Changelog](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/CHANGELOG.md)
- [Privacy](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/PRIVACY.md)
- [Support](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SUPPORT.md)
- [Security](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SECURITY.md)
- [License](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/LICENSE)

---

## Português (Brasil)

Data da release: 2026-11-19

A versão 1.0.7 garante o funcionamento completo dos atalhos de teclado `Ctrl+C`, `Ctrl+X` e `Ctrl+V` nos 4 modos de visualização (Detalhes, Colunas, Grade e Painel Duplo) e em todos os tipos de pasta (mesma pasta, subpastas, pastas vazias, entre volumes e entre Local ↔ FTP).

### Destaques

- Adicionados `CommandBindings` de pré-visualização para `ApplicationCommands.Cut`, `Copy` e `Paste` na janela principal, impedindo que o `DataGrid` do WPF intercepte `Ctrl+C` e preservando a edição nativa quando o foco está em um campo de texto (`TextBox`/`PasswordBox`) (Issue #2).
- Rastreamento da coluna ativa no modo Colunas (`ResolveColumnPasteTarget`) e de foco no modo Painel Duplo para que o `Ctrl+V` cole sempre na pasta correta (seja na subcoluna filha aberta ao selecionar uma pasta, em coluna intermediária com arquivo ou seleção múltipla, ou ao clicar no espaço vazio de uma coluna).
- `Ctrl+X` seguido de `Ctrl+V` na mesma pasta pai agora é tratado como no-op seguro (sem renomear o item para `(1)`), mantendo a duplicação numerada ao usar `Ctrl+C` + `Ctrl+V` na mesma pasta.
- Pausa automática do `FileWatcherService` antes de mover uma pasta que corresponda ao diretório monitorado, evitando bloqueio de handle pelo Windows durante `Ctrl+X` / `Ctrl+V`.
- Suporte a `Ctrl+C` / `Ctrl+X` em pastas FTP para colar (`Ctrl+V`) em pastas locais, além de leitura da área de transferência com retry e fallback em memória no Windows 11.
- Restauração da renderização completa de cabeçalhos e células do `DataGrid` no Modo Detalhes mantendo as barras de rolagem estilizadas por tema.
- Mapa de Tamanho (treemap) atualizado para acompanhar o painel ativo nos modos Painel Duplo e Colunas, exibir o tamanho formatado dentro dos blocos e nos tooltips e navegar no painel ativo ao clicar.
- Eliminação do piscar (flicker) e da perda de seleção no Modo Colunas através de sincronização in-place das coleções `ColumnPanes` e `Items`, reaproveitamento de ícones e tamanhos já calculados, pré-carregamento da nova coluna antes da inserção e supressão de atualizações duplicadas do `FileWatcherService`.
- Correção do clique em pastas na coluna mais à direita e resolução resiliente da seleção ativa para todos os atalhos de teclado (`Ctrl+C`, `Ctrl+X`, `Ctrl+V`, `Del`, `F2`, `Enter` e setas) mesmo durante o cálculo de tamanhos em segundo plano.
- Identidade visual e nome do aplicativo atualizados para `FolderSizeExplorerDX` (mantendo intactos as configurações e o cache SQLite existentes).

### Download

- Executável portable: `FolderSizeExplorer-1.0.7-win-x64.exe` (`FolderSizeExplorerDX.exe`)
- SHA-256: `FolderSizeExplorer-1.0.7-win-x64.exe.sha256`
- Pacote: `FolderSizeExplorer-1.0.7-win-x64.zip`
- SHA-256 do pacote: `FolderSizeExplorer-1.0.7-win-x64.zip.sha256`
- Plataforma: Windows 10/11 x64
- Runtime: self-contained; não é necessário instalar o .NET separadamente

**SHA-256 do executável**

```text
4f75ea454a88f88d5b8b80df6f0f3a93f4d48a37fc4b8f861bfe13ba46defa41  FolderSizeExplorer-1.0.7-win-x64.exe
```

Confira o ZIP com o arquivo `FolderSizeExplorer-1.0.7-win-x64.zip.sha256` publicado antes de extrair.

### Atualização

Feche a versão anterior e substitua o executável antigo na sua pasta local. Configurações e cache armazenados no perfil do usuário Windows são preservados.

### Privacidade e segurança

- As operações locais e remotas permanecem estritamente privadas, sem telemetria.
- A segurança das conexões FTP/FTPS e a proteção das credenciais (Windows DPAPI) não mudaram.
- O executável não possui assinatura digital. O Windows SmartScreen pode exibir um aviso; confira o SHA-256 acima antes de executar.

### Validação

- Os builds Release e portable single-file (`win-x64`) foram concluídos com sucesso.
- Todos os 359 testes automatizados passam.
- Versão do arquivo: `1.0.7.0`; revisão fonte: `f37483ce59b7884eb23c93673c69244afb580e88`.

### Recursos

- [Changelog](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/CHANGELOG.md)
- [Privacidade](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/PRIVACY.md)
- [Suporte](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SUPPORT.md)
- [Segurança](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SECURITY.md)
- [Licença](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/LICENSE)
