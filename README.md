# Capital Markets AI Agents Challenge - SMC 2026

Pasta de trabalho do time para o Desafio Capital Markets - AI Agents Challenge (SMC 2026), promovido pela GFT Technologies Brasil.

**Conteudo interno da GFT. Nao publicar, nao subir em plataforma publica, nao compartilhar fora da GFT.** O regulamento classifica como confidencial tudo relacionado ao desafio, inclusive os criterios de avaliacao e resultados preliminares (sec. 16), e proibe upload de documentos internos em plataformas nao homologadas (sec. 14, III). Violacao e gatilho explicito de desclassificacao (sec. 20, II e IX).

> Os arquivos **autorais** deste diretorio estao em pt-BR sem acentuacao (ASCII puro), para nao quebrar em formularios, nomes de arquivo, URLs e terminais.
>
> As excecoes sao as tres **transcricoes fieis**, que preservam a acentuacao da fonte porque espelham um original: `GUIA_TECNICO_RESPOSTA.md`, `oneask/PROPOSTA_SUBMETIDA.md` e `oneask/OneAsk_Proposta_Evolucao_MVP.md`.

## Datas que mandam

| Data | O que acontece |
|---|---|
| ~~28/08~~ | Encerrou a inscricao. Formulario **individual** - cada integrante preenchia o seu. |
| ~~01/09~~ | Encerrou a selecao das propostas pelo comite |
| **30/09** | Ultimo dia para enviar o agente - **prazo vigente** |
| 16/10 | Divulgacao dos 3 finalistas |
| **28/10** | Apresentacao final. O publico presente vota 1o, 2o e 3o lugares. |

Cronograma completo em `RULES.md`.

## Por onde comecar

1. Leia `PLAN.md` - onde estamos, caminho critico, plano ate 30/09, questoes abertas.
2. Leia `oneask/PROPOSTA_SUBMETIDA.md` - o escopo submetido. E o texto que manda.
3. Leia `oneask/README.md` - a solucao em construcao e a avaliacao dela.
4. Leia `RULES.md` - resumo do regulamento. Confira sua propria elegibilidade antes de qualquer coisa.
5. `IDEAS.md` - dores de negocio mapeadas e catalogo de solucoes candidatas. **Historico**: a recomendacao de agosto (A3 Covenant Watch) foi superada pela direcao OneAsk, mas o mapa de dores segue valido como referencia.
6. `NAMES.md` - candidatos a nome do time. Confirmar qual nome foi efetivamente registrado no formulario.

## Arquivos

| Arquivo | O que e |
|---|---|
| `PLAN.md` | Plano de trabalho: situacao atual, caminho critico, plano ate 30/09, definicao de pronto da V1, questoes abertas |
| `oneask/` | A solucao em construcao: o texto submetido no formulario, a extracao fiel da proposta OneAsk (pagina do Loop) e a avaliacao contra os criterios do desafio |
| `GUIA_TECNICO_RESPOSTA.md` | Resposta da Organizacao sobre o Guia Tecnico: **nao existe** como documento separado. Transcricao fiel |
| `RULES.md` | Resumo do regulamento e da pagina de divulgacao, com numero de secao |
| `IDEAS.md` | 5 dores de negocio (P1 a P5) e 10 solucoes candidatas (A1 a D9), com analise contra os pesos de avaliacao |
| `NAMES.md` | 18 candidatos a nome do time, em ingles e portugues |
| `checkpoint.json` | Todo o contexto em formato legivel por maquina. Serve para retomar o trabalho sem reprocessar as fontes |
| `Regulamento_AI_Agents_Challenge_SMC_2026.md` | Regulamento completo convertido para markdown (26 secoes) |
| `Brazil_NewsForYou.md` | Pagina de divulgacao do SharePoint convertida para markdown |
| `Regulamento_AI_Agents_Challenge_SMC_2026.pdf` | **Fonte autoritativa.** Em duvida juridica, vale o PDF, nao a conversao |
| `Brazil_NewsForYou.html` + `Brazil_NewsForYou_files/` | Pagina salva original. Substituida por `Brazil_NewsForYou.md` - ver aviso abaixo |

