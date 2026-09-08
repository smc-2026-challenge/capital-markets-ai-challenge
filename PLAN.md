# Plano - Desafio Capital Markets AI Agents Challenge (SMC 2026)

Data do checkpoint: **08/09/2026**. Versao legivel por maquina: `checkpoint.json` (v8).
Arquivos companheiros: `RULES.md` (resumo do regulamento), `IDEAS.md` (espaco de problemas e catalogo de solucoes), `NAMES.md` (candidatos a nome do time), `oneask/` (a solucao em construcao, o texto submetido e a avaliacao).

> Este arquivo esta em pt-BR sem acentuacao (ASCII puro), para nao quebrar em formularios, nomes de arquivo e terminais.

## O que mudou desde 12/08

O checkpoint anterior dizia que nada estava decidido. Isso ja nao e verdade: existe um MVP com direcao definida, chamado **OneAsk - Agente Inteligente de Extracao de Dados**, documentado em pagina do Microsoft Loop e extraido para `oneask/OneAsk_Proposta_Evolucao_MVP.md`.

A recomendacao de agosto (**A3 Covenant Watch**, vice **B4 Normalizador de eventos corporativos**) esta **superada**. Fica preservada em `checkpoint.json`, em `direcao_da_solucao.recomendacao_anterior_agosto_2026`, e o catalogo de dores P1-P5 e de solucoes A1-D9 em `IDEAS.md` segue valido como referencia de espaco de problemas.

**Atualizacao de 08/09:** o texto submetido no formulario foi obtido e esta em `oneask/PROPOSTA_SUBMETIDA.md` (campos 7, 8 e 9 - "Dados do Agente"). Isso destrava o que era a questao numero um do projeto e **corrige duas decisoes de escopo** - ver "O que o texto submetido muda", abaixo. A **aprovacao** pelo comite (selecao encerrada em 01/09) segue nao confirmada.

## Onde estamos

| Item | Situacao |
|---|---|
| Regulamento lido | Feito |
| Direcao de problema e solucao | **Travada pelo formulario** - `oneask/PROPOSTA_SUBMETIDA.md`. O que segue em discussao e o plano de evolucao V1/V2/V3 |
| Fase | **Construcao do agente** - janela 13/08 a 30/09 |
| Proposta submetida no formulario | **Confirmada** - texto em `oneask/PROPOSTA_SUBMETIDA.md` |
| Proposta aprovada pelo comite | **Nao confirmada** - a selecao fechou em 01/09 |
| Campos 1 a 6 do formulario | **Nao vistos** - e por isso o nome do time registrado segue nao confirmado |
| Composicao do time | **Confirmada - 4 integrantes, o maximo permitido** (ver abaixo) |
| Agent Lead | **Raffaele Brivio** |
| Nome do time registrado | Nao confirmado - o chat se chama OneAsk, mas isso e o nome do produto |
| Licencas Gemini Enterprise | Recebimento nao confirmado |
| Guia Tecnico | **Resolvido - nao existe** como documento separado. Ver `GUIA_TECNICO_RESPOSTA.md` |
| Os quatro entregaveis obrigatorios | Nao iniciados, exceto a demo (V1 em construcao) |

Em `checkpoint.json`, `null` significa **nao confirmado**, nao `false`. A distincao importa: parte do trabalho avancou fora deste repositorio.

## O time

Quatro integrantes - **o maximo que o regulamento permite** (sec. 4.3: de 2 a 4). O time esta cheio: nao cabe mais ninguem, e a substituicao de integrantes so era permitida ate a data limite do cronograma oficial, que ja passou.

| Integrante | Usuario | Cargo | Unidade | Jornada |
|---|---|---|---|---|
| **Brivio, Raffaele** - Agent Lead | - | Analista de Negocios III | PSU BR | 09:00-18:00 |
| Franco, Jeferson | `jrfc` | Desenvolvedor(a) Front-End II | PSU BR | 08:00-17:00 |
| Augusto de Melo, Guilherme | `geam` | Desenvolvedor(a) Back-End I | PSU BR | 08:00-17:00 |
| da Silva, Michelle Carla | `maiv` | Analista de Teste I | PSU BR Indirect | 08:30-17:30 |

O regulamento chama todos de **Builders**, independentemente da funcao exercida.

