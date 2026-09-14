# Plano - Desafio Capital Markets AI Agents Challenge (SMC 2026)

Data do checkpoint: **14/09/2026**. Versao legivel por maquina: `checkpoint.json` (v10, 11/09) - **desatualizado em relacao a este arquivo**: nao incorpora ainda o backlog de 14/09 nem `oneask/REFINAMENTO_ANALISE.md`.
Arquivos companheiros: `APROVACAO.md` (o e-mail de aprovacao e o que ele muda), `RULES.md` (resumo do regulamento), `IDEAS.md` (espaco de problemas e catalogo de solucoes), `NAMES.md` (historico dos candidatos a nome do time - encerrado em OneAsk), `oneask/` (a solucao em construcao, o texto submetido e a avaliacao).

> Este arquivo esta em pt-BR sem acentuacao (ASCII puro), para nao quebrar em formularios, nomes de arquivo e terminais.

## O que mudou desde 12/08

O checkpoint anterior dizia que nada estava decidido. Isso ja nao e verdade: existe um MVP com direcao definida, chamado **OneAsk - Agente Inteligente de Extracao de Dados**, documentado em pagina do Microsoft Loop e extraido para `oneask/OneAsk_Proposta_Evolucao_MVP.md`.

A recomendacao de agosto (**A3 Covenant Watch**, vice **B4 Normalizador de eventos corporativos**) esta **superada**. Fica preservada em `checkpoint.json`, em `direcao_da_solucao.recomendacao_anterior_agosto_2026`, e o catalogo de dores P1-P5 e de solucoes A1-D9 em `IDEAS.md` segue valido como referencia de espaco de problemas.

**Atualizacao de 08/09:** o texto submetido no formulario foi obtido e esta em `oneask/PROPOSTA_SUBMETIDA.md` (campos 7, 8 e 9 - "Dados do Agente"). Isso destrava o que era a questao numero um do projeto e **corrige duas decisoes de escopo** - ver "O que o texto submetido muda", abaixo.

**Atualizacao de 11/09: a proposta foi APROVADA.** E-mail da Organizacao em 10/09, 12h30, aos quatro integrantes. Transcricao fiel e analise em `APROVACAO.md`. O e-mail traz tres coisas que mudam o plano - ver "A aprovacao, e as tres coisas que vieram com ela", abaixo.

**Atualizacao de 14/09: existe backlog.** O Agent Lead publicou no Loop uma segunda pagina - **"OneAsk - Proposta de Estrutura de Refinamento"** - consolidando a escada V1/V2/V3 em **1 Epic, 3 Features e 7 User Stories**, e pediu ao time validacao de representatividade e granularidade, mais cinco confirmacoes de comportamento. Extracao fiel em `oneask/OneAsk_Proposta_Estrutura_Refinamento.md`; analise, linha de corte e respostas em `oneask/REFINAMENTO_ANALISE.md`.

Em uma linha: **a quebra esta certa na forma e faltam quatro coisas** - a V3 nao tem US para o seu mecanismo (o playbook), nao ha verificacao de consistencia em lugar nenhum, o invariante anti-alucinacao nao esta escrito como requisito, e **nenhum item do backlog tem formato de entregavel**. Mais uma quinta, de ordenacao: as US02 e US05 sao **V2.2 e V2.3 com nome novo** - os dois itens cortados do escopo em 08/09 - e sem linha de corte explicita o corte se desfaz sem ninguem decidir desfaze-lo.

## Onde estamos

