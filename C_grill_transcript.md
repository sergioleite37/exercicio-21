# Transcrição da Sessão — Grill-Me: Mapa de Atores URA Caixa / Seguro-Desemprego

**Data:** 2026-05-31
**Participantes:** Usuário (Sergio Leite) · Assistente (Claude Sonnet 4.6)
**Artefato produzido:** `C_relatorio_final_mapa_atores_URA_Caixa.md`

---

## Turno 1 — Instalação da Skill

**Usuário:**
> instale esta skill pra mim https://github.com/mattpocock/skills/tree/main/skills/productivity/grill-me63

**Assistente:**
A skill é `grill-me` (o "63" era parte do link acidentalmente). Verificado via GitHub CLI: o diretório `grill-me63` retorna 404; `grill-me` existe com um único arquivo `SKILL.md`.

Conteúdo do `SKILL.md`:
```
---
name: grill-me
description: Interview the user relentlessly about a plan or design until reaching
  shared understanding, resolving each branch of the decision tree. Use when user
  wants to stress-test a plan, get grilled on their design, or mentions "grill me".
---

Interview me relentlessly about every aspect of this plan until we reach a shared
understanding. Walk down each branch of the design tree, resolving dependencies
between decisions one-by-one. For each question, provide your recommended answer.

Ask the questions one at a time.

If a question can be answered by exploring the codebase, explore the codebase instead.
```

A skill `grill-me` já estava instalada em `C:\Users\leite\.claude\skills\grill-me.md` e está idêntica ao repositório — nenhuma alteração necessária.

**Como usar:** basta digitar `/grill-me` seguido do seu plano ou design que quer testar.

---

## Turno 2 — Acionamento do Grill-Me

**Usuário:**
> grill-me Quero produzir um mapa de atores da jornada "Atendimento ao Seguro-Desemprego pela URA da Caixa". Considere como contexto o artefato @B_relatorio_assistente_v3.md. Quero chegar a um mapa de atores consistente, com papéis, categorias e relações, incluindo atores frequentemente esquecidos, como auditoria, normatização, sistemas de retaguarda e fornecedores.

**Assistente — Pergunta 1:**
Antes de começarmos a construir o mapa, preciso resolver uma tensão fundamental de escopo que está no próprio enunciado.

**Qual é o canal que você quer mapear — a URA do MTE (Central 158) ou o canal da Caixa (0800 726 0207)?**

O relatório deixa claro que são dois canais com jurisdições completamente distintas:

- A **Central 158 (MTE)** é a porta de entrada principal do Seguro-Desemprego: orienta, consulta status, agenda atendimentos, e é onde a URA com CPF e árvore de decisão opera.
- O **0800 726 0207 (Caixa)** é restrito a pagamentos, saque, PIS, FGTS e Cartão Social — a Caixa não tem poder legal para alterar dados cadastrais nem julgar recursos do benefício.

Se o seu mapa se chama "URA da Caixa" mas o relatório descreve a URA do MTE, o artefato terá um erro de titularidade que contaminará toda a análise de atores e suas competências.

**Minha recomendação:** renomear o escopo para **"Atendimento ao Seguro-Desemprego pela URA da Central Alô Trabalho (158/MTE)"** e tratar a Caixa como ator de retaguarda pagador — não como titular do canal. Se quiser mapear os dois canais, sugiro fazer dois mapas separados ou um mapa integrado com fronteiras jurisdicionais explícitas.

Qual é a sua intenção real de escopo?

---

## Turno 3 — Definição de Escopo

**Usuário:**
> atendimento do Seguro-Desemprego via Unidade de Resposta Audível (URA) da Caixa Econômica Federal

**Assistente — Pergunta 2:**
Entendido. Vou trabalhar com esse escopo — a URA do canal **0800 726 0207 da Caixa**, no contexto de quem liga buscando resolver algo relacionado ao Seguro-Desemprego.

**Qual é o uso final deste mapa de atores — diagnóstico institucional, redesenho de serviço, análise de falhas de governança, ou outro?**

A resposta muda radicalmente o que o mapa precisa mostrar:

- **Diagnóstico institucional:** foco em quem detém poder decisório versus quem apenas executa — o mapa precisa expor o vazio de jurisdição da Caixa sobre dados do benefício.
- **Redesenho de serviço:** foco nos pontos de fricção e transbordo entre canais — o mapa precisa mostrar onde o usuário é redirecionado e por quê.
- **Análise de governança multi-órgão:** foco nas dependências entre atores de retaguarda (Dataprev, Serpro, MTE) que a Caixa não controla mas que determinam o que ela consegue ou não resolver.

**Minha recomendação:** se o contexto é o relatório que você já tem (que é um diagnóstico institucional com hipóteses de falha), o mapa mais útil é o de **governança e poder de agência** — ele tornará visível por que a URA da Caixa é estruturalmente incapaz de resolver a maioria das demandas que chegam até ela, e quais atores de retaguarda precisariam ser acionados para que isso mudasse.

Qual é o uso final?

---

## Turno 4 — Definição de Uso

**Usuário:**
> Diagnóstico institucional e redesenho de serviço

**Assistente — Pergunta 3:**
Ótimo — os dois objetivos juntos criam uma tensão produtiva: o diagnóstico precisa expor o que está quebrado, e o redesenho precisa mostrar onde intervir. Isso significa que o mapa precisa representar tanto poder quanto fluxo.

**Qual é a fronteira do sistema que você quer mapear — apenas os atores que interagem diretamente com a URA da Caixa, ou todo o ecossistema que determina o que ela consegue resolver?**

Há três opções com implicações bem diferentes:

- **Fronteira estreita (só atores diretos):** trabalhador → URA Caixa → atendente humano → eventualmente redirecionamento. Mapa simples, mas esconde por que a Caixa não resolve nada além de pagamento.
- **Fronteira média (atores diretos + retaguarda imediata):** inclui Dataprev, MTE e o lote de pagamento — mostra as dependências que a Caixa recebe sem controlar.
- **Fronteira ampla (ecossistema completo):** inclui TCU, Serpro, CODEFAT, empregadores, eSocial — mostra por que as falhas sistêmicas chegam até a URA da Caixa e o que seria necessário mudar para que ela pudesse resolver mais.

**Minha recomendação:** fronteira **média com aberturas para a ampla** — você representa o núcleo de atores diretos com clareza, mas registra explicitamente os atores de retaguarda como "forças externas que constrangem a URA". Isso serve tanto ao diagnóstico (mostra o vazio resolutivo) quanto ao redesenho (mostra onde estão as alavancas de mudança possíveis).

Qual fronteira você quer adotar?

---

## Turno 5 — Definição de Fronteira

**Usuário:**
> fronteira média com aberturas para ampla

**Assistente — Pergunta 4:**
Perfeito. Fronteira média com aberturas explícitas para o ecossistema amplo — isso vai gerar um mapa com dois níveis de leitura: o núcleo operacional da URA e as forças externas que a constrangem.

**Quais dimensões você quer registrar para cada ator — só papel e relação, ou também poder, incentivos e resistências como o relatório já faz?**

O relatório tem uma tabela rica com 12 colunas. Para um mapa que serve a diagnóstico e redesenho, as dimensões mais úteis são:

- **Papel e relação com o serviço** — o que o ator faz e como interage com a URA. Indispensável.
- **Poder de agência** — o quanto o ator pode mudar o resultado do atendimento. Essencial para o diagnóstico.
- **Incentivos e resistências** — o que motiva e o que bloqueia o ator. Essencial para o redesenho.
- **Dependências** — de quem o ator depende para agir. Revela gargalos.
- **Base normativa** — o que autoriza ou limita o ator legalmente. Útil para diagnóstico, menos para redesenho.
- **Lacunas de evidência** — o que ainda não sabemos sobre o ator. Importante para honestidade analítica.

**Minha recomendação:** manter **poder, incentivos, resistências e dependências** como colunas centrais, e tratar base normativa como campo secundário (apenas quando a norma for a causa direta de uma limitação). Isso mantém o mapa denso o suficiente para diagnóstico sem sobrecarregar a leitura orientada ao redesenho.

Quais dimensões você quer incluir?

---

## Turno 6 — Definição de Dimensões

**Usuário:**
> mantenha poder, incentivos, resistências e dependências como colunas centrais, tratando a base normativa como secundário e acrescente lacunas de evidência quando necessário.

**Assistente — Pergunta 5:**
Ótimo. Dimensões definidas. Agora precisamos resolver o inventário de atores antes de atribuir dimensões a cada um.