Time multidisciplinar - 1 negocio, 1 front, 1 back, 1 teste - exatamente o que o regulamento incentiva (sec. 8). Senioridade: Negocios III, Front-End II, Back-End I, Teste I; a musculatura de engenharia esta em niveis I e II, o que e mais um argumento para cortar escopo com firmeza.

Tres jornadas diferentes, com sobreposicao comum aproximada de **09:00 as 17:00** - relevante para agendar as poucas decisoes sincronas necessarias. E a participacao e voluntaria: dedicacao em expediente depende de ciencia e autorizacao do gestor imediato (sec. 10), e nao se pode exigir dedicacao fora da jornada.

### A lacuna de dominio - o achado mais importante desta secao

**Nenhum integrante e da Business Unit de Capital Markets.** Todos os quatro sao PSU BR, e nenhum dos quatro cargos e papel de dominio de mercado de capitais.

Isso importa porque o juri inclui a lideranca de Negocios/Delivery da BU de Capital Markets, "Aderencia ao Mercado de Capitais" e criterio de primeira classe, e Valor de Negocio vale 25%. O `IDEAS.md` ja avisava, em agosto: *um pitch sobre um fluxo que o time nunca viu soa generico, nao importa quao bom seja o agente*.

**Consequencia direta para a recomendacao de vestir o dominio:** ela segue valida, mas **deixa de ser gratuita**. Sem revisao de alguem de Capital Markets, a pele de dominio passa de ativo a passivo - um juri de lideranca de CM identifica detalhe inventado mais rapido do que penalizaria uma demo generica e honesta.

**A acao que fecha a lacuna, e e a de maior alavancagem disponivel hoje:** uma conversa de 30 a 60 minutos com uma pessoa da BU de Capital Markets, para validar o cenario da demo, o vocabulario e o formato dos relatorios. Isso **nao** viola o limite de 4 integrantes - consultar alguem nao a torna integrante da equipe. Perfil natural para conduzir: o Agent Lead, por ser Analista de Negocios e por ja ser o canal externo do time.

Apoio publico enquanto isso: manuais e procedimentos operacionais da B3 sobre custodia e liquidacao, guias operacionais da ANBIMA, dados abertos da CVM.

**Plano B, se a revisao nao acontecer:** manter o enquadramento horizontal do formulario como narrativa principal e escolher um cenario de custodia deliberadamente simples e bem documentado publicamente, em vez de simular profundidade que o time nao tem. Perde nota em Aderencia, mas nao perde credibilidade - que e o dano mais caro diante deste juri.

### Como os papeis encaixam no trabalho

A boa noticia: esta composicao encaixa bem na arquitetura recomendada.

| Integrante | O que faz sentido assumir |
|---|---|
| **Raffaele** - Negocios III | O **catalogo semantico** (e artefato de vocabulario de negocio antes de ser codigo) e os **playbooks** (processo de negocio declarativo). Mais o one-pager, as premissas do numero, a entrevista com Capital Markets, o pitch e o envio. |
| **Guilherme** - Back-End I | O **backend deterministico** no Cloud Run: validacao de spec, execucao, arquivo e manifesto. Conectores mockados. Camada de join no BigQuery. |
| **Jeferson** - Front-End II | A camada de conversa e apresentacao - **UX vale 15%**. O passo de **mostrar o plano antes de executar** e o **manifesto de procedencia na tela**: dois dos tres diferenciais recomendados sao trabalho de front-end. |
| **Michelle** - Teste I | Provar o invariante **"nenhum numero que nao tenha vindo de tool"** - e afirmacao testavel, e ter quem a comprove transforma promessa em evidencia. Mais os tres caminhos de falha da V1, as verificacoes de consistencia do playbook, e um roteiro de demo repetivel. |

Dois pontos que valem destacar. Primeiro: **dois dos tres diferenciais da avaliacao sao front-end** - o que normalmente e camada de acabamento e, aqui, onde a nota se ganha. Segundo: o **invariante anti-alucinacao e o argumento mais forte da proposta para um juri de setor regulado, e o unico que pode ser demonstrado em vez de afirmado** - ter QA no time e o que viabiliza isso, e quase nenhum time de hackathon tem.

O ponto de carga e o **backend**: nivel I carregando o nucleo deterministico em cerca de 12 dias, com trabalho principal em paralelo. Se algo tem de sair, sai daqui - e **V2.3 com join arbitrario e a primeira coisa a cortar**.

#### O que muda por existir um Agent Lead

