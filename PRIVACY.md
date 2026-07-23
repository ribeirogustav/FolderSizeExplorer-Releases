# Política de Privacidade

**Folder Size Explorer**  
**Versão:** 1.0  
**Vigência:** 23 de julho de 2026  
**Responsável:** Gustavo Ribeiro de Carvalho, pessoa física no Brasil, atuando sob a marca GRCX

Esta política descreve o tratamento de dados realizado pela versão atual do Folder Size Explorer e pelos canais oficiais de contato da GRCX.

## 1. Resumo

- O aplicativo funciona localmente e não exige conta.
- A versão atual não implementa telemetria, analytics, publicidade ou envio automático de relatórios de uso.
- Nomes, caminhos, tamanhos e metadados de arquivos são processados no computador do usuário.
- Configurações, histórico, cache e perfis FTP são armazenados localmente.
- Dados só saem do computador quando o usuário acessa recursos de rede, abre links externos, exporta/compartilha informações ou entra em contato com a GRCX.

## 2. Dados processados localmente

Para executar suas funções, o aplicativo pode acessar:

- nomes e caminhos completos de arquivos e pastas;
- tamanhos, extensões, atributos e datas;
- estrutura de diretórios;
- unidades locais, removíveis, ópticas e de rede;
- seleção e operações solicitadas pelo usuário;
- preferências de tema, idioma, visualização e filtros; e
- informações de conexão FTP fornecidas pelo usuário.

O cálculo de tamanho soma metadados e bytes reportados pelo sistema de arquivos. O aplicativo não indexa nem envia o conteúdo dos arquivos à GRCX.

## 3. Dados armazenados no computador

| Dado | Local padrão | Proteção e finalidade |
| --- | --- | --- |
| Configurações, favoritos, recentes e último caminho | `%AppData%\FolderSizeExplorer\settings.json` | JSON sem criptografia própria; restaura preferências e atalhos |
| Perfis FTP | `%AppData%\FolderSizeExplorer\ftp-connections.json` | Host, usuário e opções em texto; senha protegida por Windows DPAPI `CurrentUser` |
| Cache de tamanhos | `%LocalAppData%\FolderSizeExplorer\folder-size-cache.db` | SQLite sem criptografia própria; guarda paths, resultados e timestamps |
| Exports | Caminho escolhido pelo usuário | CSV/JSON podem conter paths completos e mensagens de erro |
| Clipboard | Clipboard do Windows | Pode conter paths, FileDrop ou identificadores de apoio após ação do usuário |

O SQLite pode criar arquivos auxiliares `-wal` e `-shm`.

## 4. Retenção e exclusão local

- O histórico recente mantém até 15 caminhos.
- Resultados SQLite deixam de ser reutilizados depois de sete dias, mas linhas expiradas não são apagadas automaticamente na versão atual.
- Não existe botão único para apagar todos os dados locais.

Para remover dados gerenciados pelo aplicativo:

1. Feche o Folder Size Explorer.
2. Exclua `%AppData%\FolderSizeExplorer`.
3. Exclua `%LocalAppData%\FolderSizeExplorer`.
4. Exclua separadamente exports criados por você.
5. Limpe ou substitua o conteúdo do clipboard, se necessário.

Essas ações não apagam dados mantidos por servidores FTP, provedores de pagamento, GitHub, e-mail ou outros serviços externos.

## 5. Rede e terceiros

### FTP e FTPS

Quando o usuário configura um servidor, o aplicativo envia ao servidor escolhido:

- endereço do servidor e porta;
- nome de usuário e senha;
- comandos e paths remotos; e
- solicitações de listagem.

O servidor devolve nomes, tipos, tamanhos e datas. FTP sem criptografia transmite credenciais e tráfego sem proteção. A implementação FTPS da versão auditada aceita qualquer certificado e não deve ser considerada adequada para credenciais sensíveis até correção publicada.

A GRCX não controla a política de privacidade do servidor escolhido pelo usuário.

### Unidades e compartilhamentos de rede

O Windows pode realizar DNS, autenticação e tráfego SMB ao consultar unidades mapeadas ou paths UNC. Esse tratamento depende da configuração do sistema, da organização e do servidor acessado.

### Links externos

O aplicativo pode abrir no navegador, somente após ação do usuário:

- <https://www.grcx.com.br/>
- <https://buymeacoffee.com/ribeirogustav>
- páginas do GitHub relacionadas aos releases e suporte.

Esses serviços tratam dados segundo suas próprias políticas.

### Doações

