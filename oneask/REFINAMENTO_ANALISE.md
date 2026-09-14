<!--
Avaliacao da "OneAsk - Proposta de Estrutura de Refinamento" (3 Features / 7 User Stories),
compartilhada por Raffaele Brivio no chat OneAsk do Teams em 14/09/2026, 13h30.
Este arquivo esta em pt-BR sem acentuacao (ASCII puro), seguindo a convencao do repositorio.
EXCECAO: a secao 8 - rascunho de resposta para o Teams - preserva a acentuacao,
porque e texto para colar em um chat, nao para viver em formulario ou URL.
CONTEUDO INTERNO DA GFT - nao publicar, nao subir em plataforma nao homologada.
-->

# Analise da Proposta de Estrutura de Refinamento

Data desta analise: **14/09/2026**.
Fonte avaliada: `OneAsk_Proposta_Estrutura_Refinamento.md` (extracao fiel da pagina do Loop).
Referencias: `PROPOSTA_SUBMETIDA.md` (o escopo que manda), `AVALIACAO.md` (a avaliacao contra o desafio), `../PLAN.md` (cronograma e papeis), `../APROVACAO.md` (os cinco entregaveis).

> O que o Raffaele pediu foram duas coisas - se as Features/US representam o que precisamos construir, e se a granularidade cabe em duas semanas - mais cinco confirmacoes de comportamento. As duas perguntas estao nas secoes 2 e 3; as cinco confirmacoes, na secao 5. A secao 8 e um rascunho de resposta pronto para colar.

---

## 1. Veredito em um paragrafo

**A estrutura esta certa na forma e incompleta no que falta nomear.** As tres Features mapeiam quase um a um nas tres camadas da arquitetura recomendada - conversa, catalogo/conectores, entrega/procedencia - e isso nao e coincidencia: um backlog com o formato do sistema e um backlog estimavel. O documento tambem absorveu quase tudo que `AVALIACAO.md` recomendava: catalogo como dado, plano antes de executar, manifesto de procedencia, resultado vazio nao e erro, e a V3 amarrada explicitamente ao texto submetido. O que falta sao **quatro coisas**, e tres delas sao baratas: o mecanismo da V3 nao tem US, a verificacao de consistencia nao existe em lugar nenhum, o invariante anti-alucinacao nao esta escrito como requisito, e **nenhum item do backlog tem formato de entregavel** - que e 100% do que o juri ve.

E uma quinta, que e de ordenacao e nao de conteudo: **7 US sem linha de corte, em 9 dias uteis de construcao, com o nucleo deterministico em um unico Back-End I.** E assim que se chega em 30/09 com cinco coisas a 80%.

---

## 2. Pergunta 1 - as Features/US representam o que precisamos construir?

**Sim, com quatro lacunas.** Primeiro o que esta certo, porque e a maior parte:

| O que a estrutura acertou | Onde |
|---|---|
| As tres Features sao as tres camadas do sistema | F01 conversa, F02 catalogo/conectores, F03 entrega |
| Catalogo como **dado**, nao como prompt - e explicitamente deixando a forma tecnica fora do refinamento funcional | US04 |
| Plano antes de executar, com confirmacao, e recalculo em caso de correcao | US01 |
| Manifesto de procedencia junto com o resultado | US06 |
| Resultado vazio nao e erro, e falha e coisa diferente de zero registros | US06 |
| A V3 declarada como o objetivo funcional **porque o texto submetido a prometeu** | Epic |
| Honestidade sobre o exemplo de Capital Markets ainda nao validado | US03 |

Esse ultimo item merece registro: o documento diz, em voz alta, que o exemplo de divergencia de posicao *"permanece apenas ilustrativo ate o caso de Capital Markets ser validado"*. Isso e exatamente a postura que `../PLAN.md` recomenda em "A lacuna de dominio" - e o oposto de simular profundidade que o time nao tem.

