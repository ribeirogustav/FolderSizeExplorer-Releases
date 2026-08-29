# Folder Size Explorer 1.0.2

## English

Version 1.0.2 adds fast, local file previews and improves visual quality and responsiveness in Grid and Columns views.

### Highlights

- Preview images, SVG, paginated PDF, video, DOCX, and PowerPoint files without leaving Folder Size Explorer.
- Render the first DOCX page locally without starting Microsoft Word.
- Capture the first PowerPoint slide in an isolated, read-only process when Microsoft PowerPoint is installed.
- Load Grid thumbnails on demand and retain them in a bounded memory cache.
- Use static Windows thumbnails for large videos instead of starting animated playback.
- Display sharper application icons from the Windows Shell in Grid view.
- Keep folders first and sort items by descending size in Columns view.

### Download

- Portable executable: `FolderSizeExplorer-1.0.2-win-x64.exe`
- SHA-256: `FolderSizeExplorer-1.0.2-win-x64.exe.sha256`
- Platform: Windows 10/11 x64
- Runtime: self-contained; no separate .NET installation is required

Optionally verify the executable against the published SHA-256 file before running it.

### Privacy and security

- Previews and thumbnails are processed locally.
- DOCX rendering does not execute macros.
- SVG active content and external resources are blocked.
- Temporary FTP previews and PowerPoint captures are cleaned automatically when possible.
- The executable is not digitally signed. Windows SmartScreen may display a warning.

### Validation

- Release and portable builds completed successfully.
- All 235 automated tests pass.
- Restored NuGet packages report no known vulnerabilities.

For the complete history, see [CHANGELOG.md](../CHANGELOG.md).

---

## Português (Brasil)

A versão 1.0.2 adiciona pré-visualizações locais e rápidas de arquivos, além de melhorar a qualidade visual e a responsividade dos modos Grade e Colunas.

### Destaques

- Pré-visualize imagens, SVG, PDF paginado, vídeo, DOCX e PowerPoint sem sair do Folder Size Explorer.
- Renderize localmente a primeira página de DOCX sem iniciar o Microsoft Word.
- Capture o primeiro slide em um processo isolado e somente leitura quando o Microsoft PowerPoint estiver instalado.
- Carregue miniaturas da Grade sob demanda e mantenha-as em um cache de memória limitado.
- Use miniaturas estáticas do Windows para vídeos grandes em vez de iniciar a reprodução animada.
- Exiba ícones de aplicativos mais nítidos, obtidos pelo Windows Shell no modo Grade.
- Mantenha pastas primeiro e ordene os itens por tamanho decrescente no modo Colunas.

### Download

- Executável portable: `FolderSizeExplorer-1.0.2-win-x64.exe`
- SHA-256: `FolderSizeExplorer-1.0.2-win-x64.exe.sha256`
- Plataforma: Windows 10/11 x64
- Runtime: self-contained; não é necessário instalar o .NET separadamente

Opcionalmente, confira o executável com o arquivo SHA-256 publicado antes de executá-lo.

### Privacidade e segurança

- Pré-visualizações e miniaturas são processadas localmente.
- A renderização de DOCX não executa macros.
- Conteúdo ativo e recursos externos de SVG são bloqueados.
- Pré-visualizações FTP e capturas do PowerPoint são temporárias e removidas automaticamente quando possível.
- O executável não possui assinatura digital. O Windows SmartScreen pode exibir um aviso.

### Validação

- Os builds Release e portable foram concluídos com sucesso.
- Todos os 235 testes automatizados passam.
- Os pacotes NuGet restaurados não apresentam vulnerabilidades conhecidas.

Para o histórico completo, consulte [CHANGELOG.md](../CHANGELOG.md).