| Item | Situacao |
|---|---|
| Regulamento lido | Feito |
| Direcao de problema e solucao | **Travada pelo formulario** - `oneask/PROPOSTA_SUBMETIDA.md`. O que segue em discussao e o plano de evolucao V1/V2/V3 |
| Fase | **Construcao do agente** - janela 13/08 a 30/09, **aberta desde 13/08**. Em 14/09 restam **16 dias corridos** ate 30/09, e **9 dias uteis** ate o congelamento de codigo em 24/09 |
| Backlog | **Existe desde 14/09** - 1 Epic, 3 Features, 7 US (`oneask/OneAsk_Proposta_Estrutura_Refinamento.md`). **Sem linha de corte definida**, e sem nenhum item com formato de entregavel |
| Proposta submetida no formulario | **Confirmada** - texto em `oneask/PROPOSTA_SUBMETIDA.md` |
| Proposta aprovada pelo comite | **APROVADA** - e-mail da Organizacao em 10/09 (`APROVACAO.md`) |
| Ambiente do codigo | **Resolvido: GitLab da GFT**, diretorio da equipe. **Acesso nao confirmado** - era para ate ~18/08 |
| Campos 1 a 6 do formulario | **Nao vistos** - o nome do time foi confirmado por fora, pelo Agent Lead |
| Composicao do time | **Confirmada - 4 integrantes, o maximo permitido** (ver abaixo) |
| Agent Lead | **Raffaele Brivio** |
| Nome do time registrado | **OneAsk** - confirmado em 09/09. Time e produto tem o mesmo nome |
| Inscricao individual dos 4 | **Somente o Agent Lead consta.** Regularizacao dos outros 3 pedida pela Organizacao em 09/09 - ver abaixo |
| Licencas Gemini Enterprise | Recebimento nao confirmado |
| Guia Tecnico | **Resolvido - nao existe** como documento separado. Ver `GUIA_TECNICO_RESPOSTA.md` |
| Os **cinco** entregaveis obrigatorios | Nao iniciados, exceto a demo (V1 em construcao). **Sao cinco, nao quatro** - ver `APROVACAO.md` |

Em `checkpoint.json`, `null` significa **nao confirmado**, nao `false`. A distincao importa: parte do trabalho avancou fora deste repositorio.

## A aprovacao, e as tres coisas que vieram com ela

A proposta foi **aprovada**. E-mail da Organizacao (Evelim Ribeiro) em **10/09, 12h30**, enderecado aos quatro integrantes, com copia para Miotta, Kato e Bueno. Transcricao fiel e analise completa em `APROVACAO.md`.

Isso encerra a questao aberta numero cinco deste arquivo. Mas o e-mail nao e so uma boa noticia - ele carrega tres mudancas materiais, e uma armadilha de leitura.

**1. Sao cinco entregaveis obrigatorios, nao quatro.** A pagina do SharePoint lista quatro; o e-mail lista cinco. O novo e **"GitLab GFT: artefatos de desenvolvimento no diretorio da sua equipe"**. Este arquivo dizia "os quatro entregaveis" em quatro lugares diferentes - estava errado. E o quinto entregavel nao e um documento a produzir na ultima semana: e onde o trabalho tem de estar acontecendo *durante* a construcao. Um unico commit em 29/09 entrega o artefato e nao entrega a evidencia de processo que um diretorio versionado existe para dar.

**2. O ambiente homologado do codigo tem nome: GitLab da GFT.** Era o item 5 do caminho critico e a questao aberta 3 - *"o GitHub usado pelo time e ambiente homologado?"*. **Respondida.** Sec. 14 manda que todo material permaneca nos ambientes indicados pela Organizacao; a Organizacao indicou. O risco vira tarefa, com uma cobranca urgente colada nela: **a liberacao do GitLab era para ate 3 dias uteis a partir de 13/08 - por volta de 18/08 - e passou quase um mes.** Se o acesso nao chegou, cobrar hoje. Diretorio sem acesso e entregavel obrigatorio que nao existe.

**3. O padrao Google Enterprise AI vale para todos os entregaveis.** O e-mail e mais especifico que o SharePoint: *"o padrao Google Enterprise AI e obrigatorio em todos os entregaveis. Projetos fora desse padrao serao desclassificados."* Nao basta o agente rodar em Gemini Enterprise - o PDF de arquitetura precisa nomear primitivas Google concretas, o video precisa mostrar a solucao no padrao, e o one-pager nao deve ser agnostico de plataforma. O que era tatica de nota (o parceiro Google esta no juri) passou a ser requisito de conformidade.

### A armadilha: "dia 13" e 13/08, e ja passou

O e-mail diz que o desenvolvimento vai **de 13/08 a 30/09** e que o acesso ao Gemini Enterprise seria liberado **em 13/08**. Isso nao e data nova nem erro de digitacao: e o cronograma publicado no SharePoint desde 05/08 (ver `RULES.md`). O e-mail chegou em **10/09** repetindo um calendario que comecou 28 dias antes - a aprovacao veio com quase um mes da janela ja consumido.

A leitura no Teams foi *"dia 13 comeca"*. **Nao comeca - ja comecou.** 13/09/2026 cai num domingo; 13/08 era a quinta-feira seguinte ao kickoff de 12/08.