### Lacuna 1 - a V3 descreve comportamento e nao nomeia mecanismo

A US03 diz que o OneAsk *"devera interpretar a necessidade, determinar as informacoes necessarias, identificar as fontes disponiveis"*. Isso e **o que** acontece. Nao ha nenhuma US que diga **como**.

Repare na assimetria dentro da Feature 02: a V1 ganhou uma US para o seu mecanismo - a US04, o catalogo. A V3 nao ganhou a dela.

Consequencia pratica, e ela e seria: **a US03 e a unica historia do backlog cujo esforco nao tem teto** - e e a obrigatoria, porque o campo 8 do formulario a prometeu (`PROPOSTA_SUBMETIDA.md`). `AVALIACAO.md` secao 6, resposta 3, classifica "V3 como autonomia aberta" como arriscada dentro do prazo, e "playbooks declarativos" como simples. Sao o mesmo comportamento com dois custos separados por uma ordem de grandeza.

**Correcao, e e barata:** uma US irma da US04 dentro da Feature 02 - *"Disponibilizar playbooks de necessidade de negocio configuraveis"*. O playbook e um objeto: a necessidade, seus sinonimos, os datasets exigidos, os passos de montagem e as verificacoes de consistencia. Com ela, a US03 vira **selecao de playbook mais coleta de parametro, reusando as tools da V1** - estimavel, auditavel, e com um mecanismo que o juri consegue repetir depois. Sem ela, a US03 e "o agente e inteligente", que e precisamente o que tira nota em Inovacao (25%).

### Lacuna 2 - nao existe verificacao de consistencia em lugar nenhum

A US07 entrega *"resultado consolidado acompanhado das evidencias"*. Mas o salto de valor da V3 nao e **consolidar** - e **achar o problema**.

O exemplo da propria US03 e *"preciso investigar uma divergencia de posicao de ontem"*. Se o agente devolve um CSV cruzado e a divergencia continua sendo trabalho do humano, a demo nao entrega o que a frase prometeu. A diferenca cabe em uma linha dentro do playbook: *a soma dos movimentos do dia tem de fechar com a variacao de posicao; se nao fecha, esse e o achado*.

E a diferenca entre o passo 4 e o passo 5 do roteiro de video de `AVALIACAO.md` secao 8 - entre "aqui estao os dados" e "aqui esta o movimento sem par".

### Lacuna 3 - o invariante anti-alucinacao nao esta escrito como requisito

A Feature 02 diz, no objetivo, que a intencao e *"evitar que o agente dependa de conhecimento implicito ou 'invente' fontes, relatorios ou formas de relacionamento"*. Esta certo, e e fraco perto da versao testavel:

> **Nenhum numero na tela que nao tenha vindo de uma tool.** Toda cifra e renderizada verbatim da saida do backend.

E o corolario de arquitetura que sustenta isso: **o agente trafega referencias - `report_id`, `result_ref` - nunca linhas de dado.** O mesmo desenho e simultaneamente o controle de privacidade e a razao pela qual o agente nao consegue inventar uma cifra.

Por que isso importa mais do que parece: e o **unico diferencial da proposta que pode ser demonstrado em vez de afirmado**, e o time tem uma Analista de Teste para demonstra-lo. Diante de um juri de setor regulado, provavelmente e o argumento mais forte que o OneAsk tem. Vale como criterio de aceite em US01, US06 e US07 - ou como requisito nao funcional escrito, se o time preferir.

### Lacuna 4 - nenhum item do backlog tem formato de entregavel

Esta e a maior, e e estrutural.

Sao **cinco entregaveis obrigatorios** (`../APROVACAO.md`), e eles sao **100% do que o juri ve**: one-pager, video com pitch e demo, demo funcional, PDF de arquitetura e o diretorio da equipe no GitLab. A estrutura de refinamento planeja produto e nao menciona nenhum deles - a mesma observacao que `AVALIACAO.md` secao 7 ja fazia sobre a pagina anterior do Loop, herdada intacta.

