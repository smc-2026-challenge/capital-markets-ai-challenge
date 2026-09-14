# oneask

O escopo submetido no formulario de inscricao, o conteudo extraido das duas paginas do Microsoft Loop - **"OneAsk: Proposta de evolucao do MVP"** e **"OneAsk - Proposta de Estrutura de Refinamento"** - e a avaliacao de ambas contra o Desafio Capital Markets - AI Agents Challenge (SMC 2026).

**Conteudo interno da GFT. Nao publicar, nao subir em plataforma nao homologada, nao compartilhar fora da GFT.** Ver `../RULES.md`, sec. 14 e 16.

## Arquivos

| Arquivo | O que e |
|---|---|
| `PROPOSTA_SUBMETIDA.md` | **O texto que manda.** Transcricao fiel dos campos 7, 8 e 9 do formulario de inscricao - o escopo submetido. Delimita o que os entregaveis podem afirmar, e o que eles tem de entregar. Preserva a acentuacao. |
| `OneAsk_Proposta_Evolucao_MVP.md` | Extracao **fiel** da pagina do Loop de 08/09 - a escada V1/V2/V3 proposta ao time. Nao editar; espelha a fonte. Preserva a acentuacao do original. |
| `OneAsk_Proposta_Estrutura_Refinamento.md` | Extracao **fiel** da segunda pagina do Loop, de 14/09 - o Epic, as **3 Features e 7 User Stories** que consolidam a escada V1/V2/V3 em backlog. Nao editar; espelha a fonte. Preserva a acentuacao do original. |
| `AVALIACAO.md` | Avaliacao da proposta contra os criterios do desafio: nota por criterio, correcoes de maior impacto, arquitetura sugerida em Gemini Enterprise/GCP, respostas as 7 perguntas que o proprio documento faz ao time, plano ate 30/09 e riscos. ASCII puro. |
| `REFINAMENTO_ANALISE.md` | Avaliacao da estrutura de refinamento: as quatro lacunas, a linha de corte comprometido/esticado para os 9 dias uteis restantes, as respostas as cinco confirmacoes que o Agent Lead pediu, e um **rascunho de resposta pronto para colar no Teams**. ASCII puro, exceto o bloco de resposta. |

Contexto fora desta pasta: `../PLAN.md` (situacao, time, caminho critico), `../checkpoint.json` (tudo em formato legivel por maquina), `../RULES.md` (regulamento) e `../GUIA_TECNICO_RESPOSTA.md` (nao existe Guia Tecnico separado).

## Sobre as extracoes

- Origem: Microsoft Loop sobre SharePoint `gft365` (contentstorage), acesso **Read-Only** para este usuario. Nenhuma das duas paginas e alcancavel por fetch anonimo - as duas foram extraidas pela sessao autenticada do navegador.
- O Loop renderiza o documento em dois modos sobrepostos (`webView` e `simpleView`) e em quadros paginados com `content-visibility: auto`; as extracoes usam apenas o fluxo `webView` e forcam a renderizacao dos quadros antes de ler, para nao perder conteudo virtualizado nem duplicar o que aparece nos dois modos.
- **Nenhum comentario** em nenhuma das duas paginas no momento das extracoes.

| Pagina | Extraida em | Estrutura preservada |
|---|---|---|
| Proposta de evolucao do MVP | **08/09/2026** | 8 secoes, 1 tabela comparativa V1/V2/V3, blocos de citacao dos dialogos de exemplo, listas. A tabela da secao 6 foi reconstruida a partir do DOM da tabela |
| Proposta de Estrutura de Refinamento | **14/09/2026** | 1 Epic, 3 Features, 7 User Stories, 6 quadros paginados, negrito parcial dentro de paragrafo preservado span a span |

## Leitura recomendada

1. `PROPOSTA_SUBMETIDA.md` - o escopo submetido, e as tres coisas que ele estabelece.
2. `OneAsk_Proposta_Evolucao_MVP.md` - o plano de evolucao proposto ao time.
3. `AVALIACAO.md` secao 0.1 - o que o texto submetido muda, incluindo duas correcoes de escopo.
4. `AVALIACAO.md` secao 1 - veredito em uma pagina.
5. `AVALIACAO.md` secao 10 - as acoes imediatas.
6. `OneAsk_Proposta_Estrutura_Refinamento.md` - o backlog proposto ao time em 14/09.
7. `REFINAMENTO_ANALISE.md` secoes 2 e 3 - as quatro lacunas e a linha de corte.
8. `REFINAMENTO_ANALISE.md` secao 8 - o rascunho de resposta para o Teams.

Para a situacao do projeto como um todo - cronograma, o que esta confirmado, caminho critico - ver `../PLAN.md`. A versao legivel por maquina de tudo isso esta em `../checkpoint.json` (v8, 08/09/2026), que ja incorpora esta avaliacao; `AVALIACAO.md` secao 0 traz o mapa de qual secao daqui vive em qual chave de la.

## O ponto de atencao mais importante

**O campo 8 do formulario promete comportamento de V3, nao de V1.** Ele diz que o agente "identifica quais relatorios e fontes sao necessarios". A V1 do documento do Loop parte da premissa oposta - o usuario sabe qual relatorio quer. Logo **entregar apenas a V1 subentrega contra o escopo submetido**, e um playbook de V3 ponta a ponta passa a ser obrigatorio, nao diferencial.

**A estrutura de refinamento de 14/09 ja incorporou isso** - o Epic declara a V3 como o objetivo funcional, citando o texto submetido. O que ela ainda nao tem e o **mecanismo**: a V1 ganhou uma US para o seu (US04, o catalogo), a V3 nao ganhou a dela. Ver `REFINAMENTO_ANALISE.md`, secao 2, lacuna 1.

## O segundo ponto de atencao

**Nenhum integrante do time e da Business Unit de Capital Markets.** Os quatro sao PSU BR - Analista de Negocios III, Front-End II, Back-End I e Analista de Teste I. Isso nao muda a direcao, mas muda o preco de vestir o dominio: a manchete de custodia recomendada em `AVALIACAO.md` secao 3.1 depende de **revisao por alguem da BU de Capital Markets**, sem a qual a pele de dominio vira passivo. Ver `../PLAN.md`, "A lacuna de dominio".

## O que segue nao confirmado

O aceite das tres inscricoes individuais regularizadas em 09/09, as licencas Gemini Enterprise, e **o acesso ao GitLab da GFT** - prometido para ate ~18/08 e ainda sem confirmacao, sendo que o diretorio da equipe e entregavel obrigatorio.

Ja resolvidos: o texto submetido, a composicao do time, o Agent Lead, os papeis profissionais, o Guia Tecnico - que **nao existe** como documento separado (`../GUIA_TECNICO_RESPOSTA.md`) - e, desde 10/09, **a aprovacao da proposta**, o nome do time (**OneAsk**) e o ambiente homologado do codigo (**GitLab da GFT**). Ver `../APROVACAO.md`.

> **Atencao ao contar entregaveis:** sao **cinco**, nao quatro. O e-mail de aprovacao acrescentou os artefatos no diretorio da equipe no GitLab, e exigiu o padrao Google Enterprise AI em todos eles.

Detalhes em `AVALIACAO.md`, secoes 0 e 0.1.