Por que vale gastar um paragrafo nisso: quem le "comeca dia 13" acredita ter a janela inteira pela frente, e quem acredita nisso nao sente urgencia nenhuma nos proximos dois dias. A conta real esta em "Datas duras", abaixo - e ela e curta.

### O que a aprovacao **nao** resolve

O e-mail e sobre a proposta, nao sobre inscricao. **Ele nao e o aceite formal das tres inscricoes individuais faltantes** - embora estar enderecado aos quatro seja indicio relevante de que a Organizacao trata o time como quarteto formado. A premiacao alcanca apenas integrantes **inscritos** e elegiveis (sec. 19), entao a cobranca da secao seguinte continua de pe.

Tambem nao confirma que as licencas Gemini Enterprise estao efetivamente liberadas: o e-mail diz "sera liberado em 13/08" - futuro, sobre data no passado.

### Um canal novo, e uma licao que ja custou caro

O e-mail anuncia um **grupo exclusivo com os Agent Builders aprovados**, para orientacoes, cronograma e duvidas. Duas providencias: garantir que o Agent Lead esteja nele (sec. 4.4 - a comunicacao com a Organizacao e atribuicao formal do papel), e **aterrar no repositorio, no mesmo dia, o que for dito ali**. Foi exatamente assim que a resposta sobre o Guia Tecnico ficou quase um mes fora do repositorio enquanto o projeto tratava o assunto como principal risco tecnico.

## A lacuna de inscricao - aberta em 09/09

A Organizacao (Evelim Ribeiro) conferiu os formularios e **nao encontrou a inscricao de 3 dos 4 integrantes**. Somente a do Agent Lead consta.

Causa: a inscricao era **individual** - sec. 7 do regulamento, reforcado na pagina do SharePoint (*todos os participantes preenchem o formulario, inclusive quem participa em equipe*). O Agent Lead submeteu um formulario de grupo, com participacao em quarteto, nome do time e os quatro e-mails; os outros tres entenderam que aquela submissao registrava a equipe inteira, e nenhum preencheu o proprio.

O que a Organizacao pediu, em 09/09 as 11h00: que **cada integrante faltante envie um e-mail ate as 13h do mesmo dia**, explicando que perdeu o prazo de inscricao e o motivo, e respondendo as perguntas que estavam no formulario. Destinatario: `evelim.ribeiro@gft.com`, com copia para Vitor Miotta, Carlos Kato e Thiago Bueno.

Por que e risco alto, e nao burocracia: a premiacao e dividida entre os integrantes **inscritos** e elegiveis (sec. 19), e a parcela de quem nao se qualifica **nao e redistribuida** ao resto do time. Enquanto a regularizacao nao for aceita, tres dos quatro nao constam como inscritos - o que expoe mais do que a premiacao.

**Status:** regularizacao pedida em 09/09, com prazo de 13h no mesmo dia. **Envio dos tres e-mails e aceite pela Organizacao: nao confirmados** - e o proximo item a cobrar, pelo canal do Agent Lead.

**Licao de processo, a mesma de 12/08:** a exigencia de inscricao individual estava escrita em `RULES.md` desde o primeiro checkpoint - *"a inscricao e individual - todos os participantes preenchem o formulario, inclusive quem participa em equipe"* - e ainda assim passou. Regra lida nao e regra cumprida enquanto ninguem confirma a execucao, um a um.

## O time

Quatro integrantes - **o maximo que o regulamento permite** (sec. 4.3: de 2 a 4). O time esta cheio: nao cabe mais ninguem, e a substituicao de integrantes so era permitida ate a data limite do cronograma oficial, que ja passou.

| Integrante | Usuario | Cargo | Unidade | Jornada |
|---|---|---|---|---|
| **Brivio, Raffaele** - Agent Lead | `rebv` | Analista de Negocios III | PSU BR | 09:00-18:00 |
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

**30/09** e o ultimo dia para enviar o agente - **20 dias corridos** e **14 dias uteis** a partir desta data.

A conta que importa nao e essa, e a de construcao. Com congelamento de codigo em 24/09, restam **10 dias uteis de construcao** (11/09 a 24/09) e **4 dias uteis para os entregaveis** (25/09 a 30/09). E trabalho voluntario, fora ou dentro do expediente conforme autorizacao do gestor - logo 10 dias uteis nao sao 80 horas por pessoa.