Com congelamento de codigo em **24/09** e **9 dias uteis de construcao** a partir de hoje, um backlog so de historias de produto garante que os cinco entregaveis sejam comprimidos em 25/09 a 29/09. E dois deles nao aceitam compressao:

- **o roteiro do video precisa vir ANTES**, nao depois - a plateia que decide o primeiro lugar em 28/10 ve o video, nao a arquitetura;
- **o diretorio do GitLab nao se produz no fim** - ele e avaliado pelo historico que acumulou, e o acesso segue sem confirmacao desde ~18/08.

**Correcao:** uma Feature 04 - "Entregaveis do desafio" - ou, no minimo, esses itens rastreados ao lado do backlog de produto, com o roteiro do video datado antes do ultimo dia de construcao.

### Uma lacuna menor, de completude

A definicao de pronto da V1 (`../PLAN.md`) tem **tres** caminhos de falha. A US06 cobre dois - resultado vazio e falha de execucao. Falta o terceiro: **relatorio desconhecido - o agente oferece os candidatos mais proximos do catalogo** em vez de errar ou inventar. E criterio de aceite da US01, e sai quase de graca do catalogo da US04.

---

## 3. Pergunta 2 - a granularidade faz sentido para as proximas duas semanas?

**A quebra esta boa. O que falta e a linha de corte** - e duas US estao grandes demais, pelo mesmo motivo.

### A aritmetica que precisa estar na mesa

De hoje (14/09) ate o congelamento de codigo em 24/09 sao **9 dias uteis**. O nucleo deterministico e trabalho de **um** Back-End I, em horario voluntario. `AVALIACAO.md` secao 7 ja fez essa conta: ordem de 60 a 80 horas disponiveis contra mais de 120 na lista original, e por isso quatro coisas ja tinham sido cortadas - BigQuery, V2.3 com join arbitrario, terceiro conector, e V2.2 como capacidade de usuario.

**As US02 e US05 da estrutura proposta sao exatamente V2.2 e V2.3 com nome novo.** Isso nao e erro do documento - ele e um refinamento funcional, e funcionalmente elas fazem parte do produto. Mas se entrarem no mesmo lote das outras cinco, o corte que ja tinha sido decidido se desfaz sem ninguem decidir desfaze-lo.

### As duas US que estao grandes demais

Ambas pelo mesmo motivo: **cada uma empacota um comportamento comprometido junto com um comportamento opcional caro.**

**US05 - Descobrir e relacionar informacoes entre multiplas fontes.** Ela junta duas coisas de custos muito diferentes:

| Metade | Custo | Veredito |
|---|---|---|
| **Relacionamento previamente configurado** | Baixo - e um campo do catalogo (chaves de join), e o playbook da V3 precisa dele de qualquer forma | **Comprometido** |
| **Relacionamento semanticamente inferido**, explicado e confirmado | Alto - e o comportamento mais caro do backlog inteiro, e cai no unico Back-End I | **Esticado** |

Sugestao: **US05a** e **US05b**. A US05a entra no lote comprometido porque o playbook depende dela. A US05b fica acima da linha so se sobrar folga real.

**US07 - Entregar resultado consolidado com evidencias.** Ela ja vem marcada `[V2/V3]`, o que e o proprio documento reconhecendo que sao duas. A metade V3 - evidencias de uma execucao de playbook - e comprometida. A metade V2 - consolidacao a partir de um pedido livre - depende da US05b. Vale separar, ou no minimo escrever os criterios de aceite de modo que a metade V3 se sustente sozinha.

### Alguma US esta desnecessariamente separada?

**Nenhuma.** A candidata seria juntar US01 e US06, porque o manifesto e parte de entregar o resultado da V1. Mas vale manter separadas por um motivo pratico: **o manifesto na tela e trabalho de front-end** (Jeferson) e o fluxo conversacional e compartilhado - separadas, as duas correm em paralelo.

