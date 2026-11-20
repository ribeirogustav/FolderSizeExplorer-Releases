# Changelog

All notable changes to FolderSizeExplorerDX are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project intends to follow Semantic Versioning.

## [1.0.7] - 2026-11-19

### Fixed

- Added preview `CommandBindings` for `ApplicationCommands.Cut`, `Copy`, and `Paste` so `MainDataGrid` cannot hijack `Ctrl+C` while preserving native text editing when a `TextBox` or `PasswordBox` is focused (Issue #2).
- Tracked the active column pane in Columns view (`ResolveColumnPasteTarget`) and keyboard focus on Dual panes so `Ctrl+V` always pastes into the intended folder (including child columns opened from a single folder selection, files/multi-selection in intermediate columns, or empty column space).
- Made `Ctrl+X` followed by `Ctrl+V` in the same parent folder a safe no-op instead of renaming the item to `(1)`, while keeping `Ctrl+C` + `Ctrl+V` duplication in the same folder.
- Paused `FileWatcherService` before moving a folder that matches or contains `CurrentPath` so Windows does not lock the directory handle during `Ctrl+X` / `Ctrl+V`.
- Added FTP clipboard support (`Ctrl+C` / `Ctrl+X` in FTP folders to `Ctrl+V` in local folders) and clipboard read retries with in-memory `Cut` fallback on Windows 11.
- Restored native `DataGrid` `DG_ScrollViewer` rendering in Details view by removing the global `ScrollViewer` template override while keeping themed scrollbars.
- Updated the Size Map (treemap) to track the active pane in Dual and Columns views, display formatted sizes inside blocks and tooltips, and navigate the active Dual pane when clicked.
- Replaced destructive `ColumnPanes.Clear()` and collection replacements with in-place collection synchronization and item-instance reuse (`CollectionSyncHelper`) across Details, Grid, Dual, and Columns views, reusing loaded icons/thumbnails and calculated folder sizes and suppressing duplicate `FileWatcherService` refreshes during and after file operations to eliminate flicker and selection loss.
- Preloaded child column items and coalesced width redistribution before WPF render in Columns view, and fixed right-column click navigation (including already-highlighted folders) without layout jump.
- Fixed keyboard shortcuts (`Ctrl+C`, `Ctrl+X`, `Ctrl+V`, `Del`, `F2`, `Enter`, and arrow keys) across columns and after dialogs/file operations by synchronizing `ActiveColumnPane` selection and adding fallback active-column resolution (`HasActiveSelection` / `ResolveFallbackColumnSelectedItem`).

### Changed

- Renamed application branding to `FolderSizeExplorerDX` (preserving existing `%AppData%\FolderSizeExplorer` user settings and SQLite cache).
- Updated application and status-bar versions to `1.0.7`.

### Validation

- Release and portable single-file (`win-x64`) builds completed successfully.
- All 359 automated tests pass.

## [1.0.6] - 2026-11-16

### Fixed

- Unified all deletion triggers (toolbar trash button, `Del` key, and context menu) into a single selection-based flow across Details, Columns, Grid, and Dual views.
- Fixed multi-selection synchronization and preservation in Columns (Miller columns) view and on right-click across all file lists, allowing multiple files and folders to be deleted together.
- Fixed folder deletion from Columns view by preserving active column selection after subcolumn navigation and stopping `FileWatcherService` when deleting the currently watched directory or an ancestor directory.
- Fixed `Ctrl+X`, `Ctrl+C`, and `Ctrl+V` (as well as `ImeProcessed` and `Alt+Arrow` keys) not firing after navigation, on empty folders, when file-list focus was lost, or with an active Windows 11 IME, and ensured `Ctrl+V` pastes into the active destination directory (Issue #2).

### Changed

- Added dark Windows title bar support (`DwmSetWindowAttribute`) for the main window and secondary dialogs when Dark theme is active, updating live on theme toggle.
- Styled `ScrollBar`, `ScrollViewer` corners, `CheckBox`, `ComboBox`, and `ComboBoxItem` with theme-aware brushes (`DarkTheme` and `LightTheme`) so dialogs and lists match Dark mode cleanly.
- Applied Theme and Language selections immediately in Settings with automatic revert if canceled.
- Updated application and status-bar versions to `1.0.6`.

### Validation

- Release and portable single-file (`win-x64`) builds completed successfully.
- All 350 automated tests pass.

## [1.0.5] - 2026-11-08

### Fixed

- Preserved system regional date patterns independently of interface language (Issue #1).
- Corrected deletion context for deep-search results, column panes, and dual view; added per-item summary and an STA recycle-bin worker.
- Corrected FTP download conflict policies, case-sensitive refresh, cancellation and connection error reporting.
- Applied live calculation concurrency limits, moved size-cache queries off the UI thread and ordered cache invalidations with writes.
- Added staged, cancelable local copying and watcher-error refresh handling.
- Constrained Settings and FTP dialogs to monitor work areas and DPI changes.

### Validation

- Release and portable single-file builds completed successfully.
- All 348 automated tests pass.
- Restored NuGet packages report no known vulnerabilities.

## [1.0.4] - 2026-08-31

### Added

- Added a compact zoom bar from 50% to 250% in 5% steps, with an independently persisted percentage for Details, Columns, Grid, and Dual views.
- Added `Ctrl` + mouse-wheel zoom, including Precision Touchpad pinch events promoted by Windows.

### Fixed

- Image, document, video, icon, and thumbnail previews no longer appear mirrored in Urdu and other RTL cultures.
- Grid keyboard navigation now uses the active zoom percentage instead of a fixed item width.

### Validation

- Release and portable single-file builds completed successfully.
- All 321 automated tests pass.
- Restored NuGet packages report no known vulnerabilities.

## [1.0.3] - 2026-08-29

### Added

- Bundled the official Noto Nastaliq Urdu variable font and completed missing Urdu interface messages.
- Added multi-select filtering and persistent grouping by file type across all view modes.
- Added persistence for main-window placement and Details column order and widths.
- Added circular SVG flags to the language selector, including paired flags for languages shared across major regions.
- Added selectable previews for text, configuration, markup, and source-code files, limited to 256 KB or 5,000 lines.
- Added partial FTP text reads so large remote text files do not need to be downloaded in full.
- Added local WebP previews and a setting to enable lightweight video proxies in Modern mode.

### Changed

- Modern video previews open the original file directly by default; Classic mode uses cached, silent 10-second H.264 proxies at the smallest useful 360p, 540p, or 720p tier.
- Unsupported video codecs fall back to a static Windows thumbnail without bundling FFmpeg.
- SVG previews with explicit dimensions and a `viewBox` now fill and align correctly in the bottom-right preview.
- Window restoration now handles full-width placements on monitors with negative fractional coordinates without a startup error.
- Text previews now fill the available Classic preview pane while retaining the compact floating size in Modern mode.
- Controller help now fades after 10 seconds; Escape dismisses Modern previews until an explicit file click or selection change.
- Language flags now use a true circular clip, and Dark/Light theme choices include moon/sun icons.
- Urdu uses the embedded font at startup and after live language changes, with adjusted Window and DataGrid metrics.
- Invalid or off-screen saved window layouts are repaired when monitor configuration changes.
- Application and status-bar versions were updated to `1.0.3`.

### Privacy and licensing

- Text and video previews are processed locally. Video proxies are stored in a bounded 128 MB local cache and expire after seven days.
- Added Circle Flags source commit, per-file SHA-256 provenance, MIT license, and generated third-party notice.
- Added Noto Nastaliq Urdu source hash and SIL Open Font License 1.1 notice.

### Validation

- Release and portable single-file builds completed successfully.
- A functional media test produced a silent `640×358`, 10-second proxy from an `854×480` video.
- All 299 automated tests pass.
- Restored NuGet packages report no known vulnerabilities.

## [1.0.2] - 2026-08-29

### Highlights

This release adds fast, local file previews and improves visual quality and responsiveness in Grid and Columns views.

### Added

- Preview pane support for images, SVG, PDF, video, DOCX, and PowerPoint files.
- Paginated PDF preview.
- Fast local rendering of the first page of DOCX documents without starting Microsoft Word.
- Isolated, read-only capture of the first PowerPoint slide when Microsoft PowerPoint is installed.
- Safe local SVG rendering with active content and external resources blocked.
- On-demand Grid thumbnails for visible and adjacent rows, backed by a bounded memory cache.
- Persistent, resizable preview pane in Details view.
- Five Grid icon sizes controlled by `Ctrl++` / `Ctrl+-`; `Ctrl+0` restores the default.
- `Ctrl+Shift+C` copies selected file and folder paths as text.
- Bookmark-bar drag-and-drop for adding, reordering, nesting, and Ctrl-drag copying.

### Changed

- Large videos use a static Windows thumbnail instead of starting animated playback.
- Application files use higher-resolution Windows Shell icons in Grid view.
- Columns view keeps folders first and sorts items by size in descending order.
- Preview loading, explicit errors, cancellation, and in-memory reuse were refined.
- CSV export neutralizes spreadsheet-formula prefixes in text fields.

### Privacy

- Document, media, and SVG previews are processed locally.
- Temporary FTP preview files and PowerPoint captures are cleaned automatically when possible.

### Documentation

- Added optional `Windows+E` remapping instructions using Microsoft PowerToys.
- Thanks to [u/testednation](https://www.reddit.com/user/testednation/) for the feature feedback.

### Validation

- Release build and portable single-file build completed successfully.
- All 239 automated tests pass.
- Restored NuGet packages report no known vulnerabilities.

## [1.0.1] - 2026-08-05

### Highlights

This release focuses on two main areas:

1. **Chrome-style bookmark bar** — shortcuts for folders and programs, bookmark folders (groups), responsive overflow, and a dedicated manager.  
   **Thanks:** suggested by [u/testednation](https://www.reddit.com/user/testednation/) on Reddit. Thank you for the idea!
2. **FTP/FTPS system** — connect, browse, and transfer between local storage and remote servers, with a clearer connection window and real advanced options.

### Added

#### Chrome-style bookmark bar

- Bookmark bar with folders (groups), custom icons, responsive overflow, and a dedicated manager.
- Middle-click folders in navigation surfaces to open them in a new tab.
- Sidebar and top-bar favorites with import/export and broken-item cleanup.

#### FTP / FTPS

- Browse, upload, download, temporary open, create folder, rename, and delete on FTP and explicit FTPS servers.
- Local↔FTP transfers in dual pane, clipboard, and internal drag-and-drop, with progress and cancellation.
- Connection window (MVVM) with `IP / Host + Port` and `Full address` modes, immediate validation, and field icons.
- Security modes: **Automatic** (try FTPS, then FTP), explicit FTPS, and plain FTP, with clear warnings.
- Advanced options: passive/active mode, timeouts, retries, keep-alive, filename encoding, and symbolic-link policy.
- FTP connections can be added to sidebar favorites with an optional display name and FTP icon.
- Downloads verify by file size (instead of checksum), reducing failures on legacy servers and devices such as TVs.
- Unit tests for address parsing, profile migration, ViewModel, password persistence, and FluentFTP configuration.

#### Product and documentation

- Proprietary freeware license and EULA.
- Formal ownership and authorship statement.
- Privacy, support, security, and metrics policies without telemetry.
- Distribution strategy: private source repository, public GitHub Releases, and GRCX website.
- Technical documentation and product context.

### Changed

- FTP port and security are on the main form; advanced options are grouped into General, Connection, Server behavior, and TLS security.
- The legacy passive-mode boolean migrates to a passive/active selector without breaking existing profiles.
- New connections default to **Automatic** security; plain FTP clearly warns about unencrypted username, password, and files.
- Test connection does not save the profile; Connect still allows saving when the server is offline.
- FTP connection UI strings cover all 21 supported languages.
- Settings **OK** button is visually emphasized as the primary action.
- Startup restores the last folder only when it is still a quickly available local path; FTP, missing, slow, or unrecognized paths open **This PC** instead.

### Security

- Updated `SQLitePCLRaw` to `2.1.12`, removing High advisory `GHSA-2m69-gcr7-jv3q` from the restored dependency tree.
- Local copies reject junctions and symlinks before creating the destination tree.
- Cross-volume moves use staging, SHA-256 verification, and rollback before removing the source.
- Local rename accepts only a single valid Windows name component and rejects paths, `.` / `..`, and reserved names.
- FTP create/rename reject separators, `.` / `..`, and control characters in the UI and service.
- FTP delete revalidates the selected instance and pane before and after confirmation, rejecting stale selections.
- FTP URLs with embedded credentials, SFTP, and unsupported schemes are rejected; passwords are never stored in URLs or profile JSON plaintext.
- FTPS certificates remain subject to standard Windows validation; there is no option to accept any certificate.
- FTP links can be hidden or shown without following; recursive following remains unavailable.
- The publication review documented CSV formula handling, destructive FTP operations, and code-signing status.

## [1.0.0] - 2026-07-30

### Implemented in the audited code

- Local navigation, This PC, and network/removable drives.
- Asynchronous folder-size calculation and SQLite cache.
- Details, Columns, Grid, and Dual view modes.
- Treemap, tabs, favorites, recents, and deep search.
- Local file operations, drag-and-drop, and CSV/JSON export.
- Size comparison of two paths.
- FTP/FTPS browse-only navigation.
- Themes, 21 cultures, and XInput gamepad support.
- Optional support via external channels and payment identifiers.

### Relevant limitations

- Version `1.0.0` was published without Authenticode signing; subsequent unsigned releases must explicitly disclose the Windows SmartScreen warning.
- See `docs/SECURITY.md` and `docs/DISTRIBUTION.md` before publication.