A janela **abriu em 13/08** e ja consumiu cerca de 60% do prazo. O e-mail de aprovacao, que chegou em 10/09 repetindo "13/08 a 30/09", nao move essa data - ver "A armadilha", acima.

Depois: avaliacao do juri de 01/10 a 15/10, finalistas em **16/10**, apresentacao final e votacao do publico em **28/10**.

Cronograma completo em `RULES.md`.

## Caminho critico

1. ~~Confirmar o que a proposta submetida declara.~~ **Feito em 08/09** - `oneask/PROPOSTA_SUBMETIDA.md`.
2. **Fechar o escopo minimo como V1 mais um playbook de V3**, nao V1 sozinha. E o que o campo 8 do formulario prometeu, e e a decisao que reordena o cronograma. Esta e a acao numero um.
3. ~~Solicitar o Guia Tecnico.~~ **Resolvido: nao existe.** A Organizacao respondeu em 12/08 que o guia tecnico e a pagina do SharePoint mais o regulamento, nada alem. Ver `GUIA_TECNICO_RESPOSTA.md`. **A arquitetura sugerida deixou de correr risco de invalidacao** - nao ha documento por vir.
4. **Agendar a revisao do cenario com alguem da BU de Capital Markets.** Nenhum integrante e de CM - sem essa revisao, a manchete de custodia fica sem lastro diante de um juri que e justamente de CM. Ver "A lacuna de dominio".
5. ~~Confirmar se o GitHub usado pelo time e ambiente homologado.~~ **Respondido em 10/09: o ambiente e o GitLab da GFT**, em diretorio da equipe (`APROVACAO.md`). No lugar disso, duas acoes novas, ambas urgentes: **(a) cobrar o acesso ao GitLab** - era para ate ~18/08 e nao chegou confirmacao; **(b) comecar a versionar os artefatos ali**, porque o diretorio da equipe e o **quinto entregavel obrigatorio**, e ele e avaliado pelo que contem em 30/09.
6. **Congelar a definicao de pronto da V1** (abaixo). E a defesa contra o risco mais provavel do projeto: escopo espalhado por V1, V2 e V3 sem nenhum completo em 30/09.
7. **Fechar o numero de impacto.** Nem o documento OneAsk nem o formulario tem um unico numero. O desempate do juri e por valor agregado ao negocio, e a votacao final e do publico. Sem numero, "ganho de eficiencia" e adjetivo.
8. **Vestir o dominio, sem perder a afirmacao horizontal.** Exemplos de V1 e V2 em custodia, divergencia de posicao como caso de abertura, e o alcance amplo mantido como argumento de escala.
9. ~~Confirmar a aprovacao pelo comite.~~ **Feito - APROVADA em 10/09** (`APROVACAO.md`). O nome do time esta confirmado: **OneAsk** - o proprio e-mail abre com "Ola OneAsk!".
9b. **Confirmar com a Organizacao o aceite das inscricoes individuais regularizadas em 09/09** - ver "A lacuna de inscricao". Sem aceite, 3 dos 4 integrantes nao constam como inscritos. O e-mail de aprovacao aos quatro e indicio, **nao e aceite**.
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
| ~~08/09 - 10/09~~ | ~~Congelar escopo contra o texto submetido. Agendar a revisao com Capital Markets. Confirmar homologacao do repositorio. Fechar as premissas do numero.~~ **Vencida.** A homologacao do repositorio foi respondida de fora (GitLab GFT); o resto segue pendente e foi empurrado para a linha abaixo | - |
| **11/09 - 12/09** | **Cobrar acesso ao GitLab e as licencas Gemini Enterprise** - ambos com prazo estourado desde agosto. Abrir o diretorio da equipe e subir o primeiro artefato. Congelar escopo **contra o texto submetido**. Agendar a revisao com Capital Markets. Fechar as premissas do numero. | Acessos cobrados por escrito, diretorio do GitLab vivo, escopo congelado, numero acordado, revisao marcada |
| 11/09 - 15/09 | Catalogo semantico como dado. Dois servicos mockados heterogeneos. V1 ponta a ponta no Gemini Enterprise. **Tudo versionado no GitLab desde o primeiro commit.** | Fundacao pronta |
| 15/09 - 21/09 | **Um playbook de V3 ponta a ponta** - divergencia de posicao, com verificacao de consistencia. V2.1, que sai quase de graca do catalogo. Manifesto de procedencia. Passo de plano e confirmacao. | **A demo que o texto submetido promete** |
| 22/09 - 24/09 | Caixa de seguranca no diagrama. Integracao. **Congelar codigo em 24/09.** | Demo completa |
| 24/09 - 28/09 | **Roteiro do video primeiro**, depois gravacao com take de reserva. One-pager e PDF de arquitetura. **Os tres no padrao Google Enterprise AI** - o e-mail de aprovacao exige isso de todos os entregaveis, nao so do agente. | Pacote de submissao |
| 29/09 | Folga deliberada - revisao, ensaio, correcao do que aparecer. **Conferir o diretorio do GitLab como se fosse entregavel - porque e.** | Margem |
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

