# Política e modelo de métricas

## 1. Princípio

O Folder Size Explorer adota, na versão atual, uma postura **sem telemetria no aplicativo**.

O executável não envia eventos, paths, identificadores de dispositivo, crash reports ou informações de uso à GRCX. Relatórios de produto serão agregados. Os canais externos e o feedback voluntário podem, porém, fornecer à GRCX registros de origem identificáveis, como e-mail, usuário GitHub ou dados de pagamento; esse processamento é distinto da telemetria do aplicativo e segue `PRIVACY.md`.

## 2. Objetivos

As métricas devem responder, sem monitorar o filesystem do usuário:

- quantos downloads os assets oficiais recebem;
- quais versões concentram downloads;
- quais problemas chegam por suporte/issues;
- quais tipos de falha são recorrentes;
- se usuários retornam voluntariamente a pesquisas;
- volume agregado de apoio/doações; e
- eficiência operacional de releases e suporte.

## 3. Fontes permitidas

| Fonte | Dados permitidos | Observação |
| --- | --- | --- |
| GitHub Releases | Contagem de downloads por asset/release | Downloads não equivalem a usuários únicos ou instalações |
| GitHub Issues | Quantidade, categoria, estado e tempo de resposta | Não incluir conteúdo sensível no relatório agregado |
| E-mail de suporte | Contagem por categoria e versão | Agregar manualmente; não copiar mensagem pessoal para dashboard |
| Pesquisas voluntárias | Respostas consentidas | Informar finalidade e evitar paths/dados de arquivos |
| Provedores de doação | Contagem e valores bruto/líquido agregados | Seguir política e obrigações do provedor |
| Processo de release | Builds, testes, avisos, tempo e falhas | Métrica técnica interna, sem dados do usuário |

Antes da agregação, issues, e-mails, pesquisas e painéis de doação podem conter dados pessoais. O acesso deve ser restrito à finalidade operacional, e o dashboard de produto não deve copiar esses identificadores.

Fontes proibidas sem nova decisão e atualização da política de privacidade:

- telemetria silenciosa no executável;
- fingerprint de dispositivo;
- coleta de paths, extensões ou nomes de arquivos;
- upload de cache/settings;
- rastreamento de clipboard;
- correlação de doador com uso do aplicativo; e
- envio automático de crash dump.

## 4. Definições

### Downloads

**Downloads de release:** contagem de download do asset oficial reportada pelo GitHub.

Não chamar essa métrica de usuários, instalações ou dispositivos. Uma pessoa pode baixar várias vezes; automações e antivírus também podem acessar assets.

### Adoção de versão

Estimativa baseada na participação de downloads de cada versão em uma janela:

```text
participacao_downloads_versao = downloads_da_versao / downloads_de_todas_as_versoes_na_janela
```

É uma proxy de distribuição, não prova de uso ativo.

### Solicitações de suporte

Contar por categoria:

- instalação/startup;
- cálculo/cache;
- navegação/UI;
- operações de arquivos;
- FTP/rede;
- localização;
- segurança/privacidade;
- doação; e
- solicitação de recurso.

### Tempo de primeira resposta

```text
tempo_primeira_resposta = data_primeira_resposta_humana - data_recebimento
```

Relatar mediana mensal. Não publicar SLA a partir dessa métrica.

### Taxa de resolução

```text
taxa_resolucao = solicitacoes_encerradas_com_solucao / solicitacoes_encerradas
```

Separar “solução”, “orientação”, “não reproduzido”, “duplicado” e “fora de escopo”.

### Falhas reportadas

Contagem voluntária por versão e componente. Não representa crash rate porque o denominador de sessões não existe.

### Retenção

Retenção real não é mensurável sem conta ou telemetria. Não estimar retenção a partir de downloads.

Alternativas permitidas:

- pesquisa voluntária perguntando frequência e versão;
- painel voluntário com consentimento separado; e
- repetição autodeclarada em pesquisa voluntária, sem cruzar identidade entre suporte, download e doação.

### Doações

Registrar mensalmente, por canal:

- quantidade de contribuições;
- valor bruto na moeda original;
- taxas;
- valor líquido;
- moeda; e
- estornos, quando houver.

Não publicar identidade, endereço, conta, hash de transação associado a pessoa ou comprovante.

Os painéis dos provedores podem mostrar registros individuais à GRCX para conciliação, estorno, prevenção de fraude e obrigações legais. Esses registros não devem ser usados para inferir comportamento dentro do aplicativo nem combinados com suporte/download para formar perfil de usuário.