Cabe ao Agent Lead, e nao a qualquer integrante (sec. 4.4 e 8):

- representar oficialmente a equipe
- ter realizado a inscricao
- **efetuar o envio das entregas ate 30/09**
- **manter a comunicacao com a Organizacao** - logo e por este canal que se pede o Guia Tecnico
- assegurar o cumprimento dos prazos

Duas consequencias praticas. Primeira: **pedir o Guia Tecnico e tarefa do Agent Lead**, nao de quem tiver tempo - o canal com a Organizacao e atribuicao formal do papel. Segunda: **o envio de 30/09 tem ponto unico de falha.** Vale combinar por escrito um plano B caso haja indisponibilidade na data, e nao deixar o envio para o proprio dia 30.

#### Aritmetica do premio com 4 integrantes

Dividido igualmente entre os integrantes **elegiveis**; rateio desigual e proibido.

| Colocacao | Total | Por pessoa |
|---|---|---|
| 1o | R$ 3.000 | **R$ 750** |
| 2o | R$ 2.000 | R$ 500 |
| 3o | R$ 1.000 | R$ 250 |

A parcela de integrante inelegivel na data da concessao e **perdida e nao redistribuida**. Com 4 pessoas, um inelegivel custa R$ 750 que ninguem recebe, em caso de primeiro lugar. A conferencia de elegibilidade e individual e vale **ate a divulgacao do resultado**, nao apenas na inscricao.

## Guia Tecnico - nao existe

A Organizacao respondeu em **12/08** que **nao ha Guia Tecnico separado**: e a pagina do SharePoint mais o que ja esta no regulamento, nada alem. Transcricao em `GUIA_TECNICO_RESPOSTA.md`.

Tres consequencias:

1. **O bloqueio mais antigo do projeto esta encerrado.** A especificacao tecnica completa e o que o time ja tem: regulamento sec. 12 (Gemini Enterprise + GCP, obrigatorio sob pena de desclassificacao), sec. 13 (dados), sec. 14 (seguranca da informacao) e a pagina do SharePoint (entregaveis, cronograma, criterios). **Nada mais vai chegar.**

2. **A arquitetura sugerida deixou de correr risco de invalidacao.** A ressalva que a acompanhava em `oneask/AVALIACAO.md` cai - nao ha documento por vir. E nao existe template nem rubrica para o diagrama de arquitetura: o SharePoint pede "diagrama simplificado" e nada alem, entao o time define o que isso quer dizer.

3. **Privacidade e seguranca de dados sao expectativa nomeada da Organizacao.** A frase final da resposta - *"que as pessoas cuidem da questao de privacidade de dados, seguranca e afins"* - e a unica exigencia que a Organizacao acrescentou de proprio punho. Isso promove as regras de dados de clausula no PDF a pedido explicito de quem organiza.

> **Nota de processo.** A resposta e de 12/08, o mesmo dia do primeiro checkpoint deste repositorio, que nunca a registrou. O projeto carregou "Guia Tecnico nao obtido" como principal risco tecnico por quase um mes com a questao ja respondida. Resposta obtida em chat precisa aterrar no repositorio no mesmo dia.

## O que o texto submetido muda

Detalhamento em `oneask/AVALIACAO.md`, secao 0.1. Tres fatos, e os dois primeiros corrigem decisoes anteriores.

**1. A proposta e horizontal - e o texto e neutro de dominio, nao errado de dominio.** Nao ha uma unica palavra de Mercado de Capitais nos tres campos: o problema fala de "atividades operacionais", o publico-alvo e "equipes de operacoes, negocio e tecnologia". Isso **confirma** a fragilidade em Aderencia ao Mercado de Capitais que antes era suspeita.

Mas neutro nao e contrario. Se o formulario dissesse "e-commerce", a correcao estaria travada; como ele diz "diferentes sistemas", demonstrar num caso de custodia **evidencia o texto em vez de contradizer**. Logo a correcao segue valida, com uma restricao nova: **a afirmacao horizontal precisa sobreviver**, no lugar onde ela rende nota - Escalabilidade, 15%. O enquadramento generico deixa de ser passivo e passa a ser a historia de escala.