**Você quer validar a lista de atores comigo antes de construir o mapa, ou prefere que eu proponha o inventário completo com os "esquecidos" e você critica?**

Tenho uma proposta estruturada de inventário para a URA da Caixa com atores agrupados em quatro camadas:

- **Núcleo direto:** trabalhador, URA automatizada, atendente humano, Caixa Econômica Federal como instituição
- **Retaguarda imediata:** Dataprev (lote de pagamento), MTE (autorização de concessão), Serpro (eSocial)
- **Fornecedores e infraestrutura frequentemente esquecidos:** empresa terceirizada de contact center da Caixa (se houver), operadoras de telecomunicação, ANATEL
- **Atores de controle, normatização e pressão frequentemente esquecidos:** TCU, CGU, CODEFAT, Banco Central (como regulador prudencial da Caixa), Ouvidoria da Caixa, Procon, empregadores e escritórios de contabilidade que alimentam o eSocial, SINE/SRTEs como destino de transbordo, Poder Legislativo como ator de pressão institucional

**Minha recomendação:** eu proponho o inventário completo com justificativa para cada ator esquecido, e você decide quais incluir, excluir ou fundir.

Como prefere proceder?

---

## Turno 7 — Solicitação de Inventário

**Usuário:**
> proponha o inventário completo

**Assistente — Inventário Completo Proposto (22 atores):**

### Camada 1 — Núcleo Direto

| # | Ator | Papel | Por que incluir |
|---|------|-------|-----------------|
| 1 | **Trabalhador formal / doméstico** | Usuário requerente | Aciona a URA buscando status de pagamento, desbloqueio ou orientação sobre saque |
| 2 | **URA da Caixa (sistema automatizado)** | Interface de triagem e resposta eletrônica | A URA em si é um ator não-humano com lógica própria de decisão — frequentemente esquecido como ator separado da instituição que a opera |
| 3 | **Atendente humano da Caixa (PA)** | Suporte de overflow após transbordo da URA | Atua com scripts fechados; não tem acesso a sistemas do MTE/Dataprev |
| 4 | **Caixa Econômica Federal (gestora do canal)** | Agente pagador e operadora do canal telefônico | Titular do 0800 726 0207; responde pelo canal mas não pela política do benefício |

### Camada 2 — Retaguarda Imediata

| # | Ator | Papel | Por que incluir |
|---|------|-------|-----------------|
| 5 | **Dataprev** | Gera os lotes de pagamento enviados à Caixa; aplica regras de concessão do eSocial Negócio | Se o lote não chega ou chega com erro, a Caixa não paga — e não sabe por quê |
| 6 | **MTE (Ministério do Trabalho e Emprego)** | Titular da política; autoriza ou bloqueia a concessão | A Caixa executa o pagamento, mas é o MTE quem libera ou trava o benefício |
| 7 | **Serpro** | Custodiante dos dados brutos do eSocial que alimentam a Dataprev | Erros ou atrasos no Serpro se propagam para a Dataprev e chegam invisíveis à URA da Caixa |

### Camada 3 — Fornecedores e Infraestrutura (frequentemente esquecidos)

| # | Ator | Papel | Por que é esquecido e por que importa |
|---|------|-------|---------------------------------------|
| 8 | **Empresa terceirizada de contact center da Caixa** | Fornece operadores humanos, infraestrutura de PAs e sistema de gestão de filas | A Caixa provavelmente terceiriza o atendimento como o MTE faz com o 158. O contrato define SLAs, scripts e limites de acesso — quem contrata, contrata a limitação junto |
| 9 | **Operadoras de telecomunicação** | Comutam e tarifam as chamadas para o 0800 | O "0800" é gratuito para o chamador, mas o custo é repassado à Caixa via contrato com operadora. Instabilidades de comutação causam quedas de chamada que não aparecem nos logs da Caixa |
| 10 | **ANATEL** | Regula os serviços de telecomunicação e os contratos de 0800 | Define as regras de qualidade de voz, portabilidade e gratuidade — ator normativo invisível mas que impõe padrões ao canal |
| 11 | **Fornecedores de TI/plataforma da URA** | Provêm o software de URA (Genesys, Avaya ou similar), integração com APIs da Dataprev e gravação de chamadas | Uma atualização de sistema da Dataprev que quebra a API da URA da Caixa pode paralisar consultas sem que nenhum dos dois reconheça formalmente a dependência |