O aplicativo não processa pagamentos nem recebe confirmação de transação. Ele apenas abre um provedor ou mostra/copia QR codes e identificadores de pagamento.

Provedores e redes de pagamento podem tratar nome, conta, endereço, IP, dispositivo, valor e dados exigidos por lei. Consulte a política do provedor antes de contribuir.

A GRCX pode acessar, nos painéis dos provedores, nome/identificador do pagador, valor, moeda, taxas, status, estorno e demais campos disponibilizados. A finalidade é conciliação, resposta a dúvidas, prevenção de fraude e cumprimento de obrigações legais. Esses dados não são combinados com uso do aplicativo para criar perfil comportamental. A retenção depende do provedor e das obrigações legais aplicáveis.

## 6. Telemetria e métricas

A versão atual não envia:

- eventos de uso;
- lista de arquivos;
- paths;
- métricas de performance;
- identificadores do dispositivo;
- crash reports; ou
- dados de retenção.

A GRCX pode consultar métricas agregadas, como downloads de assets, volume de solicitações e totais de doações. Para produzir esses agregados, pode acessar registros identificáveis de issues, e-mails, pesquisas voluntárias e provedores de pagamento. Esses registros não são coletados pelo executável e devem ser usados somente para atendimento, pesquisa consentida, conciliação e agregação. Consulte [`METRICS.md`](METRICS.md).

Pesquisas voluntárias devem informar finalidade, campos, responsável e uso antes do envio. Respostas não devem solicitar paths ou conteúdo de arquivos e não serão combinadas com doações para criar perfil individual.

Qualquer telemetria futura deverá ser documentada antes da coleta e, quando aplicável, dependerá de consentimento explícito.

## 7. Contato com suporte, privacidade ou segurança

Quando você envia um e-mail ou issue, a GRCX recebe os dados fornecidos voluntariamente, como:

- nome e endereço de e-mail;
- versão do aplicativo e do Windows;
- descrição da solicitação;
- screenshots, logs ou anexos enviados; e
- conteúdo técnico necessário ao atendimento.

Não envie senhas, chaves, tokens, dados financeiros, listas completas de arquivos ou documentos pessoais. Antes de anexar uma imagem ou export, remova paths, nomes de usuário, hosts e informações confidenciais.

Esses dados serão usados para responder, investigar falhas, prevenir abuso e melhorar o produto. Mensagens podem ser mantidas pelo tempo necessário ao atendimento, prevenção de recorrência e cumprimento de obrigações legais. Não há prazo único aplicável a todos os canais nesta versão da política.

## 8. Compartilhamento

A GRCX não vende dados pessoais coletados pelo aplicativo, pois o executável atual não envia esses dados à GRCX.

Dados recebidos por contato podem ser compartilhados somente quando necessário com:

- provedores de e-mail, hospedagem e GitHub usados para operar os canais;
- prestadores autorizados que auxiliem no atendimento; ou
- autoridades, quando houver obrigação legal.

## 9. Segurança

A versão atual utiliza permissões do usuário Windows e DPAPI para senhas FTP persistidas. Settings, cache e demais campos do perfil FTP não têm criptografia própria.

Nenhum sistema é livre de riscos. Consulte [`SECURITY.md`](SECURITY.md) para práticas, limitações conhecidas e reporte responsável.

## 10. Direitos e solicitações

Para solicitar informações, correção ou exclusão de dados mantidos diretamente pela GRCX nos canais de contato, escreva para `contact@grcx.com.br`.

Inclua informação suficiente para localizar a interação, mas não envie documentos adicionais sem necessidade. A resposta observará a legislação aplicável e poderá exigir confirmação de identidade proporcional ao pedido.

Dados armazenados somente no computador devem ser gerenciados pelo próprio usuário conforme a seção 4.

## 11. Crianças e adolescentes

O produto é um utilitário geral e não é direcionado especificamente a crianças. O aplicativo não cria contas nem coleta deliberadamente idade. Responsáveis devem supervisionar operações de arquivos e uso de meios de pagamento.

## 12. Alterações desta política

Alterações serão versionadas e publicadas com o produto ou nos canais oficiais. Mudanças materiais de coleta no aplicativo devem ser comunicadas antes de entrarem em vigor.

## 13. Contatos

- Privacidade e assuntos legais: `contact@grcx.com.br`
- Suporte: `support@grcx.com.br`
- Segurança: `gustavo@grcx.com.br`
- Doações: `billing@grcx.com.br`
- Site: <https://www.grcx.com.br/>
