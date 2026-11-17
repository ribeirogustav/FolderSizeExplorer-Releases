# Folder Size Explorer 1.0.6

## English

Release date: 2026-11-16

Version 1.0.6 unifies deletion behavior for multi-selection and folders across all view modes (especially Columns view) and upgrades Dark mode with dark native window title bars and themed scrollbars.

### Highlights

- Unified toolbar trash button, `Del` key, and context-menu Delete into a single selection-based path so multi-selected items are never reduced to a single target.
- Fixed multi-selection syncing and right-click selection preservation in Columns (Miller columns) view and across all other views.
- Fixed folder deletion from Columns view by preserving column selection after opening a folder column and releasing active `FileWatcherService` directory watches before sending local folders to the Recycle Bin.
- Enabled dark Windows title bars via `DwmSetWindowAttribute` across the main window and dialogs, updating dynamically when toggling between Dark and Light themes.
- Styled `ScrollBar` tracks/thumbs, `ScrollViewer` corners, `CheckBox`, `ComboBox`, and `ComboBoxItem` for Dark and Light themes so controls and dropdowns match Dark mode.
- Changing Theme or Language in Settings now applies immediately in real time, reverting automatically if the dialog is canceled.

### Download

- Portable executable: `FolderSizeExplorer-1.0.6-win-x64.exe` (`FolderSizeExplorer.exe`, 96.87 MB)
- Platform: Windows 10/11 x64
- Runtime: self-contained; no separate .NET installation is required

**Executable SHA-256**

```text
6f41c83a7e6ae0333921d11fbd138630b57a247f8415d7f90f98e025328c48ae  FolderSizeExplorer-1.0.6-win-x64.exe
```

### Update

Close the previous version and replace the earlier executable in your local folder. Settings and cache stored in the Windows user profile are preserved.

### Privacy and security

- Local and remote operations remain strictly private with no telemetry.
- FTP/FTPS connection security and credential protection (Windows DPAPI) are unchanged.
- The executable is not digitally signed. Windows SmartScreen may display a warning; verify the SHA-256 checksum above before running.

### Validation

- Release and portable single-file (`win-x64`) builds completed successfully.
- All 350 automated tests pass.
- File version: `1.0.6.0`; source revision: `079f59f5b48ca119be1dbf5e5968ed172a0710e0`.

### Resources

- [Changelog](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/CHANGELOG.md)
- [Privacy](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/PRIVACY.md)
- [Support](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SUPPORT.md)
- [Security](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SECURITY.md)
- [License](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/LICENSE)

---

## Português (Brasil)

Data da release: 2026-11-16

A versão 1.0.6 unifica o comportamento de exclusão para seleção múltipla e pastas em todos os modos de visualização (especialmente no modo Colunas) e aprimora o tema escuro com barra de título escura nativa e barras de rolagem estilizadas.

### Destaques

- Unificação do botão da lixeira na barra de ferramentas, tecla `Del` e opção Excluir do menu de contexto em um único fluxo baseado na seleção ativa, garantindo que múltiplos itens selecionados sejam enviados juntos à Lixeira.
- Correção da sincronização de seleção múltipla no modo Colunas (Miller columns) e preservação da seleção ao abrir o menu de contexto com o botão direito em todos os modos.
- Correção da exclusão de pastas no modo Colunas: a seleção da coluna é mantida após abrir a subcoluna da pasta e o `FileWatcherService` libera o monitoramento da pasta alvo (ou subpastas) antes do envio para a Lixeira.
- Barra superior (título do Windows) em modo escuro via `DwmSetWindowAttribute` na janela principal e nos diálogos, com atualização dinâmica ao alternar entre os temas Escuro e Claro.
- Barras de rolagem (`ScrollBar`), cantos de `ScrollViewer`, `CheckBox`, `ComboBox` e listas suspensas estilizados com cores dos temas Escuro e Claro, eliminando controles brancos no modo escuro.
- Seleção de Tema e Idioma nas Configurações aplicada imediatamente em tempo real, revertendo automaticamente caso o usuário cancele a janela.

### Download

- Executável portable: `FolderSizeExplorer-1.0.6-win-x64.exe` (`FolderSizeExplorer.exe`, 96.87 MB)
- Plataforma: Windows 10/11 x64
- Runtime: self-contained; não é necessário instalar o .NET separadamente

**SHA-256 do executável**

```text
6f41c83a7e6ae0333921d11fbd138630b57a247f8415d7f90f98e025328c48ae  FolderSizeExplorer-1.0.6-win-x64.exe
```

### Atualização

Feche a versão anterior e substitua o executável antigo na sua pasta local. Configurações e cache armazenados no perfil do usuário Windows são preservados.

### Privacidade e segurança

- As operações locais e remotas permanecem estritamente privadas, sem telemetria.
- A segurança das conexões FTP/FTPS e a proteção das credenciais (Windows DPAPI) não mudaram.
- O executável não possui assinatura digital. O Windows SmartScreen pode exibir um aviso; confira o SHA-256 acima antes de executar.

### Validação

- Os builds Release e portable single-file (`win-x64`) foram concluídos com sucesso.
- Todos os 350 testes automatizados passam.
- Versão do arquivo: `1.0.6.0`; revisão fonte: `079f59f5b48ca119be1dbf5e5968ed172a0710e0`.

### Recursos

- [Changelog](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/CHANGELOG.md)
- [Privacidade](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/PRIVACY.md)
- [Suporte](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SUPPORT.md)
- [Segurança](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/docs/SECURITY.md)
- [Licença](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/blob/main/LICENSE)
