# Folder Size Explorer

![Folder Size Explorer 1.0.1](docs/images/nova1.0.1.webp)

Folder Size Explorer is a proprietary desktop app for Windows x64 that combines file browsing with recursive folder-size calculation, a Chrome-style bookmark bar, treemap, tabs, multiple view modes, and FTP/FTPS.

This document is intended for the public releases repository. Source code is private and is not distributed in that repository.

## Status

The latest public version is `1.0.0`. Version `1.0.1` is not published yet. Do not download `OLD`, Debug, or third-party mirror builds.

## Official downloads

- GitHub Releases: <https://github.com/ribeirogustav/FolderSizeExplorer-Releases/releases>
- GRCX website: <https://www.grcx.com.br/>

Every public release, including pre-releases, must include a versioned ZIP, SHA-256 checksum, valid Authenticode signature, and legal documentation.

## Screenshots

### Details, treemap, and bookmark bar

![Details view](docs/images/nova1.0.1.webp)

### Dual pane

![Dual pane](docs/images/tela02.webp)

### Columns view

![Columns view](docs/images/tela03.webp)

### Grid view

![Grid view](docs/images/tela04.webp)

### FTP connection

![FTP connection](docs/images/tela05.webp)

## Platform

- Target: Windows 10/11 x64.
- Self-contained executable; no separate .NET install required for the portable build.
- Runs as the current user without automatic elevation.

Compatibility by Windows edition/build is described in the corresponding release notes.

## Main features

- asynchronous folder-size calculation;
- local in-memory and SQLite size cache;
- Details, Columns, Grid, and Dual views;
- treemap of the largest visible items;
- tabs, recents, and a **Chrome-style bookmark bar** (folders/groups, custom icons, overflow);
- name search in the current folder and subfolders;
- local file operations and drag-and-drop;
- CSV/JSON export and size comparison;
- UI in 21 cultures; and
- FTP/FTPS browse and local↔remote transfers.

See the release notes for limitations and fixed/pending risks.

## Important security notes

A public release is not considered official without GRCX security and integrity gates.

Report vulnerabilities privately to `gustavo@grcx.com.br`. Do not publish credentials or destructive proof-of-concept material in issues.

## Privacy

The current version does not implement telemetry in the executable. Settings, history, cache, and FTP profiles are stored in the local Windows profile. Network resources and external providers follow their own policies.

See `PRIVACY.md` in the release package/repository.

## Support

- Support: `support@grcx.com.br`
- Privacy and legal: `contact@grcx.com.br`
- Security: `gustavo@grcx.com.br`
- Donations: `billing@grcx.com.br`

Public issues for non-sensitive bugs: <https://github.com/ribeirogustav/FolderSizeExplorer-Releases/issues>.

## License

Copyright © 2026 Gustavo Ribeiro de Carvalho, doing business as GRCX. All rights reserved.

The application is proprietary freeware. The license allows personal and internal business use and deployment within the same organization. Public redistribution to third parties, mirrors, modification, and reverse engineering are not authorized without written permission.

See `LICENSE` and `EULA.md` in the release package/repository.

Donations are optional and do not expand license rights.