**Sao cinco, nao quatro.** A pagina do SharePoint lista quatro; o e-mail de aprovacao de 10/09 acrescenta o quinto. A pagina do Loop planeja evolucao de produto e nao menciona nenhum deles. E aqui que times perdem pontos, nao no modelo.

| Entregavel | O que nao pode faltar |
|---|---|
| One-pager (PDF) | O numero. A dor em uma frase reconhecivel por quem e de Capital Markets |
| Video com pitch e demo | **Escrever o roteiro ANTES de construir o resto.** A plateia que decide o 1o lugar em 28/10 ve o video, nao a arquitetura - e sao duas pecas para duas plateias (`oneask/AVALIACAO.md` secao 8). Take de reserva gravado |
| Demo funcional | Rodando em Gemini Enterprise, nao em notebook local. A redacao "prototipo navegavel ou simulado" **nao libera** rodar fora do padrao - sec. 12 e o proprio e-mail fecham essa porta |
| Arquitetura (PDF) | A fronteira LLM/deterministico **desenhada** - e o argumento de viabilidade tecnica em forma visual. Mais a **caixa de seguranca e conformidade**, comecando por "o agente nunca ve dado bruto, so referencia". Nomear as primitivas GCP concretas: o parceiro Google esta no juri |
| **GitLab GFT** *(novo, 10/09)* | Artefatos de desenvolvimento no **diretorio da equipe**. Nao e tarefa de ultima semana: e onde o trabalho precisa estar acontecendo durante a construcao. Depende de um acesso que ainda nao foi confirmado - **cobrar hoje** |

**Uma exigencia que atravessa os cinco:** o e-mail de aprovacao diz que *"o padrao Google Enterprise AI e obrigatorio em todos os entregaveis. Projetos fora desse padrao serao desclassificados."* Isso sobe a barra do PDF de arquitetura e do video, que passam a precisar mostrar o padrao, e nao apenas descreve-lo.

## Fase final - 16/10 a 28/10

Se selecionado entre os tres finalistas, refazer o pitch para uma plateia **nao tecnica**: a sala e que vota. Abrir pela dor, mostrar o agente funcionando ao vivo, fechar em um numero. A coreografia recomendada esta em `oneask/AVALIACAO.md`, secao 8 - o passo que mostra o plano antes de executar e o que separa a demo de um chatbot, e o passo que fecha no numero e o que ganha voto.

## Questoes abertas

1. **O acesso ao GitLab da GFT foi provisionado, e qual e o caminho do diretorio da equipe?** Era para ate 3 dias uteis a partir de 13/08 - ou seja, ~18/08 - e nao ha confirmacao. **Sobe para primeira posicao porque o diretorio e entregavel obrigatorio**, e nenhum outro item da lista tem prazo estourado ha um mes.
2. **O time aceita o escopo minimo como V1 mais um playbook de V3, em vez de V1 sozinha?** Ela define o cronograma. **A partir de 14/09 a pergunta tem forma concreta:** qual e a linha de corte entre as 7 US do refinamento? Proposta em `oneask/REFINAMENTO_ANALISE.md` secao 3 - comprometido US04, US01, US06, a US nova do playbook, US03 restrita a um playbook fechado e US05a; esticado US05b e depois US02.
3. **Quem, na BU de Capital Markets, pode revisar o cenario da demo em 30 a 60 minutos?** Sem isso a manchete de custodia fica sem lastro. **Subiu de prioridade em 14/09:** com backlog escrito, essa conversa deixou de ser pre-requisito so da demo e passou a ser **pre-requisito da escrita do Epic** - os exemplos das US01 e US02 continuam genericos e nao ha como congelar vocabulario antes dela.
4. Os tres e-mails de regularizacao de inscricao foram aceitos pela Organizacao? O e-mail de aprovacao aos quatro e indicio, nao aceite.
5. As licencas Gemini Enterprise foram liberadas **para os quatro**? O e-mail de aprovacao diz "sera liberado em 13/08" - futuro, sobre data no passado. O chat de 08/09 mostra um problema de acesso resolvido as 10h27 que **pode** ter sido exatamente isso - confirmar.
6. Os 4 integrantes seguem elegiveis, e seguirao ate a divulgacao do resultado?
7. Os gestores imediatos deram ciencia e autorizacao para dedicacao em expediente (sec. 10)?
8. Qual caso de custodia vira a demo? Ver questao 3 - ela nao se responde sem a revisao de Capital Markets.
9. Qual o conjunto de premissas do numero de impacto?
10. **Quem rastreia os cinco entregaveis?** Nenhum deles aparece no backlog de 14/09, que so tem historias de produto. Dois nao aceitam compressao na ultima semana: o **roteiro do video** precisa vir antes do fim da construcao, e o **diretorio do GitLab** e avaliado pelo historico que acumulou. Ver `oneask/REFINAMENTO_ANALISE.md` secao 2, lacuna 4.