## Aviso sobre os arquivos HTML

`Brazil_NewsForYou.html` carrega, embutida, a URL de origem do SharePoint com tokens de sessao (`xsdata`, `sdata`), o identificador do tenant e o UPN do usuario que salvou a pagina. Esses tokens foram removidos na conversao para `Brazil_NewsForYou.md`.

Recomendacao: **nao inclua os dois arquivos HTML no que for compartilhado com o time.** O markdown tem todo o conteudo. Se ninguem precisar do original, apague os HTML da pasta.

## Estado atual das decisoes

Atualizado em **08/09/2026**. Fase: **construcao do agente**.

**Definido**

- Problema e solucao: **OneAsk - Agente Inteligente de Extracao de Dados** (`oneask/`). A direcao esta travada pelo texto submetido no formulario; o que segue em discussao e o plano de evolucao V1/V2/V3.
- Proposta submetida: **confirmada** - texto em `oneask/PROPOSTA_SUBMETIDA.md` (campos 7, 8 e 9). Delimita o que os entregaveis podem afirmar, e o que eles tem de entregar.
- **Escopo minimo:** o campo 8 promete que o agente identifica quais relatorios sao necessarios - comportamento de V3. Logo **V1 sozinha nao basta**: e preciso V1 mais um playbook de V3. Ver `PLAN.md`, "O que o texto submetido muda".
- Time: **4 integrantes**, o maximo permitido, multidisciplinar - Analista de Negocios III (Raffaele Brivio), Front-End II (Jeferson Franco), Back-End I (Guilherme Augusto de Melo), Analista de Teste I (Michelle Carla da Silva). Todos PSU BR.
- Agent Lead: **Raffaele Brivio** - cabe a ele o envio das entregas e a comunicacao com a Organizacao.
- Guia Tecnico: **nao existe como documento separado.** A Organizacao respondeu em 12/08 que e a pagina do SharePoint mais o proprio regulamento, nada alem. Ver `GUIA_TECNICO_RESPOSTA.md`.

**Em aberto**

- **Lacuna de dominio:** nenhum integrante e da BU de Capital Markets. A revisao do cenario da demo por alguem de CM e a acao de maior alavancagem disponivel hoje - ver `PLAN.md`, "A lacuna de dominio".
- **A confirmar com urgencia:** se o GitHub usado pelo time e ambiente homologado para o codigo do desafio (sec. 14, 15 e 20 - classe de gatilho de desclassificacao).
- Aprovacao pelo comite (selecao encerrada em 01/09): **nao confirmada**
- Nome do **time** registrado nos formularios: **nao confirmado** - os campos 1 a 6 nao foram vistos
- Licencas Gemini Enterprise: **recebimento nao confirmado**
- Elegibilidade individual dos 4, e autorizacao do gestor para dedicacao em expediente: **a conferir por cada um**
- Os quatro entregaveis obrigatorios: **nao iniciados**, exceto a demo (V1 em construcao)

Em `checkpoint.json`, `null` significa **nao confirmado**, nao `false`. A distincao importa: parte do trabalho avancou fora deste repositorio.

## Regras que nao se negocia

- **Plataforma**: o agente final tem de rodar em Gemini Enterprise + Google Cloud Platform. Fora desse padrao, desclassificacao.
- **Dados**: somente publicos, sinteticos, mockados ou anonimizados com autorizacao previa. Sem dados reais de cliente, sem dados pessoais, sem bases de producao, sem codigo fonte da GFT ou de clientes.
- **Elegibilidade**: somente CLT. Bench/Staff, aviso previo e afastamento desclassificam - e a parcela do premio de um integrante inelegivel nao e redistribuida ao resto do time.
- **Propriedade intelectual**: tudo que for construido e da GFT, por cessao gratuita e irrevogavel.
- **Confidencialidade**: vale tambem depois do fim do desafio e depois de eventual desligamento.