### Camada 4 — Controle, Normatização e Pressão (os mais frequentemente esquecidos)

| # | Ator | Papel | Por que é esquecido e por que importa |
|---|------|-------|---------------------------------------|
| 12 | **TCU** | Audita o FAT, a Dataprev e a Caixa; emite acórdãos que forçam endurecimento de filtros automáticos | Quando o TCU aponta R$ 1,02 bi em irregularidades, o MTE aperta os batimentos — e o excesso de bloqueios preventivos chega como congestionamento na URA da Caixa |
| 13 | **CGU (Controladoria-Geral da União)** | Fiscaliza internamente a Caixa como empresa pública federal | Auditorias da CGU sobre desvios na operação da Caixa geram pressão sobre métricas de atendimento e controles de acesso dos operadores |
| 14 | **CODEFAT** | Conselho tripartite que delibera sobre orçamento e regras do FAT | Define o envelope financeiro dentro do qual a Caixa opera como agente pagador — cortes de orçamento afetam lotes de pagamento |
| 15 | **Banco Central do Brasil** | Regula prudencialmente a Caixa como instituição financeira | Normas do Bacen sobre atendimento ao consumidor financeiro (Resolução CMN 4.949/2021) impõem à Caixa obrigações de tempo de atendimento e registro de reclamações que o canal 0800 precisa cumprir |
| 16 | **Ouvidoria da Caixa** | Canal interno de pós-atendimento; recebe e classifica reclamações sobre o 0800 | Frequentemente esquecida como ator analítico: é ela quem agrega os dados de falha do canal e deveria retroalimentar o redesenho — mas raramente tem poder de escrita sobre o sistema |
| 17 | **Procon / Senacon (MJ)** | Recebem reclamações de consumidores sobre o atendimento da Caixa | Um pico de reclamações no Procon sobre o 0800 é sinal de falha sistêmica — mas esse dado raramente retorna ao time de operação do canal |
| 18 | **Empregadores / empresas** | Alimentam o eSocial com dados de vínculo e rescisão | A fonte primária de erros que bloqueiam pagamentos está aqui — mas são invisíveis na jornada do trabalhador que liga para a Caixa |
| 19 | **Escritórios de contabilidade e RH** | Inserem os eventos do eSocial em nome dos empregadores | Na prática, são eles que cometem ou corrigem os erros cadastrais — mais granulares e operacionalmente mais relevantes que "empregadores" como categoria abstrata |
| 20 | **SINE / SRTEs** | Destino de redirecionamento quando a URA da Caixa não resolve | A Caixa instrui o trabalhador a procurar o SINE ou a SRTE — mas não controla nem monitora se esse redirecionamento resulta em solução |
| 21 | **Central 158 / MTE** | Canal paralelo e competidor funcional | Frequentemente esquecido no mapa da Caixa, mas é para lá que muitos trabalhadores deveriam ter ligado. A sobreposição de demandas entre os dois canais é uma falha de design do ecossistema |
| 22 | **Poder Legislativo (federal e estadual)** | Exerce pressão institucional sobre MTE e Caixa via requerimentos, CPIs e pedidos de providências | O caso da ALMG (PP nº 2.263/2023) mostra que legislativos estaduais documentam falhas do canal — são atores de pressão e sinalização de crise, não de operação |

São **22 atores** em 4 camadas.

**Pergunta 6:** Há atores que você quer excluir, fundir ou acrescentar neste inventário?

---

## Turno 8 — Fusões no Inventário

**Usuário:**
> funda órgãos de controle TCU e CGU, empregadores e escritórios de contabilidade como fontes de dados do eSocial, (8) e (9) como operadoras

**Assistente:**
Perfeito. O inventário consolidado fica com **19 atores** em 4 camadas:

**Camada 1 — Núcleo direto:** Trabalhador, URA da Caixa, Atendente humano, Caixa Econômica Federal

**Camada 2 — Retaguarda imediata:** Dataprev, MTE, Serpro

**Camada 3 — Fornecedores e infraestrutura:** Operadoras (contact center terceirizado + telecom), ANATEL, Fornecedores de TI/plataforma da URA

**Camada 4 — Controle, normatização e pressão:** Órgãos de Controle (TCU + CGU), CODEFAT, Banco Central, Ouvidoria da Caixa, Procon/Senacon, Fontes de dados do eSocial (empregadores + contabilidade), SINE/SRTEs, Central 158/MTE, Poder Legislativo