| Momento do pitch | Conteudo | Ancoragem |
|---|---|---|
| Problema | Relatorios fragmentados entre sistemas, e o gargalo persiste **mesmo onde ja existem APIs** | campo 7, quase literal |
| Onde doi mais - a demo | Custodia e pos-negociacao: investigacao de divergencia de posicao | instancia do campo 7 |
| Mecanismo | Catalogo semantico, playbooks e conectores configuraveis | campo 8, quase literal |
| Escala | Mesmo motor, qualquer dominio: operacoes, negocio e tecnologia | campo 9, literal |

**2. O texto submetido promete V3, nao V1.** O campo 8 diz que o agente "interpreta a necessidade do usuario, **identifica quais relatorios e fontes sao necessarios**, determina os parametros da consulta e orquestra as extracoes". Isso e a V3 do documento de evolucao. A V1 daquele documento parte da premissa oposta e explicita: *"o usuario sabe qual relatorio deseja"*.

Existe portanto uma **lacuna entre o escopo submetido e o plano de MVP**. Consequencia, e ela corrige o que este arquivo dizia antes: **a V1 sozinha nao e submissao valida.** Um playbook de V3 ponta a ponta deixa de ser diferencial e passa a ser **obrigatorio**. O plano abaixo foi reordenado por isso - e, felizmente, playbook e a parte barata: e configuracao, nao engenharia de dados.

**3. A arquitetura de conectores ja foi prometida.** O campo 8 se compromete com "uma arquitetura de conectores configuraveis, permitindo sua adaptacao a diferentes sistemas, APIs e mecanismos de automacao **sem alterar a experiencia do usuario**". "Sem alterar a experiencia do usuario" e exatamente a propriedade de **catalogo como dado**. O catalogo semantico deixa de ser sugestao de inovacao e passa a ser cumprimento do prometido, e os conectores mockados heterogeneos passam a ser a evidencia de uma afirmacao ja feita ao comite.

**Uma frase do texto vale levar para o one-pager e para a abertura do video:** a fragmentacao persiste "mesmo quando ja existem APIs ou automacoes para parte dessas atividades". Isso preempta a objecao mais obvia de um juri tecnico - *por que nao chamar a API direto?*. O gargalo nao e integracao, e saber o que pedir e onde.

**O que o texto nao resolve:** nao ha numero nele tambem. "Aumenta o esforco operacional" e o adjetivo, no lugar exato onde deveria estar a cifra. O one-pager nao herda nenhum numero do formulario - tem de produzi-lo.

## Segunda opiniao externa

Em 08/09 a avaliacao foi submetida a um modelo externo com instrucao de contestar. Registro completo em `oneask/AVALIACAO.md`, secao 11 - incluindo o que foi **rejeitado** e por que.

Tres achados aceitos, todos ja incorporados acima e em `oneask/AVALIACAO.md`:

1. **Faltava historia de seguranca no diagrama** - e privacidade/seguranca foi a unica exigencia que a Organizacao acrescentou de proprio punho.
2. **Video e demo ao vivo sao pecas diferentes**, para plateias e prazos diferentes. O roteiro do video vem primeiro.
3. **A conta de horas de backend nao fechava** - o corte de escopo anterior era insuficiente.

Uma rejeicao merece destaque, porque a tentacao volta quando o prazo aperta: a sugestao de **rodar o backend localmente atras de tunel**. Sec. 12 exige o agente executavel e disponivel para avaliacao **no padrao Gemini Enterprise/GCP**, e isso e gatilho explicito de desclassificacao. Cloud Run e um comando de deploy.

## Datas duras

**30/09** e o ultimo dia para enviar o agente - **22 dias corridos** a partir desta data. Descontando a janela de entregaveis, **restam cerca de 12 dias reais de construcao**.

Depois: avaliacao do juri de 01/10 a 15/10, finalistas em **16/10**, apresentacao final e votacao do publico em **28/10**.

Cronograma completo em `RULES.md`.

## Caminho critico

