# Security Policy

## Supported versions

| Version | Security support |
| --- | --- |
| Latest stable release | Best effort |
| Previous releases | Upgrade to the latest may be required |
| Debug, `OLD`, modified, or third-party builds | Unsupported |

Official releases: <https://github.com/ribeirogustav/FolderSizeExplorer-Releases/releases>

## Responsible disclosure

Report vulnerabilities privately to:

`gustavo@grcx.com.br`

Use a subject such as: `[SECURITY] Folder Size Explorer - short summary`.

Do not open a public issue before receiving guidance, especially when credentials, code execution, data loss, or security bypass may be involved.

## Useful information in a report

- exact application version;
- Windows version/edition;
- affected component;
- preconditions and reproduction steps;
- observed or likely impact;
- minimal non-destructive proof of concept;
- sanitized logs, if any;
- suggested fix, if available; and
- a secure way to contact you.

Do not send:

- real passwords or credential files;
- tokens, private keys, or seed phrases;
- third-party data without authorization;
- unsolicited malware samples; or
- exploits against systems the researcher does not own.

## Handling process

GRCX intends to:

1. acknowledge receipt when possible;
2. reproduce and classify impact;
3. prepare a fix or mitigation;
4. coordinate disclosure proportional to risk; and
5. record the fix in release notes.

There is no contractual SLA or bug bounty. Do not perform testing that causes outage, data loss, unauthorized access, or violation of law.

## Scope

In scope:

- official Folder Size Explorer executables;
- code and scripts maintained in the private repository;
- official build and publication flow;
- local storage created by the application;
- file operations started from the UI; and
- the product's FTP/FTPS integration.

Third-party services, user-provided FTP servers, Windows, GitHub, payment providers, and the GRCX website follow their own programs, unless a failure is caused directly by the application's integration.

## Known security limitations in the audited version

Before the first official public release, treat these as blockers:

- CSV export without formula-injection neutralization; and
- missing Authenticode signing and binary provenance.

Until a corrected release is available:

- prefer FTPS or Automatic security; use plain FTP only on trusted networks;
- do not copy trees that contain unknown links;
- review names and destinations before rename/move;
- treat exported CSV as untrusted data before opening in a spreadsheet; and
- validate the origin of any executable.

## Existing protections

- runs as the current user, without automatic elevation;
- FTP passwords persisted with DPAPI `CurrentUser`;
- FTPS certificates validated by the standard Windows mechanism;
- new connections default to **Automatic** security (try explicit FTPS, then plain FTP) and plain FTP shows an unencrypted-transport warning;
- connection URLs reject embedded credentials, SFTP, and unsupported schemes;
- unchecking “Remember password” removes the persisted credential; passwords are never embedded in URLs;
- FTP links are shown without following or hidden; recursive following is not offered;
- timeouts, retries, and keep-alive have finite limits and are validated before connect;
- native SQLite dependency pinned outside advisory `GHSA-2m69-gcr7-jv3q`;
- SQLite queries are fixed and parameterized;
- search and size calculation avoid reparse points;
- local copies reject junctions and symlinks before creating the destination;
- cross-volume moves use staging and SHA-256 verification before removing the source;
- local rename accepts only a single valid Windows name component;
- FTP create/rename reject special segments, separators, and control characters;
- FTP delete revalidates the remote selection immediately before the destructive operation;
- UI delete uses the Recycle Bin and asks for confirmation; and
- no telemetry or automatic update was identified in the current version.

These controls are not a security certification.

### FTP certificates and protocols

Explicit FTPS uses Windows/.NET chain and hostname validation. The current implementation does not offer temporary trust, host/fingerprint pinning, or a persistent exception for self-signed certificates. Adding that flow requires presenting certificate details, binding any trust to host and fingerprint, and detecting certificate changes; until then, invalid or untrusted certificates are rejected.

Automatic security tries FTPS first and falls back to plain FTP only if the secure connection fails. Plain FTP transmits credentials and data without encryption and should be used only on trusted local networks.

SFTP is not a variant of FTP/FTPS and is not supported by the current FluentFTP backend. `sftp://` addresses are rejected rather than interpreted as FTP.

Downloads verify transferred files by size rather than remote checksum, because many legacy servers and appliances report unreliable hash values. Size verification still rejects truncated transfers when the remote size is available.

## Release authenticity

Every public release, including pre-releases, must include:

- a versioned executable or ZIP;
- SHA-256 checksum;
- valid Authenticode signature;
- release notes;
- license/EULA and third-party notices; and
- a link to this policy.

Do not distribute as an official release any binary that fails the gates in [`DISTRIBUTION.md`](DISTRIBUTION.md).

## Credits

Public credit to researchers will be considered only with explicit consent and after a fix or mitigation is available.