### A linha de corte proposta

**Comprometido - o minimo para submeter, que e V1 como fundacao mais um playbook de V3:**

| # | US | Quem | Por que e inegociavel |
|---|---|---|---|
| 1 | **US04** - catalogo configuravel | Raffaele (conteudo) + Guilherme (forma) | Tudo depende dele. E vocabulario de negocio antes de ser codigo |
| 2 | **US01** - fluxo ponta a ponta da V1 | Jeferson (conversa/plano) + Guilherme (tools) | E a fundacao |
| 3 | **US06** - CSV mais rastreabilidade | Jeferson (tela) + Guilherme (manifesto) | Maior valor por unidade de esforco do backlog inteiro |
| 4 | **US-nova** - playbooks configuraveis | Raffaele | O mecanismo que torna a US03 barata e estimavel |
| 5 | **US03** - necessidade de negocio, **restrita a um playbook fechado** | Raffaele + Guilherme | O campo 8 do formulario a prometeu. Nao entrega-la e subentregar contra o escopo submetido |
| 6 | **US05a** - relacionamento previamente configurado | Guilherme | O playbook da US03 precisa dela |
| 7 | **Verificacao de consistencia** dentro do playbook | Michelle + Raffaele | E o que transforma "buscar dados" em "achar o problema" |
| 8 | **Invariante anti-alucinacao**, com suite que prova | Michelle | O unico diferencial demonstravel em vez de afirmavel |

**Esticado, nesta ordem, e so com folga real:** US05b (relacao inferida) antes de US02 (selecao de campos e filtros). A inversao em relacao a ordem natural e proposital: a US05b **aparece no video** - "o agente encontrou uma relacao possivel e pediu confirmacao" e uma cena; filtro em linguagem natural nao e cena nenhuma.

**Fora da janela de construcao, e rastreado em paralelo desde ja:** roteiro do video, one-pager com o numero, PDF de arquitetura com a caixa de seguranca, e o diretorio do GitLab com historico real.

---

## 4. O que a estrutura nao diz e deveria

Tres itens que nao sao lacuna de qualidade do documento, mas que precisam estar escritos em algum lugar antes de virar Epic/Features/Stories definitivos.

**Dois conectores de naturezas opostas.** A US04 fala em *"qual conector/capacidade deve ser utilizado"*, mas nao exige que os sistemas mockados sejam de fato diferentes. O campo 8 do formulario **ja prometeu** adaptacao a *"diferentes sistemas, APIs e mecanismos de automacao"*. Dois de naturezas opostas - um REST/JSON paginado com auth e modos de erro, e um arquivo em Cloud Storage simulando entrega batch - provam a promessa. Um so deixa a abstracao sem prova. Vale como criterio de aceite da US04.

**Os exemplos de US01 e US02 continuam genericos.** "Relatorio X", "transacoes de ontem". A US03 ja carrega a ressalva honesta sobre validar o caso de Capital Markets - mas enquanto a conversa de 30 a 60 minutos com alguem da BU de CM nao acontecer, o refinamento nao consegue congelar o vocabulario. **E a acao de maior alavancagem disponivel ao time hoje**, e ela e pre-requisito de escrita, nao so de demo.

**A afirmacao horizontal precisa sobreviver.** O Epic diz *"reduzindo a necessidade de conhecer previamente sistemas, relatorios, APIs ou mecanismos de extracao"* - bom, e fiel ao campo 7. Vale nao perder isso ao vestir o dominio de custodia: o alcance amplo dos campos 7 e 9 e o argumento de **Escalabilidade e potencial (15%)**. Custodia e onde a dor morde mais forte, nao a redefinicao do escopo.

---

## 5. As cinco confirmacoes

### 5.1 O fluxo entender -> completar -> plano -> confirmar -> executar

