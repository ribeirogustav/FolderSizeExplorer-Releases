# Estratégia de atualização e distribuição

## 1. Objetivo

Esta política define como o Folder Size Explorer deve ser versionado, validado, publicado, atualizado e, quando necessário, retirado de circulação.

O objetivo é manter o código-fonte privado, oferecer downloads públicos verificáveis e evitar que builds antigos ou não oficiais sejam confundidos com releases da GRCX.

## 2. Canais oficiais

### Código-fonte privado

- Repositório: <https://github.com/ribeirogustav/FolderSizeExplorer>
- Visibilidade: privada.
- Conteúdo: fonte, testes, documentação interna, scripts e histórico de desenvolvimento.
- Acesso: somente pessoas autorizadas pela GRCX.

O repositório privado não é canal de distribuição ao usuário final.

### Releases públicas

- Repositório: <https://github.com/ribeirogustav/FolderSizeExplorer-Releases>
- Download: <https://github.com/ribeirogustav/FolderSizeExplorer-Releases/releases>
- Visibilidade: pública.
- Conteúdo permitido: releases, checksums, notas, documentação de usuário e links oficiais.
- Conteúdo proibido: fonte proprietária, PDBs, arquivos de projeto, sessão de desenvolvimento, credenciais e assets internos desnecessários.

### Site GRCX

- Site: <https://www.grcx.com.br/>
- Função: apresentar o produto e apontar para a release canônica.
- Regra: o site deve usar URL versionada ou a página oficial de releases, não uma cópia sem checksum/proveniência.

GitHub Releases é a origem canônica do binário público. O site GRCX funciona como canal de descoberta e redirecionamento.

## 3. Modelo de licenciamento da distribuição

- O aplicativo é freeware proprietário.
- Uso pessoal e empresarial interno é permitido conforme `LICENSE` e `EULA.md`.
- Redistribuição pública, mirrors, modificação e engenharia reversa não são autorizados.
- O repositório público não concede licença sobre o código-fonte.
- Doações são opcionais e não alteram a licença.

## 4. Versionamento

Usar versionamento semântico `MAJOR.MINOR.PATCH`:

- `MAJOR`: mudança incompatível relevante, novo modelo de dados/uso ou alteração material de licença.
- `MINOR`: funcionalidade compatível adicionada.
- `PATCH`: correção compatível, inclusive segurança.

Releases de teste podem usar sufixos como `-beta.1` e devem ser marcadas como **pre-release** no GitHub.

A versão deve permanecer consistente em:

- `FolderSizeExplorer.App.csproj` (`Version`, `AssemblyVersion`, `FileVersion`);
- `AppInfo`/janela Sobre;
- `CHANGELOG.md`;
- nome dos artefatos;
- tag Git; e
- título da release.

## 5. Canais de atualização

### Estável

Para usuários finais. Deve cumprir todos os gates obrigatórios desta política.

### Pré-release

Para validação voluntária. Deve ser identificada claramente, usar dados não sensíveis nos testes e não substituir automaticamente uma release estável. Toda pré-release pública também exige assinatura Authenticode válida, checksum, documentos legais, avisos de terceiros e ausência de bloqueador High/Critical conhecido. Builds experimentais sem esses gates permanecem privados.

Não há canal nightly público definido.

## 6. Estratégia de atualização

A versão atual não possui atualização automática nem verificação silenciosa de novas versões.

Fluxo do usuário:

1. consultar o site GRCX ou GitHub Releases;
2. ler notas, limitações e requisitos;
3. baixar o pacote versionado;
4. validar checksum e assinatura Authenticode;
5. fechar a versão anterior;
6. substituir o executável/pasta local; e
7. iniciar a nova versão.

Configurações e cache ficam em AppData e normalmente permanecem entre versões. Mudanças incompatíveis nesses formatos exigem migração documentada e backup.

Nenhum processo futuro de atualização deve enviar versão, identificador ou telemetria sem atualização prévia da política de privacidade.

## 7. Artefatos de uma release

Nome recomendado:

```text
FolderSizeExplorer-<versao>-win-x64.zip
FolderSizeExplorer-<versao>-win-x64.zip.sha256
```

Conteúdo mínimo do ZIP:

```text
FolderSizeExplorer.exe
LICENSE
EULA.md
PRIVACY.md
SUPPORT.md
SECURITY.md
THIRD_PARTY_NOTICES.md
CHANGELOG.md
PUBLIC_README.md (publicado no ZIP como README.md)
OWNERSHIP.md
METRICS.md
DISTRIBUTION.md
```

Não incluir:

- `.pdb`;
- `settings.json`, cache ou perfis FTP reais;
- QR/screenshot fora dos recursos já incorporados e autorizados;
- `FolderSizeExplorerOLD*.exe`;
- logs e transcripts;
- fonte ou arquivos de projeto; ou
- secrets/certificados de assinatura.

## 8. Gates obrigatórios

Uma release estável só pode ser publicada quando:

1. o repositório privado estiver em estado conhecido e a revisão estiver identificada;
2. `dotnet restore` concluir;
3. `dotnet build -c Release` concluir sem erros;
4. `dotnet test -c Release` concluir sem falhas;
5. a auditoria de dependências não contiver vulnerabilidade High/Critical conhecida;
6. riscos de perda de dados e transporte tiverem testes/revisão aplicáveis;
7. o executável corresponder à versão/tag;
8. a assinatura Authenticode for aplicada e validada;
9. o checksum SHA-256 for gerado após a assinatura e empacotamento;
10. documentos legais e avisos de terceiros acompanharem o ZIP;
11. a release for testada em instalação limpa/VM Windows suportada;
12. `CHANGELOG.md` e notas da release forem revisados; e
13. `THIRD_PARTY_NOTICES.md` for regenerado e comparado com o `.deps.json` final; e
14. direitos/autorização dos assets incorporados forem documentados; e
15. o link no site apontar para o artefato correto.

## 9. Bloqueadores atuais da primeira release oficial

Conforme auditoria de 23 de julho de 2026:

- FTPS aceita qualquer certificado;
- FTP sem criptografia é o padrão;
- `SQLitePCLRaw.lib.e_sqlite3 2.1.10` possui alerta `NU1903` High;
- copy recursivo segue reparse points;
- rename aceita paths além de um nome simples;
- CSV permite formula injection;
- não há certificado/configuração Authenticode; e
- avisos completos de terceiros ainda precisam ser empacotados e verificados.

Esses itens devem ser resolvidos antes de qualquer release pública, estável ou pré-release. Enquanto permanecerem, builds só podem circular de forma privada para correção e validação controlada. Uma advertência no README não substitui correção.

## 10. Assinatura e integridade

### Authenticode

- O certificado deve pertencer ao titular/publisher autorizado.
- A chave privada não pode ser armazenada no repositório.
- A assinatura deve usar timestamp confiável.
- `Get-AuthenticodeSignature` deve retornar status válido antes do empacotamento.

Configuração de certificado, cofre e timestamp: **[PENDENTE]**.

### Checksum

Gerar SHA-256 do ZIP final. O arquivo `.sha256` deve conter apenas o hash e nome exato do artefato.

O hash publicado no GitHub e no site deve ser idêntico.

## 11. Processo de publicação

1. Definir versão e escopo.
2. Atualizar código, testes, versão e changelog no repositório privado.
3. Executar restore, build, testes e auditoria.
4. Publicar em diretório limpo para `win-x64`, self-contained e single-file.
5. Verificar versão do executável.
6. Assinar o EXE e validar a assinatura.
7. Executar `.\generate-third-party-notices.ps1` e revisar o resultado.
8. Montar ZIP com documentos e avisos, usando `PUBLIC_README.md` como `README.md` público.
9. Gerar checksum.
10. Testar o ZIP em ambiente limpo.
11. Criar tag `v<versao>` no repositório privado.
12. Criar draft release no repositório público.
13. Anexar ZIP e checksum.
14. Revisar notas, licença, limitações e links.
15. Publicar a release.
16. Atualizar o site GRCX.
17. Registrar data e métricas-base em `METRICS.md` ou no controle operacional privado.

Publicação e push exigem autenticação GitHub e autorização explícita do titular.

## 12. Notas da release

Cada release deve informar:

- versão e data;
- sistemas/arquiteturas suportados;
- principais mudanças;
- correções de segurança;
- limitações conhecidas;
- instruções de atualização;
- nome e SHA-256 do artefato;
- status da assinatura; e
- links para privacidade, suporte, segurança e licença.

Não afirmar “seguro”, “sem riscos”, “mais rápido” ou “compatível” sem evidência correspondente.

## 13. Rollback e retirada

Se uma release apresentar risco de segurança ou perda de dados:

1. marcar a release como não recomendada ou removê-la dos downloads;
2. publicar aviso no repositório de releases;
3. retirar/redirecionar o link do site;
4. preservar internamente artefato, hash e revisão para investigação;
5. orientar usuários sobre mitigação e versão segura; e
6. publicar correção com novo número de versão, nunca substituindo silenciosamente o arquivo sob o mesmo nome.

Não reutilizar uma tag ou versão para binário diferente.

## 14. Repositório público de releases

Configuração recomendada:

- descrição: `Official releases of Folder Size Explorer for Windows x64`;
- issues habilitadas para bugs não sensíveis, com vulnerabilidades direcionadas ao e-mail privado;
- wiki e projects desabilitados se não forem utilizados;
- README público com downloads e licença proprietária;
- links para `SUPPORT.md`, `SECURITY.md` e `PRIVACY.md`;
- sem pull requests de código-fonte; e
- proteção da branch principal.

O repositório público deve deixar claro que não é open source e não aceita redistribuição.

## 15. Responsáveis

- Titular/publisher: Gustavo Ribeiro de Carvalho, atuando sob a marca GRCX.
- Autor principal: Gustavo Ribeiro de Carvalho.
- Release e segurança: `gustavo@grcx.com.br`.
- Suporte: `support@grcx.com.br`.
- Site/contato: `contact@grcx.com.br`.
