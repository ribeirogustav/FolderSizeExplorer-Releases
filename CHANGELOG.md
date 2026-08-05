# Changelog

All notable changes to Folder Size Explorer are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project intends to follow Semantic Versioning.

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
- Known blockers for publishing `1.0.1` are documented: CSV formula injection, destructive FTP operation review, and code signing.

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

- Version `1.0.0` was published without Authenticode signing; version `1.0.1` must not be published until current security and distribution gates are complete.
- See `SECURITY.md` and `DISTRIBUTION.md` before publication.