1. ~~Confirmar o que a proposta submetida declara.~~ **Feito em 08/09** - `oneask/PROPOSTA_SUBMETIDA.md`.
2. **Fechar o escopo minimo como V1 mais um playbook de V3**, nao V1 sozinha. E o que o campo 8 do formulario prometeu, e e a decisao que reordena o cronograma. Esta e a acao numero um.
3. ~~Solicitar o Guia Tecnico.~~ **Resolvido: nao existe.** A Organizacao respondeu em 12/08 que o guia tecnico e a pagina do SharePoint mais o regulamento, nada alem. Ver `GUIA_TECNICO_RESPOSTA.md`. **A arquitetura sugerida deixou de correr risco de invalidacao** - nao ha documento por vir.
4. **Agendar a revisao do cenario com alguem da BU de Capital Markets.** Nenhum integrante e de CM - sem essa revisao, a manchete de custodia fica sem lastro diante de um juri que e justamente de CM. Ver "A lacuna de dominio".
5. **Confirmar se o GitHub usado pelo time e ambiente homologado** para o codigo do desafio. Sec. 14 veda plataformas nao homologadas e determina que todo material permanece nos ambientes indicados pela Organizacao; sec. 15 torna o codigo patrimonio da GFT; sec. 20 faz da violacao gatilho de desclassificacao. Padrao seguro: repositorio gerido pela GFT, ou o proprio projeto GCP.
6. **Congelar a definicao de pronto da V1** (abaixo). E a defesa contra o risco mais provavel do projeto: escopo espalhado por V1, V2 e V3 sem nenhum completo em 30/09.
7. **Fechar o numero de impacto.** Nem o documento OneAsk nem o formulario tem um unico numero. O desempate do juri e por valor agregado ao negocio, e a votacao final e do publico. Sem numero, "ganho de eficiencia" e adjetivo.
8. **Vestir o dominio, sem perder a afirmacao horizontal.** Exemplos de V1 e V2 em custodia, divergencia de posicao como caso de abertura, e o alcance amplo mantido como argumento de escala.
9. **Confirmar a aprovacao pelo comite e o nome do time registrado nos 4 formularios** - com o Agent Lead, que realizou a inscricao.
10. **Cada integrante confere a propria elegibilidade** e a autorizacao do gestor para dedicacao em expediente. A elegibilidade vale ate a divulgacao do resultado.

## Avaliacao da direcao atual, em resumo

Detalhamento completo em `oneask/AVALIACAO.md`. Veredito: **tecnicamente bem pensada e estrategicamente mal posicionada.**

Esta certo, e nao e pouco: a premissa de que o agente cuida de entendimento, decisao e orquestracao, enquanto backend e tools cuidam de operacoes deterministicas. E a divisao que o Gemini Enterprise faz bem e que um juri tecnico premia, porque mostra um time que sabe onde o LLM **nao** deve entrar.

Esta em risco: a proposta, como escrita, **poderia ser de qualquer setor**. O unico momento genuinamente de Mercado de Capitais no documento e o exemplo da V3 - divergencia de posicao exigindo Position, Transaction e Movement Report, que e reconciliacao de custodia (dores P2/P3, solucao candidata B5) - e esta enterrado na secao 5 de 8. Isso ataca ao mesmo tempo Inovacao (25%) e Aderencia ao Mercado de Capitais (criterio de primeira classe na redacao do SharePoint).

As tres correcoes de maior impacto:

| # | Correcao | Custo | Ganho |
|---|---|---|---|
| C1 | **Vestir o dominio** - exemplos de V1/V2 em custodia, divergencia de posicao como abertura | Baixo em esforco, **mas exige revisao de alguem de Capital Markets** | Move Inovacao e Aderencia juntas. Sem a revisao, vira passivo - ver "A lacuna de dominio" |
| C2 | **Nomear o mecanismo** - catalogo semantico como dado, mais playbooks declarativos para a V3 | Medio | Da a V3 mecanismo demonstravel, torna a V3 barata e auditavel. Responde a pergunta de arquitetura do proprio time |
| C3 | **Manifesto de procedencia** - origem, parametros, filtros e contagem de linhas em todo resultado | Baixo | Em setor regulado, o problema de um numero nao e produzi-lo, e defende-lo |

Junto com C3 vem o invariante que vale escrever no one-pager: **o agente nunca escreve um numero que nao tenha vindo de uma tool.**

## Definicao de pronto da V1 - para congelar

- 1 agente no Gemini Enterprise, 3 tools, 3 relatorios, 2 sistemas de origem distintos
- Caminho feliz completo: pedido -> identifica relatorio -> extrai parametro -> **mostra o plano** -> usuario confirma -> executa -> entrega arquivo mais manifesto
- Tres caminhos de falha tratados: parametro ausente (pergunta), relatorio desconhecido (oferece os candidatos mais proximos do catalogo), resultado vazio (diz que veio vazio e mostra os filtros aplicados)
- Invariante verificado: nenhum numero na tela que nao tenha vindo de tool