**Respondidas em 08/09, e por isso fora da lista:** o que a proposta submetida declara (`oneask/PROPOSTA_SUBMETIDA.md`); quem esta no time, quem e o Agent Lead e quais sao os papeis profissionais (ver "O time"); e se o Guia Tecnico foi obtido - nao existe (`GUIA_TECNICO_RESPOSTA.md`).

**Respondidas em 10/09 pelo e-mail de aprovacao** (`APROVACAO.md`), e por isso fora da lista: se a proposta foi aprovada pelo comite - **foi**; qual o nome do time registrado - **OneAsk**, o e-mail abre com "Ola OneAsk!"; e se o repositorio usado pelo time e ambiente homologado - a pergunta perdeu o objeto, porque a Organizacao nomeou o ambiente: **GitLab da GFT**.

## Pontos que vale nao esquecer

- **Plataforma**: o agente final tem de estar implementado, configurado, integrado, executavel e disponivel para avaliacao nos padroes Gemini Enterprise + GCP. Fora disso, desclassificacao. Nao ha requisito tecnico adicional a descobrir - ver `GUIA_TECNICO_RESPOSTA.md`.
- **Ambientes**: sec. 14 determina que todo material permanece nos ambientes indicados pela Organizacao, e veda plataformas nao homologadas. **O ambiente indicado para o codigo tem nome desde 10/09: GitLab da GFT, diretorio da equipe.** Codigo do desafio e patrimonio da GFT (sec. 15) e nao deve viver em conta pessoal - e agora estar fora do GitLab tambem significa entregavel obrigatorio faltando.
- **Dados**: mock e sintetico sao explicitamente permitidos, o que valida a premissa do OneAsk. E privacidade e seguranca de dados foram o **unico pedido que a Organizacao acrescentou de proprio punho** ao responder sobre o Guia Tecnico. Mas `customer_name` no exemplo da V2.3 e um convite a alguem popular a base com nome de cliente real - mock ostensivamente sintetico, e dito em voz alta para o time. Violacao e desclassificacao imediata.
- **Credibilidade da demo**: uma integracao publica real dentro do mundo mockado (PTAX/Bacen para conversao de moeda, por exemplo) custa quase nada e quebra o cheiro de "esta tudo mockado".
- O premio e por projeto, dividido igualmente entre os 4; rateio desigual e proibido independentemente da contribuicao individual. Primeiro lugar da **R$ 750 por pessoa**, e a parcela de integrante inelegivel **nao** e redistribuida.
- Elegibilidade vale **ate a divulgacao do resultado**, nao apenas na inscricao.
- Toda a propriedade intelectual e da GFT - cessao gratuita, total e irrevogavel. A autoria recebe apenas reconhecimento institucional.
- Tudo sobre o desafio e confidencial, explicitamente incluindo os criterios de avaliacao e os resultados preliminares. Manter estes arquivos internos. **A aprovacao da propria proposta e resultado preliminar** - comemorar dentro da GFT, nao fora dela.
- O grupo de Agent Builders aprovados e canal novo: o que for dito la **aterra no repositorio no mesmo dia**. Ja custou quase um mes uma vez.
- O regulamento chama cada integrante de **Builder** e o representante de **Agent Lead** - usar esse vocabulario no pitch soa como fluencia nas regras.
