# Política de Segurança

## Versões suportadas

| Versão | Suporte de segurança |
| --- | --- |
| Release estável mais recente | Melhor esforço |
| Releases anteriores | Atualização para a mais recente pode ser exigida |
| Builds Debug, `OLD`, modificados ou de terceiros | Não suportados |

A relação de releases oficiais fica em <https://github.com/ribeirogustav/FolderSizeExplorer-Releases/releases>.

## Reporte responsável

Envie vulnerabilidades de forma privada para:

`gustavo@grcx.com.br`

Use um assunto como: `[SECURITY] Folder Size Explorer - resumo do problema`.

Não abra issue pública antes de receber orientação, especialmente quando houver possibilidade de exposição de credenciais, execução de código, perda de dados ou bypass de segurança.

## Informações úteis no reporte

- versão exata do aplicativo;
- versão/edição do Windows;
- componente afetado;
- pré-condições e passos de reprodução;
- impacto observado ou provável;
- prova de conceito mínima e não destrutiva;
- logs sanitizados, se existirem;
- sugestão de correção, se disponível; e
- forma segura de contato.

Não envie:

- senhas ou arquivos reais de credenciais;
- tokens, chaves privadas ou seed phrases;
- dados de terceiros sem autorização;
- arquivos maliciosos não solicitados; ou
- exploração contra sistemas que não pertençam ao pesquisador.

## Processo de tratamento

A GRCX pretende:

1. confirmar o recebimento quando possível;
2. reproduzir e classificar o impacto;
3. preparar correção ou mitigação;
4. coordenar divulgação proporcional ao risco; e
5. registrar a correção nas notas da release.

Não há SLA contratual ou programa de bug bounty. Não realize testes que causem indisponibilidade, perda de dados, acesso não autorizado ou violação de lei.

## Escopo

Estão no escopo:

- executáveis oficiais do Folder Size Explorer;
- código e scripts mantidos no repositório privado;
- fluxo de build e publicação oficial;
- armazenamento local criado pelo aplicativo;
- operações de arquivos iniciadas pela interface; e
- integração FTP/FTPS implementada pelo produto.

Serviços de terceiros, servidores FTP do usuário, Windows, GitHub, provedores de pagamento e o site GRCX seguem programas próprios, salvo falha causada diretamente pela integração do aplicativo.

## Limitações de segurança conhecidas na versão auditada

Antes da primeira release pública oficial, devem ser tratados como bloqueadores:

- FTPS configurado com aceitação de qualquer certificado;
- FTP sem criptografia como configuração padrão;
- dependência nativa SQLite com alerta `NU1903` de alta gravidade;
- cópia recursiva que pode seguir junctions/symlinks;
- rename que aceita paths além de um nome simples;
- CSV sem neutralização de formula injection; e
- ausência de assinatura Authenticode e provenance do binário.

Enquanto não houver release corrigida:

- não use FTP/FTPS com credenciais sensíveis;
- não copie árvores que contenham links desconhecidos;
- revise nomes e destinos antes de renomear/mover;
- trate CSV exportado como dado não confiável antes de abrir em planilha; e
- valide a origem de qualquer executável.

## Proteções existentes

- execução como usuário atual, sem elevação automática;
- senha FTP persistida com DPAPI `CurrentUser`;
- queries SQLite fixas e parametrizadas;
- busca e cálculo de tamanho evitam reparse points;
- exclusão pela interface usa a Lixeira e pede confirmação; e
- nenhuma telemetria ou atualização automática foi identificada na versão atual.

Esses controles não constituem certificação de segurança.

## Autenticidade das releases

Toda release pública, inclusive pré-release, deve incluir:

- executável ou ZIP versionado;
- checksum SHA-256;
- assinatura Authenticode válida;
- notas de versão;
- licença/EULA e avisos de terceiros; e
- link para esta política.

Não distribua como release oficial um binário que falhe nos gates de [`DISTRIBUTION.md`](DISTRIBUTION.md).

## Créditos

Crédito público a pesquisadores será considerado somente com consentimento explícito e após a disponibilização de correção ou mitigação.