**Confirmado, sem ressalva.** E literalmente a definicao de pronto da V1 em `../PLAN.md`, e o passo do plano e o que separa esta demo de um chatbot - e o passo 3 do roteiro de video, o momento em que a plateia ve **raciocinio em vez de caixa preta**.

Tres detalhes que valem fixar agora, porque sao baratos antes e caros depois:

- **o plano se apresenta no vocabulario do usuario**, nao no do schema: quais relatorios, de quais sistemas, com quais parametros;
- **a confirmacao e explicita**, nao continuacao implicita da conversa;
- **na correcao, re-renderizar o plano inteiro**, nao um diff. E mais barato de construir e mais legivel em video.

### 5.2 Informacao obrigatoria faltante ou ambiguidade bloqueiam a execucao

**Confirmado - e vale promover de comportamento a invariante.** E o mesmo principio do anti-alucinacao: o agente **nunca** preenche parametro obrigatorio por suposicao.

Duas coisas para torna-la testavel, que e o que permite a Michelle prova-la:

- **definir ambiguidade**: mais de um candidato do catalogo acima do limiar de correspondencia -> lista os candidatos e pergunta. Sem definicao, "ambiguidade" nao vira caso de teste;
- **dar saida ao laco**: depois de N turnos sem resolver, o agente declara o que ainda falta e para. "Continua interagindo ate ter informacao suficiente" sem teto vira loop na demo ao vivo - e demo ao vivo falha na hora errada.

### 5.3 Relacionamento configurado, e tambem inferido com confirmacao explicita

**Conceitualmente certo. Na pratica, sao duas decisoes e elas tem precos diferentes** - ver secao 3.

- **Configurado: sim, comprometido.** E um campo do catalogo, e o playbook da V3 depende dele.
- **Inferido: sim como comportamento, restrito no alcance.** O agente **declara a relacao candidata que enxergou e pergunta**; nunca executa so na inferencia. Isso e feature de conversa, nao de engenharia de dados - e e o que a torna viavel. Correspondencia semantica geral e aberta nao cabe em 9 dias uteis.
- **A terceira ramificacao e a mais valiosa, e e a mais barata:** *"nao possuo seguranca suficiente para realizar o cruzamento"*. Diante de um juri de setor regulado, um agente que sabe dizer que nao sabe vale mais do que um que sempre responde. A US05 ja tem essa frase - vale nao perde-la no corte.

> **Um alerta sobre o exemplo.** `CPF` e `document_number` e uma armadilha dupla. Primeiro, LGPD: `../PLAN.md` ja avisa que `customer_name` no mock e convite a alguem popular a base com dado real, e CPF e pior - e violacao de dado pessoal e desclassificacao imediata. Segundo, dominio: CPF nao e vocabulario de mercado de capitais. Trocar por uma chave de custodia - identificador de instrumento contra `isin`, ou codigo de contraparte contra `participant_id` - custa nada, demonstra exatamente a mesma coisa, e joga a favor da Aderencia em vez de contra a seguranca.

### 5.4 Multiplos relatorios por solicitacao na V1?

**Um relatorio por solicitacao na V1.** Mas a resposta completa tem uma segunda metade, e ela e a que importa:

**Multiplos relatorios nao podem faltar na submissao.** O campo 8 do formulario promete que o agente *"identifica quais relatorios e fontes sao necessarios"* - no plural. Entregar so "um pedido, um relatorio" subentrega contra o texto submetido.

A saida barata: **multiplos relatorios chegam pelo playbook da V3, nao por um parser de multipla intencao na V1.** No playbook de divergencia de posicao sao tres - Position, Transaction e Movement - e a quantidade e propriedade do playbook, nao do pedido do usuario. O agente nao precisa aprender a decompor "me traga A e B"; ele precisa saber que *esta necessidade* exige tres fontes.

Ou seja: **V1 = 1 relatorio por solicitacao. V3 = N relatorios por necessidade.** Essa resposta protege o cronograma e cumpre o texto submetido ao mesmo tempo.