Se isso esta de pe, a V1 esta funcional como **fundacao**, mesmo que V2 e V3 nao existam.

**Correcao de 08/09:** este arquivo dizia antes que a V1 sozinha ja seria submissao valida. **Nao e.** O campo 8 do formulario promete identificacao de necessidade - comportamento de V3 - e a V1 sozinha subentrega contra o escopo submetido. O minimo para submeter e **V1 como fundacao mais um playbook de V3 ponta a ponta**.

## Plano ate 30/09

Reordenado em 08/09 apos a leitura do texto submetido: o playbook de V3 subiu de "se houver folga" para **obrigatorio**; o join arbitrario da V2.3 desceu para fora de escopo.

| Janela | Foco | Saida |
|---|---|---|
| 08/09 - 10/09 | Congelar escopo **contra o texto submetido**. Agendar a revisao com Capital Markets. Confirmar homologacao do repositorio de codigo. Fechar as premissas do numero. | Escopo congelado, numero acordado, revisao marcada |
| 08/09 - 15/09 | Catalogo semantico como dado. Dois servicos mockados heterogeneos. V1 ponta a ponta no Gemini Enterprise. | Fundacao pronta |
| 15/09 - 21/09 | **Um playbook de V3 ponta a ponta** - divergencia de posicao, com verificacao de consistencia. V2.1, que sai quase de graca do catalogo. Manifesto de procedencia. Passo de plano e confirmacao. | **A demo que o texto submetido promete** |
| 22/09 - 24/09 | Caixa de seguranca no diagrama. Integracao. **Congelar codigo em 24/09.** | Demo completa |
| 24/09 - 28/09 | **Roteiro do video primeiro**, depois gravacao com take de reserva. One-pager e PDF de arquitetura. | Pacote de submissao |
| 29/09 | Folga deliberada - revisao, ensaio, correcao do que aparecer | Margem |
| 30/09 | Enviar de manha, nao no fim do dia | Submetido |

**Cortes de escopo, aprofundados em 08/09 apos revisao externa** (detalhe em `oneask/AVALIACAO.md` secoes 7 e 11). O nucleo deterministico e trabalho de um unico dev junior em horario voluntario: ordem de 60 a 80 horas disponiveis contra mais de 120 na lista original. Fora, portanto:

| Fora de escopo | Por que |
|---|---|
| **BigQuery** | Acervo mockado e minusculo; join em memoria (DuckDB) no proprio Cloud Run resolve. Zero valor de demo |
| **V2.3 com join arbitrario** | O playbook cobre o join da demo, com chaves fixas |
| **Terceiro conector (XML)** | Dois de naturezas opostas ja provam a abstracao prometida no campo 8 |
| **V2.2 como capacidade de usuario** | Filtro em linguagem natural nao aparece no roteiro do video; os filtros da demo vivem no playbook |

**A folga de 29/09 e proposital.** Folga zero em projeto voluntario com prazo duro nao e plano - e a primeira coisa que quebra.

A ordem de construcao V2.1 -> V2.2 -> V2.3 esta correta **como sequencia**, e o motivo e estrutural: cada incremento adiciona *um conjunto de campos ao mesmo catalogo* (colunas e rotulos; tipos e dominios; chaves de join). Isso continua valendo mesmo com a V2.3 fora de escopo - se ela voltar, volta nessa posicao, nunca antes da V2.2.

E construir de baixo para cima nao e o mesmo que **contar** de baixo para cima: o pitch abre pela necessidade de negocio.

Observacao contraintuitiva: os **playbooks da V3 sao mais faceis** que a V2.3 aberta. Playbook e configuracao; join arbitrario e problema de engenharia de dados. Se o prazo apertar, cortar V2.3 aberta e manter o playbook - o resultado demonstravel e melhor.

## Entregaveis - 100% do que o juri ve

A pagina do Loop planeja evolucao de produto e nao menciona nenhum dos quatro. E aqui que times perdem pontos, nao no modelo.

| Entregavel | O que nao pode faltar |
|---|---|
| One-pager (PDF) | O numero. A dor em uma frase reconhecivel por quem e de Capital Markets |
| Video com pitch e demo | **Escrever o roteiro ANTES de construir o resto.** A plateia que decide o 1o lugar em 28/10 ve o video, nao a arquitetura - e sao duas pecas para duas plateias (`oneask/AVALIACAO.md` secao 8). Take de reserva gravado |
| Demo funcional | Rodando em Gemini Enterprise, nao em notebook local |
| Arquitetura (PDF) | A fronteira LLM/deterministico **desenhada** - e o argumento de viabilidade tecnica em forma visual. Mais a **caixa de seguranca e conformidade**, comecando por "o agente nunca ve dado bruto, so referencia". Nomear as primitivas GCP concretas: o parceiro Google esta no juri |