**Pergunta 7:** Qual formato de entrega você quer para o mapa final — tabela analítica densa (como no relatório), diagrama de rede de relações, ou os dois?

- **Tabela analítica:** registra poder, incentivos, resistências e dependências com precisão textual. Ótima para diagnóstico institucional.
- **Diagrama de rede:** mostra visualmente quem depende de quem, onde estão os nós críticos e os fluxos de transbordo. Ótimo para redesenho de serviço.

**Minha recomendação:** produzir a **tabela analítica completa** como artefato primário e derivar um **diagrama textual em Mermaid** para uso no redesenho.

---

## Turno 9 — Definição de Formato

**Usuário:**
> Tabela analítica completa e diagrama em Mermaid

**Assistente:**
Temos tudo o que precisamos. Artefato produzido e salvo em `C_mapa_atores_URA_Caixa.md` com:

- **Tabela analítica de 19 atores** com colunas: Ator, Camada, Categoria, Papel na jornada URA Caixa, Poder, Incentivos, Resistências, Dependências, Base Normativa, Lacunas de Evidência.
- **Diagrama Mermaid** com todas as relações direcionadas entre os 19 atores, organizados em subgrafos por camada.
- **Síntese diagnóstica** com os 4 diagnósticos estruturais emergentes.

**Quatro diagnósticos estruturais que emergem do mapa:**

1. **Vazio resolutivo** — a Caixa não tem poder de concessão, nem acesso ao eSocial; qualquer coisa além de "quando e quanto" é irresolvível pelo canal.
2. **Dependência invisível** — a URA só enxerga o lote de pagamento da Dataprev; a causa de um bloqueio é opaca tanto para o sistema quanto para o atendente.
3. **Sobreposição de canais sem integração** — o trabalhador não sabe distinguir o 0800 da Caixa do 158 do MTE, e nenhum dos dois tem mecanismo para transferir a demanda ao outro de forma resolutiva.
4. **Pressão de auditoria amplificando bloqueios** — as determinações do TCU endurecem os filtros da Dataprev, gerando bloqueios em massa que chegam ao canal da Caixa como congestionamento irresolvível.

---

## Turno 10 — Solicitação de Aprofundamento

**Usuário:**
> aprofunde os itens 3 e 4

**Assistente — Pergunta 8:**
Antes de aprofundar, preciso resolver uma questão de formato.

**Para cada um dos dois itens, o que você quer como produto do aprofundamento — análise narrativa densa, cadeia causal mapeada passo a passo, implicações para o redesenho, ou os três?**

Os dois itens têm naturezas distintas:

- **Item 3 (sobreposição de canais)** é um problema de design de ecossistema — o aprofundamento mais útil é um **mapa da jornada de confusão**: quem liga para onde, por quê, o que encontra, e onde a demanda morre ou se perde.
- **Item 4 (pressão de auditoria)** é um problema de causalidade institucional — o aprofundamento mais útil é uma **cadeia causal explícita**: do acórdão do TCU até o congestionamento na URA da Caixa, passando por cada ator intermediário e sua decisão.

**Minha recomendação:** análise narrativa densa com cadeia causal embutida para o item 4, e mapa de jornada de confusão com implicações de redesenho para o item 3.

---

## Turno 11 — Confirmação do Formato de Aprofundamento

**Usuário:**
> Sim, confirmo este formato.

**Assistente:**
Aprofundamento adicionado ao arquivo `C_mapa_atores_URA_Caixa.md`. Produzido para cada item:

**Item 3 — Sobreposição de canais:**
Mapeadas quatro rotas de confusão distintas:
- **Rota A** — Trabalhador com conta Caixa: abre CAIXA Tem → não encontra benefício → liga 0800 → Caixa confirma bloqueio mas não sabe motivo → orienta ligar para 158 ou ir ao SINE. Resultado: etapa adicionada, nenhuma informação nova.
- **Rota B** — Orientado pela empresa/sindicato: liga para 158 → pendência identificada → orienta recurso no App ou SINE. Resultado: informação ligeiramente melhor, sem resolução.
- **Rota C** — Pesquisa no buscador: encontra resultados misturados dos dois canais → tenta os dois → recebe orientações diferentes → desiste ou vai presencialmente. Resultado: perda de confiança.
- **Rota D** — Vai à agência da Caixa: atendente confirma bloqueio → orienta 158 ou SINE → sai sem resolução após deslocamento.