### 5.5 CSV mais resumo/rastreabilidade como saida inicial

**Confirmado - e vale tratar o manifesto como entregavel de primeira classe, nao como rodape.** E o maior valor por unidade de esforco do backlog inteiro: o backend ja conhece tudo isso, aparece na tela na demo, e converte "demo legal" em "ferramenta auditavel". Em Mercado de Capitais o problema de um numero nao e produzi-lo, e **defende-lo**.

A lista da US06 esta boa. Duas adicoes que mudam a natureza do manifesto de descritivo para auditavel:

- **horario da extracao**;
- **contagem de linhas antes e depois de cada filtro e de cada join** - nao so o total final.

E uma adicao de UX, barata e que aparece em video: **previa das primeiras linhas na propria conversa**, ao lado do arquivo. O usuario nao deveria precisar abrir o download para saber se acertou.

CSV como formato inicial esta certo. XLSX e conforto que nao aparece no roteiro do video - deixar como evolucao, exatamente como a US07 ja preve.

---

## 6. O que muda no plano

Nada do que esta acima contradiz `../PLAN.md`. O que muda e o **nivel de detalhe** com que a janela de 15/09 a 21/09 pode ser planejada, e uma unica reordenacao:

| Item | Antes | Agora |
|---|---|---|
| Playbook da V3 | recomendacao em `AVALIACAO.md` secao 3.2 | precisa virar **US no backlog**, irma da US04 |
| Verificacao de consistencia | item de "outras ideias" | criterio de aceite do playbook |
| Invariante anti-alucinacao | argumento de pitch | criterio de aceite de US01/US06/US07, com suite |
| V2.2 e V2.3 | cortados em 08/09 | voltaram como US02 e US05 - **precisam ser recolocados abaixo da linha explicitamente**, senao o corte se desfaz sem decisao |
| Entregaveis | secao propria do PLAN | **nao existem no backlog** - precisam de Feature propria ou rastreio paralelo |

E uma questao aberta nova, que substitui a questao 8 de `../PLAN.md` ("qual caso de custodia vira a demo?") por uma versao mais urgente: **o refinamento nao consegue congelar vocabulario antes da conversa com a BU de Capital Markets.** Isso move aquela conversa de "acao de maior alavancagem" para **pre-requisito da escrita do Epic**.

---

## 7. Riscos que esta estrutura acrescenta ou reduz

| Risco | Efeito | Observacao |
|---|---|---|
| Escopo espalhado sem nada completo | **reduzido** | 7 US nomeadas e melhor que uma escada V1/V2/V3 sem granularidade |
| Corte de escopo de 08/09 se desfazendo | **acrescentado** | US02 e US05 sao V2.2 e V2.3 com nome novo. Sem linha de corte explicita, voltam por inercia |
| V3 sem mecanismo demonstravel | **inalterado** | A US03 descreve comportamento; o playbook continua sem US |
| Demo termina em "aqui estao os dados" | **acrescentado** | Sem verificacao de consistencia, a divergencia continua sendo trabalho do humano |
| Entregaveis comprimidos na ultima semana | **inalterado, e agora mais provavel** | Nenhum dos cinco aparece no backlog, e restam 9 dias uteis de construcao |
| Dado pessoal entrando no mock | **acrescentado** | O exemplo de CPF e um convite. Violacao e desclassificacao imediata |
| Pele de dominio sem lastro | **inalterado** | A US03 e honesta sobre isso, o que e bom - mas a conversa com CM continua nao agendada |

---

## 8. Rascunho de resposta para o Teams

> Este bloco preserva a acentuacao de proposito - e texto para colar em chat.