**Conversão de doação não pode ser calculada com rigor**, pois não existe contagem de usuários/instalações comparável. É permitido relatar `doações por 1.000 downloads` como proxy, sempre com essa ressalva:

```text
doacoes_por_1000_downloads = quantidade_doacoes / downloads_assets * 1000
```

## 5. Baseline em 23 de julho de 2026

| Métrica | Valor factual | Limitação |
| --- | --- | --- |
| Repositório público de releases | Criado, público e inicializado com documentação | Ainda sem release/binário |
| Releases públicas | 0 | A versão `1.0.0` ainda não foi publicada oficialmente |
| Assets/downloads oficiais | 0 | Não há asset disponível |
| Issues públicas | 0 | Canal inicializado, ainda sem histórico |
| Usuários/instalações | Não mensurável | Sem telemetria, conta ou release oficial |
| Retenção | Não mensurável | Exige pesquisa voluntária ou metodologia futura |
| Doações | Dados não fornecidos para esta baseline | Consultar painéis dos provedores de forma privada |

## 6. Métricas mensais mínimas

| Métrica | Fonte | Periodicidade | Responsável | Pública? |
| --- | --- | --- | --- | --- |
| Downloads por release/asset | GitHub | Mensal | GRCX | Pode ser agregada |
| Issues abertas/fechadas | GitHub | Mensal | GRCX | Pública no repositório de releases |
| Solicitações por categoria | E-mail/issues | Mensal | GRCX | Apenas agregado |
| Mediana de primeira resposta | E-mail/issues | Mensal | GRCX | Opcional e agregada |
| Bugs confirmados por versão | Suporte/triagem | Mensal | GRCX | Agregado |
| Doações brutas/líquidas por canal | Provedores | Mensal | GRCX Billing | Privada; publicar apenas total agregado se desejado |
| Releases e falhas de pipeline | Processo de release | Por release | GRCX | Resumo pode ser público |
| Vulnerabilidades abertas/corrigidas | Segurança | Por release | GRCX | Somente após divulgação coordenada |

## 7. Registro mensal sugerido

```text
Mês: AAAA-MM

Distribuição
- Downloads totais de assets:
- Downloads por versão:
- Downloads por tipo de asset:

Suporte
- Solicitações recebidas:
- Solicitações encerradas:
- Categorias principais:
- Mediana da primeira resposta:
- Bugs confirmados:

Qualidade
- Releases publicadas:
- Testes executados/aprovados:
- Vulnerabilidades High/Critical abertas ao final do mês:

Apoio
- Quantidade de doações:
- Total bruto por moeda/canal:
- Taxas:
- Total líquido:
- Estornos:

Aprendizados
- Problemas recorrentes:
- Hipóteses alteradas:
- Ações para o próximo mês:
```

O registro operacional preenchido deve ficar privado quando contiver valores financeiros detalhados ou informações que possam identificar pessoas.

## 8. Privacidade e retenção

- Dashboards públicos devem conter somente agregados.
- Não combinar e-mail, GitHub e pagamento para criar perfil individual.
- Não importar listas de arquivos, cache ou settings para análise.
- Acesso a dados de provedores deve ser limitado às contas autorizadas.
- Exportações de métricas devem remover identificadores pessoais.
- Retenção de dados financeiros e de contato deve seguir obrigações legais e políticas dos provedores.

## 9. Métricas atualmente indisponíveis

- usuários únicos;
- instalações bem-sucedidas;
- sessões e usuários ativos;
- ativação e tempo até primeiro resultado;
- retenção D1/D7/D30;
- uso por funcionalidade;
- duração e volume de scans;
- crash rate;
- churn; e
- conversão real de download para uso/doação.

Essas lacunas devem ser assumidas em análises de produto. Não inventar estimativas.

## 10. Mudança futura de postura

Telemetria futura só pode ser considerada após:

1. definição explícita de eventos e finalidade;
2. minimização de dados;
3. endpoint e segurança documentados;
4. retenção e acesso definidos;
5. atualização de `PRIVACY.md`;
6. consentimento explícito e revogável quando aplicável;
7. opção de uso integral sem telemetria, salvo decisão legal/produto documentada; e
8. revisão de segurança e conformidade.

Até que isso ocorra, a regra é: **nenhum dado de uso sai automaticamente do aplicativo**.