Mapeados os nós de transferência sem protocolo — cada passagem entre canais é verbal e sem rastro — a lacuna de governança (nenhum ator tem responsabilidade formal pela integração) e quatro intervenções de redesenho graduadas por complexidade.

**Item 4 — Pressão de auditoria:**
Desenhada a cadeia causal completa em 8 passos, do acórdão do TCU até o congestionamento na URA da Caixa. Ponto central: o **paradoxo fiscal não contabilizado** — o custo dos bloqueios preventivos (call center, SINE, dias sem renda do trabalhador) nunca é medido nem atribuído a nenhum ator; só o R$ 1,02 bi de irregularidades aparece no cálculo, justificando qualquer nível de enrijecimento. O mecanismo de retroalimentação faz o ciclo se autoperpetuar. Proposta de quatro pontos de intervenção, sendo o mais viável de curto prazo a criação do indicador de "taxa de bloqueio preventivo revertido".

---

## Turno 12 — Avanço para Redesenho

**Usuário:**
> Avance para a etapa de redesenho indicando suas implicações.

**Assistente — Pergunta 9:**
**O redesenho deve se mover dentro da estrutura institucional atual — melhorias incrementais sem exigir mudanças de lei ou fusão de órgãos — ou pode propor intervenções estruturais que exigem alteração normativa ou novo arranjo de governança?**

- **Redesenho incremental:** trabalha com os atores e canais existentes — melhora protocolos, cria indicadores, ajusta scripts, estabelece acordos bilaterais Caixa–MTE. Implementável em 6 a 18 meses sem alterar legislação. Risco: não resolve as causas raiz, apenas atenua os sintomas.
- **Redesenho estrutural:** propõe fusão de canais, novo arranjo de governança compartilhada, alteração nas competências da Dataprev, criação de instância de segunda instância administrativa. Exige vontade política, alteração normativa e prazo de 2 a 5 anos.
- **Redesenho em camadas:** organiza as intervenções por horizonte temporal e complexidade — quick wins incrementais no curto prazo, reformas de governança no médio, mudanças estruturais no longo.

**Minha recomendação:** redesenho em camadas, com cada intervenção explicitamente vinculada ao ator responsável, ao obstáculo principal e ao horizonte de implementação.

---

## Turno 13 — Confirmação do Escopo de Redesenho

**Usuário:**
> Trabalhe com redesenho em camadas vinculando cada intervenção ao seu respectivo ator, indicando os obstáculos e tempo de implementação.

**Assistente:**
Redesenho em camadas adicionado ao arquivo. **14 intervenções em 3 camadas**, cada uma vinculada a ator responsável, ator de suporte, obstáculo principal e prazo estimado.

### Estrutura de horizontes

```
CURTO PRAZO (0–12 meses)    ──── Quick wins sem alteração normativa
        │                         Mede, desambigua, treina, conecta
        │ cria dados e acordos que viabilizam ▼
MÉDIO PRAZO (12–36 meses)   ──── Reformas de governança e integrações sistêmicas
        │                         Separa riscos, integra canais, corrige na origem
        │ cria estrutura que sustenta ▼
LONGO PRAZO (36–60 meses)   ──── Mudanças estruturais e normativas
                                  Unifica canal, cria governança, limita morosidade
```

### Camada 1 — Curto Prazo (0–12 meses) | 6 intervenções

| # | Intervenção | Ator responsável | Obstáculo | Prazo |
|---|-------------|-----------------|-----------|-------|
| C1.1 | Criar indicador público de "taxa de bloqueio preventivo revertido" | MTE + Dataprev | Nenhum ator tem incentivo para publicar dado que implica autocrítica | 3–6 meses |
| C1.2 | Desagregar reclamações do 0800 por produto (SD separado dos demais) | Ouvidoria da Caixa | Granularidade não obrigatória por produto | 3–6 meses |
| C1.3 | Publicar painel de QoS do canal 0800 | Caixa + Bacen | Caixa não tem incentivo para publicar dados de congestionamento | 6–9 meses |
| C1.4 | Desambiguar comunicação institucional de canais | MTE + Caixa | Resistência de cada órgão em ceder visibilidade do seu canal | 3–6 meses |
| C1.5 | Atualizar scripts de atendentes com triagem de canal padronizada | Operadoras + MTE | Exige revisão de scripts e ciclo de treinamento | 3–6 meses |
| C1.6 | Criar número de protocolo único e interoperável entre os dois canais | MTE + Caixa + TI | Integração de sistemas de registro de chamadas de dois fornecedores distintos | 6–12 meses |

