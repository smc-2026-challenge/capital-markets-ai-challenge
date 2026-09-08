# oneask

O escopo submetido no formulario de inscricao, o conteudo extraido da pagina do Microsoft Loop **"OneAsk: Proposta de evolucao do MVP - Agente Inteligente de Extracao de Dados"**, e a avaliacao dessa proposta contra o Desafio Capital Markets - AI Agents Challenge (SMC 2026).

**Conteudo interno da GFT. Nao publicar, nao subir em plataforma nao homologada, nao compartilhar fora da GFT.** Ver `../RULES.md`, sec. 14 e 16.

## Arquivos

| Arquivo | O que e |
|---|---|
| `PROPOSTA_SUBMETIDA.md` | **O texto que manda.** Transcricao fiel dos campos 7, 8 e 9 do formulario de inscricao - o escopo submetido. Delimita o que os entregaveis podem afirmar, e o que eles tem de entregar. Preserva a acentuacao. |
| `OneAsk_Proposta_Evolucao_MVP.md` | Extracao **fiel** da pagina do Loop - a escada V1/V2/V3 proposta ao time. Nao editar; espelha a fonte. Preserva a acentuacao do original. |
| `AVALIACAO.md` | Avaliacao da proposta contra os criterios do desafio: nota por criterio, correcoes de maior impacto, arquitetura sugerida em Gemini Enterprise/GCP, respostas as 7 perguntas que o proprio documento faz ao time, plano ate 30/09 e riscos. ASCII puro. |

Contexto fora desta pasta: `../PLAN.md` (situacao, time, caminho critico), `../checkpoint.json` (tudo em formato legivel por maquina), `../RULES.md` (regulamento) e `../GUIA_TECNICO_RESPOSTA.md` (nao existe Guia Tecnico separado).

## Sobre a extracao

- Origem: Microsoft Loop sobre SharePoint `gft365` (contentstorage), acesso **Read-Only** para este usuario.
- Extraido em **08/09/2026**, pela sessao autenticada do navegador. A pagina nao e alcancavel por fetch anonimo.
- O Loop renderiza o documento em dois modos sobrepostos (`webView` e `simpleView`) e em 51 quadros paginados; a extracao usa apenas o fluxo `webView` e reconstroi a tabela da secao 6 a partir do DOM da tabela, para nao duplicar conteudo.
- **Nenhum comentario** na pagina de origem no momento da extracao.
- Estrutura preservada: 8 secoes, 1 tabela comparativa V1/V2/V3, blocos de citacao dos dialogos de exemplo, listas.

## Leitura recomendada

1. `PROPOSTA_SUBMETIDA.md` - o escopo submetido, e as tres coisas que ele estabelece.
2. `OneAsk_Proposta_Evolucao_MVP.md` - o plano de evolucao proposto ao time.
3. `AVALIACAO.md` secao 0.1 - o que o texto submetido muda, incluindo duas correcoes de escopo.
4. `AVALIACAO.md` secao 1 - veredito em uma pagina.
5. `AVALIACAO.md` secao 10 - as acoes imediatas.

Para a situacao do projeto como um todo - cronograma, o que esta confirmado, caminho critico - ver `../PLAN.md`. A versao legivel por maquina de tudo isso esta em `../checkpoint.json` (v7, 08/09/2026), que ja incorpora esta avaliacao; `AVALIACAO.md` secao 0 traz o mapa de qual secao daqui vive em qual chave de la.

## O ponto de atencao mais importante

**O campo 8 do formulario promete comportamento de V3, nao de V1.** Ele diz que o agente "identifica quais relatorios e fontes sao necessarios". A V1 do documento do Loop parte da premissa oposta - o usuario sabe qual relatorio quer. Logo **entregar apenas a V1 subentrega contra o escopo submetido**, e um playbook de V3 ponta a ponta passa a ser obrigatorio, nao diferencial.

## O segundo ponto de atencao

**Nenhum integrante do time e da Business Unit de Capital Markets.** Os quatro sao PSU BR - Analista de Negocios III, Front-End II, Back-End I e Analista de Teste I. Isso nao muda a direcao, mas muda o preco de vestir o dominio: a manchete de custodia recomendada em `AVALIACAO.md` secao 3.1 depende de **revisao por alguem da BU de Capital Markets**, sem a qual a pele de dominio vira passivo. Ver `../PLAN.md`, "A lacuna de dominio".

## O que segue nao confirmado

A aprovacao pelo comite (selecao encerrada em 01/09), o nome do **time** registrado nos formularios (campos 1 a 6 nao vistos), as licencas Gemini Enterprise, e se o GitHub usado pelo time e ambiente homologado para o codigo do desafio.

Ja resolvidos: o texto submetido, a composicao do time, o Agent Lead, os papeis profissionais, e o Guia Tecnico - que **nao existe** como documento separado (`../GUIA_TECNICO_RESPOSTA.md`).

Detalhes em `AVALIACAO.md`, secoes 0 e 0.1.