```
Raffaele, revisei a estrutura. Resposta curta: a quebra esta certa e as tres Features
sao as tres camadas certas do sistema — conversa, catalogo/conectores, entrega.
Consolidar de 7F/39US para 3F/7US foi a decisao correta.

Representatividade — 4 pontos que eu acrescentaria:

1) A V3 descreve comportamento e não nomeia mecanismo. A V1 ganhou uma US para o
   mecanismo dela (US04, o catálogo); a V3 não ganhou a dela. Sugiro uma US irmã da
   US04: "playbooks de necessidade de negócio configuráveis" — a necessidade, seus
   sinônimos, os datasets exigidos, os passos de montagem e as verificações de
   consistência. Com isso a US03 vira seleção de playbook + coleta de parâmetro,
   reusando as tools da V1. Sem isso, ela é a única US do backlog sem teto de esforço
   — e é a obrigatória, porque foi o que o campo 8 do formulário prometeu.

2) Não há verificação de consistência em lugar nenhum. A US07 entrega o resultado
   consolidado, mas o exemplo da US03 é "investigar uma divergência de posição" — se
   devolvermos um CSV cruzado e a divergência continuar sendo trabalho do humano, a
   demo não entrega o que a frase promete. Cabe em uma linha dentro do playbook: a
   soma dos movimentos do dia tem que fechar com a variação de posição; se não fecha,
   esse é o achado.

3) O invariante anti-alucinação merece estar escrito como critério de aceite:
   "nenhum número na tela que não tenha vindo de uma tool; toda cifra renderizada
   verbatim da saída do backend". É o único diferencial nosso que dá para *demonstrar*
   em vez de afirmar, e a Michelle é quem consegue provar isso.

4) O maior: nenhum item do backlog tem formato de entregável. São cinco obrigatórios
   e eles são 100% do que o júri vê. Com code freeze em 24/09 e 9 dias úteis de
   construção, um backlog só de histórias de produto empurra os cinco para 25–29/09 —
   e dois não aceitam compressão: o roteiro do vídeo precisa vir ANTES (quem vota em
   28/10 vê o vídeo, não a arquitetura) e o diretório do GitLab é avaliado pelo
   histórico que acumulou.

Granularidade — a quebra está boa; o que falta é a linha de corte. Duas US estão
grandes, e pelo mesmo motivo: cada uma junta um comportamento comprometido com um caro.

- US05 junta "relação previamente configurada" (barata — é campo do catálogo, e o
  playbook precisa dela) com "relação semanticamente inferida" (o comportamento mais
  caro do backlog, e cai no Guilherme sozinho). Sugiro US05a e US05b.
- US07 já vem marcada [V2/V3], o que é o próprio documento reconhecendo que são duas.

Nenhuma me parece desnecessariamente separada.

Minha proposta de linha, pensando nos 9 dias úteis até o freeze:
COMPROMETIDO — US04, US01, US06, a US nova de playbook, US03 (restrita a um playbook
fechado), US05a, mais a verificação de consistência e a suite do invariante.
ESTICADO, nessa ordem — US05b antes de US02. A inversão é proposital: a US05b aparece
no vídeo ("o agente encontrou uma relação possível e pediu confirmação" é uma cena);
filtro em linguagem natural não é cena nenhuma.

As cinco confirmações:

1) Fluxo entender → completar → plano → confirmar → executar: confirmado, é o passo
   que separa a demo de um chatbot. Três detalhes: plano no vocabulário do usuário
   (quais relatórios, de quais sistemas, com quais parâmetros); confirmação explícita,
   não continuação implícita; e na correção re-renderizar o plano inteiro, não um diff
   — mais barato de construir e mais legível em vídeo.

2) Bloquear execução por informação faltante/ambiguidade: confirmado, e eu promoveria
   de comportamento a invariante — o agente nunca preenche parâmetro obrigatório por
   suposição. Duas coisas para virar caso de teste: definir ambiguidade (mais de um
   candidato do catálogo acima do limiar → lista e pergunta) e dar saída ao laço
   (depois de N turnos, declara o que falta e para — senão vira loop na demo ao vivo).

3) Relação configurada + inferida com confirmação: conceito certo, e são duas decisões
   de preços bem diferentes. Configurada: sim, comprometida. Inferida: sim como
   comportamento, mas restrita — o agente declara a relação candidata e pergunta, nunca
   executa só na inferência. E a terceira ramificação que você escreveu ("não possuo
   segurança suficiente para realizar o cruzamento") é a mais valiosa das três e a mais
   barata — diante de um júri de setor regulado, um agente que sabe dizer que não sabe
   vale mais do que um que sempre responde.
   Um alerta sobre o exemplo: CPF/document_number é armadilha dupla. LGPD (dado pessoal
   no mock é desclassificação imediata) e domínio (CPF não é vocabulário de mercado de
   capitais). Trocar por chave de custódia — instrumento vs isin, ou código de
   contraparte vs participant_id — custa nada e demonstra exatamente a mesma coisa.

4) Múltiplos relatórios na V1: um por solicitação na V1. Mas múltiplos não podem faltar
   na submissão, porque o campo 8 promete que o agente identifica quais relatórios e
   fontes são necessários — no plural. A saída barata: múltiplos chegam pelo playbook
   da V3 (o de divergência precisa de três — Position, Transaction e Movement), onde a
   quantidade é propriedade do playbook, não do pedido. Ou seja: V1 = 1 relatório por
   solicitação, V3 = N relatórios por necessidade. Assim cumprimos o texto submetido sem
   construir parser de múltipla intenção.

5) CSV + resumo/rastreabilidade: confirmado, e eu trataria o manifesto como entregável
   de primeira classe — é o maior valor por unidade de esforço do backlog. Duas adições
   que mudam ele de descritivo para auditável: horário da extração, e contagem de linhas
   antes e depois de cada filtro e de cada join (não só o total). E uma de UX que é
   barata e aparece em vídeo: prévia das primeiras linhas na própria conversa, ao lado
   do arquivo — o usuário não deveria precisar abrir o download pra saber se acertou.

Uma última: os exemplos da US01 e US02 ainda estão genéricos ("relatório X",
"transações de ontem"). Você já foi honesto na US03 dizendo que o caso de Capital
Markets segue ilustrativo até ser validado — concordo, e por isso acho que aquela
conversa de 30–60 min com alguém da BU de CM virou pré-requisito de escrita, não só de
demo. Enquanto ela não acontece, a gente não consegue congelar o vocabulário do Epic.

Fora isso, pode seguir com a escrita — a estrutura aguenta.
```