## Fase final - 16/10 a 28/10

Se selecionado entre os tres finalistas, refazer o pitch para uma plateia **nao tecnica**: a sala e que vota. Abrir pela dor, mostrar o agente funcionando ao vivo, fechar em um numero. A coreografia recomendada esta em `oneask/AVALIACAO.md`, secao 8 - o passo que mostra o plano antes de executar e o que separa a demo de um chatbot, e o passo que fecha no numero e o que ganha voto.

## Questoes abertas

1. **O time aceita o escopo minimo como V1 mais um playbook de V3, em vez de V1 sozinha?** Questao numero um - ela define o cronograma.
2. **Quem, na BU de Capital Markets, pode revisar o cenario da demo em 30 a 60 minutos?** Sem isso a manchete de custodia fica sem lastro.
3. **O GitHub usado pelo time e ambiente homologado para o codigo do desafio?** Sec. 14, 15 e 20 - classe de gatilho de desclassificacao.
4. Qual o nome do **time** registrado nos formularios, e os 4 digitaram a mesma grafia?
5. A proposta foi aprovada pelo comite na selecao encerrada em 01/09?
6. As licencas Gemini Enterprise foram liberadas? O chat de 08/09 mostra um problema de acesso resolvido as 10h27 que **pode** ter sido exatamente isso - confirmar.
7. Os 4 integrantes seguem elegiveis, e seguirao ate a divulgacao do resultado?
8. Os gestores imediatos deram ciencia e autorizacao para dedicacao em expediente (sec. 10)?
9. Qual caso de custodia vira a demo?
10. Qual o conjunto de premissas do numero de impacto?

**Respondidas em 08/09, e por isso fora da lista:** o que a proposta submetida declara (`oneask/PROPOSTA_SUBMETIDA.md`); quem esta no time, quem e o Agent Lead e quais sao os papeis profissionais (ver "O time"); e se o Guia Tecnico foi obtido - nao existe (`GUIA_TECNICO_RESPOSTA.md`).

## Pontos que vale nao esquecer

- **Plataforma**: o agente final tem de estar implementado, configurado, integrado, executavel e disponivel para avaliacao nos padroes Gemini Enterprise + GCP. Fora disso, desclassificacao. Nao ha requisito tecnico adicional a descobrir - ver `GUIA_TECNICO_RESPOSTA.md`.
- **Ambientes**: sec. 14 determina que todo material permanece nos ambientes indicados pela Organizacao, e veda plataformas nao homologadas. Codigo do desafio e patrimonio da GFT (sec. 15) e nao deve viver em conta pessoal.
- **Dados**: mock e sintetico sao explicitamente permitidos, o que valida a premissa do OneAsk. E privacidade e seguranca de dados foram o **unico pedido que a Organizacao acrescentou de proprio punho** ao responder sobre o Guia Tecnico. Mas `customer_name` no exemplo da V2.3 e um convite a alguem popular a base com nome de cliente real - mock ostensivamente sintetico, e dito em voz alta para o time. Violacao e desclassificacao imediata.
- **Credibilidade da demo**: uma integracao publica real dentro do mundo mockado (PTAX/Bacen para conversao de moeda, por exemplo) custa quase nada e quebra o cheiro de "esta tudo mockado".
- O premio e por projeto, dividido igualmente entre os 4; rateio desigual e proibido independentemente da contribuicao individual. Primeiro lugar da **R$ 750 por pessoa**, e a parcela de integrante inelegivel **nao** e redistribuida.
- Elegibilidade vale **ate a divulgacao do resultado**, nao apenas na inscricao.
- Toda a propriedade intelectual e da GFT - cessao gratuita, total e irrevogavel. A autoria recebe apenas reconhecimento institucional.
- Tudo sobre o desafio e confidencial, explicitamente incluindo os criterios de avaliacao e os resultados preliminares. Manter estes arquivos internos.
- O regulamento chama cada integrante de **Builder** e o representante de **Agent Lead** - usar esse vocabulario no pitch soa como fluencia nas regras.