### Camada 2 — Médio Prazo (12–36 meses) | 5 intervenções

| # | Intervenção | Ator responsável | Obstáculo | Prazo |
|---|-------------|-----------------|-----------|-------|
| C2.1 | Separar filtros de bloqueio por tipo de risco | MTE + Dataprev | Resistência por risco de novo apontamento do TCU | 18–24 meses |
| C2.2 | Criar transferência direta de chamada entre 158 e 0800 com passagem de contexto | Operadoras + MTE + Caixa | Integração contratual entre canais com fornecedores distintos | 12–18 meses |
| C2.3 | Publicar relatório anual de impacto operacional dos filtros de batimento | MTE + Caixa + SINE | Cooperação entre atores sem cultura de dados compartilhados | 12–18 meses |
| C2.4 | Criar notificação expressa ao empregador antes do bloqueio (janela de 5 dias no eSocial) | MTE + Serpro | Novo fluxo no eSocial; pressão sobre empregadores | 18–30 meses |
| C2.5 | Criar acesso de leitura ao eSocial Negócio para atendentes da Caixa | Dataprev + Caixa + MTE | Segurança de dados; resistência da Dataprev | 24–36 meses |

### Camada 3 — Longo Prazo (36–60 meses) | 3 intervenções

| # | Intervenção | Ator responsável | Obstáculo | Prazo |
|---|-------------|-----------------|-----------|-------|
| C3.1 | Criar instância de governança compartilhada MTE + Caixa + Dataprev | MTE (liderança) + CODEFAT (supervisão) | Resistência institucional; disputas de protagonismo | 36–48 meses |
| C3.2 | Designar o 158 como canal único de referência para SD | MTE + Caixa | Caixa perde volume; exige campanha nacional de comunicação | 36–48 meses |
| C3.3 | Criar segunda instância administrativa com prazo máximo e limite de reanálises | MTE + Dataprev + Legislativo | Pressão dos órgãos de controle contra limite de reanálises | 48–60 meses |

**Sequenciamento por cadeia de dependência:**
1. C1.1 → C2.1 → C3.1 (calibração de filtros)
2. C1.2 + C1.3 → C2.3 → C3.4 (construção de evidência)
3. C1.4 + C1.5 → C1.6 → C2.2 → C3.2 (integração de canais)
4. C2.4 → C2.5 (correção na origem)

**Ações independentes que podem iniciar imediatamente:** C1.1, C1.2, C1.3, C1.4 e C1.5.

---

## Turno 14 — Sumário Executivo

**Usuário:**
> Produza um sumário executivo do artefato completo

**Assistente:**
Sumário executivo inserido no início do arquivo `C_relatorio_final_mapa_atores_URA_Caixa.md`. Cobre cinco blocos:

1. **Contexto e objeto** — o que é, para que serve, qual a fronteira analítica.
2. **O problema central** — vazio resolutivo estrutural: a Caixa é o canal que o trabalhador aciona, mas não é o canal que pode resolver.
3. **Quatro diagnósticos estruturais** — vazio resolutivo, dependência invisível, sobreposição de canais e pressão de auditoria amplificando bloqueios.
4. **Arquitetura de 19 atores** — síntese das quatro camadas com destaque para os atores de maior poder e menor visibilidade.
5. **Redesenho em 14 intervenções** — três tabelas por camada com ator responsável e obstáculo central.

**Recomendação de entrada única:** criar o indicador de bloqueio preventivo revertido (C1.1) — sem lei, sem sistema novo, sem acordo interinstitucional — porque é o dado que desbloqueia toda a negociação de calibração de filtros com o TCU e dá fundamento empírico para a Camada 2.

---

*Fim da transcrição. Sessão encerrada antes da etapa de geração de PDF.*

**Artefatos produzidos nesta sessão:**
- `C_mapa_atores_URA_Caixa.md` — rascunho de trabalho
- `C_relatorio_final_mapa_atores_URA_Caixa.md` — relatório final
- `C_grill_transcript.md` — esta transcrição