---

## 9. Acoes que saem desta analise

1. **Decidir a linha de corte** - comprometido x esticado (secao 3). *Decisao coletiva, e e a que define o cronograma.*
2. **Criar a US do playbook** como irma da US04, e a verificacao de consistencia como criterio de aceite dela. *Raffaele.*
3. **Escrever o invariante anti-alucinacao** como criterio de aceite de US01/US06/US07. *Raffaele, com Michelle definindo como se prova.*
4. **Rastrear os cinco entregaveis** em Feature propria ou fora do backlog, com o roteiro do video datado antes do fim da construcao. *Time.*
5. **Trocar o exemplo de CPF** por uma chave de custodia, e dizer em voz alta que nenhum mock leva dado pessoal. *Raffaele.*
6. **Agendar a conversa com a BU de Capital Markets** - agora e pre-requisito de escrita do Epic, nao so da demo. *Agent Lead.*
7. **Cobrar o acesso ao GitLab** - segue a questao aberta numero 1 de `../PLAN.md`, com prazo estourado desde ~18/08, e o diretorio e entregavel. *Agent Lead.*
8. **Acrescentar o terceiro caminho de falha** - relatorio desconhecido oferece candidatos do catalogo - como criterio de aceite da US01. *Raffaele.*
9. **Exigir dois conectores de naturezas opostas** como criterio de aceite da US04. *Guilherme.*
