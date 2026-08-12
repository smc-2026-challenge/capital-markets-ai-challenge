# Capital Markets AI Agents Challenge - SMC 2026

Pasta de trabalho do time para o Desafio Capital Markets - AI Agents Challenge (SMC 2026), promovido pela GFT Technologies Brasil.

**Conteudo interno da GFT. Nao publicar, nao subir em plataforma publica, nao compartilhar fora da GFT.** O regulamento classifica como confidencial tudo relacionado ao desafio, inclusive os criterios de avaliacao e resultados preliminares (sec. 16), e proibe upload de documentos internos em plataformas nao homologadas (sec. 14, III). Violacao e gatilho explicito de desclassificacao (sec. 20, II e IX).

> Todos os arquivos deste diretorio estao em pt-BR sem acentuacao (ASCII puro), para nao quebrar em formularios, nomes de arquivo, URLs e terminais.

## Datas que mandam

| Data | O que acontece |
|---|---|
| **28/08** | Encerra a inscricao. Formulario **individual** - cada integrante preenche o seu. Vagas limitadas. |
| 01/09 | Fim da selecao das propostas pelo comite |
| **30/09** | Ultimo dia para enviar o agente |
| 16/10 | Divulgacao dos 3 finalistas |
| **28/10** | Apresentacao final. O publico presente vota 1o, 2o e 3o lugares. |

Cronograma completo em `RULES.md`.

## Por onde comecar

1. Leia `PLAN.md` - onde estamos, caminho critico, fases de construcao, questoes abertas.
2. Leia `RULES.md` - resumo do regulamento. Confira sua propria elegibilidade antes de qualquer coisa.
3. Leia `IDEAS.md` - dores de negocio mapeadas e catalogo de solucoes candidatas. Nada decidido ainda.
4. Opine em `NAMES.md` - candidatos a nome do time.

## Arquivos

| Arquivo | O que e |
|---|---|
| `PLAN.md` | Plano de trabalho: situacao atual, caminho critico, 5 fases de construcao, questoes abertas |
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

- Nome do time: **nao decidido**
- Problema e solucao: **nao decidido**
- Composicao do time e Agent Lead: **nao definidos**
- Inscricao: **nao enviada**
- Guia Tecnico oficial: **nao obtido** - solicitar a Organizacao (Evelim Buratti, emro@gft.com). Ele define os requisitos de arquitetura, integracao, seguranca e execucao, e parte integrante das regras, e descumprir os padroes Gemini Enterprise / GCP desclassifica.

## Regras que nao se negocia

- **Plataforma**: o agente final tem de rodar em Gemini Enterprise + Google Cloud Platform. Fora desse padrao, desclassificacao.
- **Dados**: somente publicos, sinteticos, mockados ou anonimizados com autorizacao previa. Sem dados reais de cliente, sem dados pessoais, sem bases de producao, sem codigo fonte da GFT ou de clientes.
- **Elegibilidade**: somente CLT. Bench/Staff, aviso previo e afastamento desclassificam - e a parcela do premio de um integrante inelegivel nao e redistribuida ao resto do time.
- **Propriedade intelectual**: tudo que for construido e da GFT, por cessao gratuita e irrevogavel.
- **Confidencialidade**: vale tambem depois do fim do desafio e depois de eventual desligamento.
