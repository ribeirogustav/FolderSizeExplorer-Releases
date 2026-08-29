# Folder Size Explorer 1.0.2

## English

Version 1.0.2 adds fast, local file previews, a persistent Details preview pane, adjustable Grid icons, and improved bookmark workflows.

### Highlights

- Preview images, SVG, paginated PDF, video, DOCX, and PowerPoint files without leaving Folder Size Explorer.
- Render the first DOCX page locally without starting Microsoft Word.
- Capture the first PowerPoint slide in an isolated, read-only process when Microsoft PowerPoint is installed.
- Load Grid thumbnails on demand and retain them in a bounded memory cache.
- Use static Windows thumbnails for large videos instead of starting animated playback.
- Display sharper application icons from the Windows Shell in Grid view.
- Keep folders first and sort items by descending size in Columns view.
- Resize the persistent preview pane in Details view.
- Change Grid icon size with `Ctrl++` / `Ctrl+-` and restore it with `Ctrl+0`.
- Copy selected paths as text with `Ctrl+Shift+C`.
- Add, reorder, nest, move, and Ctrl-drag copy bookmark-bar entries.

Thanks to [u/testednation](https://www.reddit.com/user/testednation/) for the feature feedback.

### Optional Windows+E remap

Windows reserves `Windows+E` for File Explorer. Folder Size Explorer does not modify that system shortcut, but you can remap it voluntarily with Microsoft [PowerToys Keyboard Manager](https://learn.microsoft.com/windows/powertoys/keyboard-manager): map `Windows+E` to **Start App** and select `FolderSizeExplorer.exe`. PowerToys must remain running for the remap to work.

### Download

- Portable executable: `FolderSizeExplorer-1.0.2-win-x64.exe`
- SHA-256: `FolderSizeExplorer-1.0.2-win-x64.exe.sha256`
- Platform: Windows 10/11 x64
- Runtime: self-contained; no separate .NET installation is required

Optionally verify the executable against the published SHA-256 file before running it.

**SHA-256**

```text
e1782e7973e0754f2a6a60fc54ac6eee37f1cfcd8ba3f6a68fc386885e081b7e  FolderSizeExplorer-1.0.2-win-x64.exe
```

### Privacy and security

- Previews and thumbnails are processed locally.
- DOCX rendering does not execute macros.
- SVG active content and external resources are blocked.
- CSV text fields that begin like spreadsheet formulas are neutralized before export.
- Temporary FTP previews and PowerPoint captures are cleaned automatically when possible.
- The executable is not digitally signed. Windows SmartScreen may display a warning.

### Validation

- Release and portable builds completed successfully.
- All 239 automated tests pass.
- Restored NuGet packages report no known vulnerabilities.

For the complete history, see [CHANGELOG.md](../CHANGELOG.md).

---

## Português (Brasil)

A versão 1.0.2 adiciona pré-visualizações locais e rápidas, painel persistente em Detalhes, ícones ajustáveis na Grade e melhorias no fluxo de favoritos.

### Destaques

- Pré-visualize imagens, SVG, PDF paginado, vídeo, DOCX e PowerPoint sem sair do Folder Size Explorer.
- Renderize localmente a primeira página de DOCX sem iniciar o Microsoft Word.
- Capture o primeiro slide em um processo isolado e somente leitura quando o Microsoft PowerPoint estiver instalado.
- Carregue miniaturas da Grade sob demanda e mantenha-as em um cache de memória limitado.
- Use miniaturas estáticas do Windows para vídeos grandes em vez de iniciar a reprodução animada.
- Exiba ícones de aplicativos mais nítidos, obtidos pelo Windows Shell no modo Grade.
- Mantenha pastas primeiro e ordene os itens por tamanho decrescente no modo Colunas.
- Redimensione o painel de pré-visualização persistente no modo Detalhes.
- Altere o tamanho dos ícones da Grade com `Ctrl++` / `Ctrl+-` e restaure com `Ctrl+0`.
- Copie os caminhos selecionados como texto com `Ctrl+Shift+C`.
- Adicione, reordene, agrupe, mova e copie com `Ctrl` os itens da barra de favoritos.

Agradecimento a [u/testednation](https://www.reddit.com/user/testednation/) pelas sugestões.

### Remapeamento opcional de Windows+E

O Windows reserva `Windows+E` para o Explorador de Arquivos. O Folder Size Explorer não modifica esse atalho do sistema, mas você pode remapeá-lo voluntariamente com o [PowerToys Keyboard Manager](https://learn.microsoft.com/windows/powertoys/keyboard-manager) da Microsoft: associe `Windows+E` à ação **Start App** e selecione `FolderSizeExplorer.exe`. O PowerToys precisa permanecer em execução para o remapeamento funcionar.

### Download

- Executável portable: `FolderSizeExplorer-1.0.2-win-x64.exe`
- SHA-256: `FolderSizeExplorer-1.0.2-win-x64.exe.sha256`
- Plataforma: Windows 10/11 x64
- Runtime: self-contained; não é necessário instalar o .NET separadamente

Opcionalmente, confira o executável com o arquivo SHA-256 publicado antes de executá-lo.

**SHA-256**

```text
e1782e7973e0754f2a6a60fc54ac6eee37f1cfcd8ba3f6a68fc386885e081b7e  FolderSizeExplorer-1.0.2-win-x64.exe
```

### Privacidade e segurança

- Pré-visualizações e miniaturas são processadas localmente.
- A renderização de DOCX não executa macros.
- Conteúdo ativo e recursos externos de SVG são bloqueados.
- Campos de texto CSV que se parecem com fórmulas são neutralizados antes da exportação.
- Pré-visualizações FTP e capturas do PowerPoint são temporárias e removidas automaticamente quando possível.
- O executável não possui assinatura digital. O Windows SmartScreen pode exibir um aviso.

### Validação

- Os builds Release e portable foram concluídos com sucesso.
- Todos os 239 testes automatizados passam.
- Os pacotes NuGet restaurados não apresentam vulnerabilidades conhecidas.

Para o histórico completo, consulte [CHANGELOG.md](../CHANGELOG.md).
