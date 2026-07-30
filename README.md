# Folder Size Explorer

**English** | [Português (Brasil)](README.pt-BR.md)

Folder Size Explorer is a proprietary Windows x64 desktop application that combines file browsing and management with recursive folder-size analysis.

This repository is the official public distribution channel. The source code is private and is not distributed here.

<p align="center">
  <img src="assets/folder-size-explorer.webp" alt="Folder Size Explorer showing column view and the size map" width="100%">
</p>

## Download

- [Download the latest release](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/releases/latest)
- Current version: `1.0.0`
- Asset: `FolderSizeExplorer-1.0.0-win-x64.exe`
- Target: Windows 10/11 x64

The portable executable is self-contained and does not require a separate .NET installation.

## Installation

1. Download `FolderSizeExplorer-1.0.0-win-x64.exe` from the official release page.
2. Optionally verify its SHA-256 checksum against the checksum published with the release.
3. Move the executable to a local folder and run it.

The application runs as the current user and does not automatically request administrator privileges. The current executable is not digitally signed, so Windows SmartScreen may display a warning.

## Features

- Asynchronous recursive folder-size calculation
- In-memory and SQLite size cache
- Details, Columns, Grid, and Dual-pane views
- Visual size map for the largest visible items
- Tabs, favorites, and recent locations
- Local and recursive filename search
- Local file operations and drag-and-drop
- CSV/JSON export and size comparison
- Interface available in 21 locales
- FTP/FTPS browsing for remote listings

FTP support is currently limited to browsing and listing. Remote download, upload, rename, and delete operations are not available.

## Privacy and Security

The application does not include telemetry. Settings, history, cache data, and FTP profiles are stored in the local Windows user profile. See [PRIVACY.md](PRIVACY.md) for details.

Report security vulnerabilities privately to `gustavo@grcx.com.br`. Do not publish credentials or destructive proof-of-concept material in public issues. See [SECURITY.md](SECURITY.md).

## Support

- Public, non-sensitive bug reports: [GitHub Issues](https://github.com/ribeirogustav/FolderSizeExplorer-Releases/issues)
- Support: `support@grcx.com.br`
- Privacy and legal: `contact@grcx.com.br`
- Security: `gustavo@grcx.com.br`
- Website: <https://www.grcx.com.br/>

See [SUPPORT.md](SUPPORT.md) for the support policy.

## License

Copyright (c) 2026 Gustavo Ribeiro de Carvalho, operating under the GRCX brand. All rights reserved.

Folder Size Explorer is proprietary freeware. Personal and internal business use is permitted. Public or third-party redistribution, mirrors, modification, and reverse engineering are not permitted without written authorization.

See [LICENSE](LICENSE) and [EULA.md](EULA.md) for the complete terms.
