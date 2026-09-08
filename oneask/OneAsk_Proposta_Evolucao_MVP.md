<!--
Extracao fiel de pagina do Microsoft Loop. Nao editar este arquivo - ele espelha a fonte.
Origem: Microsoft Loop / SharePoint gft365 (contentstorage), acesso Read-Only.
Extraido em: 08/09/2026, via sessao autenticada do navegador do usuario.
Comentarios na pagina de origem: nenhum no momento da extracao.
Este arquivo preserva a acentuacao do original (os demais arquivos do repositorio sao ASCII puro).
CONTEUDO INTERNO DA GFT - nao publicar, nao subir em plataforma nao homologada.
-->

# OneAsk: Proposta de evolução do MVP - Agente Inteligente de Extração de Dados

## 1. Objetivo deste documento

Organizar uma proposta inicial de evolução do agente para discutirmos em conjunto.

A intenção não é definir antecipadamente que todas as versões serão desenvolvidas, nem fechar a ordem apresentada abaixo. A proposta é termos uma visão incremental que permita:

- garantir primeiro um MVP funcional;
- evoluir o agente conforme tempo e viabilidade técnica;
- evitar aumentar o escopo antes de validar o core;
- discutir se V2 e V3 representam a melhor sequência de evolução;
- reunir sugestões e alternativas.

---

## 2. Visão da solução

A proposta é criar um agente conversacional capaz de centralizar o acesso a relatórios e informações distribuídos em diferentes sistemas.

O agente recebe solicitações em linguagem natural, interpreta a necessidade do usuário e utiliza as ferramentas/conectores disponíveis para obter os dados necessários.

Para o desafio, podemos trabalhar com APIs e dados mockados, representando diferentes sistemas, relatórios e formas de consulta.

A visão de evolução proposta é aumentar gradualmente o nível de abstração para o usuário:

V1 — “Me dê este relatório.”

↓

V2 — “Me dê esta informação.”

↓

V3 — “Me ajude com este problema.”

---

## 3. V1 — Conversational Report Retrieval

### Conceito

O usuário sabe qual relatório deseja.

Esta seria a primeira versão e o core do MVP.

O usuário solicita em linguagem natural um relatório e os parâmetros necessários, como data ou período. O agente interpreta a solicitação, identifica o conector correspondente e executa a extração.

### Exemplo

> Usuário: “Baixe o relatório de transações entre 01/09 e 05/09.”

Fluxo esperado:

Solicitação

→ identificação do relatório

→ interpretação dos parâmetros

→ seleção da ferramenta/conector

→ chamada da API

→ disponibilização do arquivo

### O que queremos validar

- interação em linguagem natural;
- identificação correta do relatório;
- interpretação de datas/períodos;
- seleção da ferramenta adequada;
- comunicação com APIs/fontes diferentes;
- retorno do arquivo ao usuário;
- tratamento básico de erros ou informações ausentes.

Caso alguma informação obrigatória não seja fornecida, o agente deve solicitar ao usuário.

> Usuário: “Baixe o relatório de transações.”
> Agente: “Para qual data ou período?”

### Resultado da V1

Ter um fluxo ponta a ponta funcional:

Usuário → Agente → Tool/API → Arquivo

---

## 4. V2 — Conversational Data Exploration

### Conceito

O usuário sabe qual informação deseja, mas não necessariamente quer ou conhece o relatório completo.

A evolução aqui seria sair da simples extração de arquivos e permitir que o usuário explore, selecione e combine informações através da conversa.

A V2 pode ser construída incrementalmente.

### V2.1 — Exploração do conteúdo

O usuário pode perguntar quais informações estão disponíveis.

> Usuário: “Quais informações existem no relatório de transações?”
> Agente: “O relatório possui ID da transação, ID do cliente, produto, moeda, valor, data, status…”

Isso permite que o usuário entenda a estrutura antes de decidir o que precisa.

### V2.2 — Seleção e filtros

O usuário pode solicitar somente parte das informações e definir condições em linguagem natural.

> Usuário: “Quero somente ID do cliente, moeda e valor das transações em EUR acima de 500 mil.”

O agente identifica:

Campos: ID do cliente, moeda, valor

Filtros: moeda = EUR / valor > 500.000

A ferramenta/backend processa os dados e gera um resultado contendo somente as informações solicitadas.

### V2.3 — Cruzamento e enriquecimento de fontes

A informação solicitada pode não existir em uma única fonte.

Exemplo:

Transactions

transaction_id | client_id | currency | value

Customers

client_id | customer_name | segment

O usuário solicita:

> “Quero as transações em EUR acima de 500 mil com nome e segmento do cliente.”

O agente identifica que precisa:

- obter os dados de transações;
- obter os dados de clientes;
- relacionar as fontes por client_id;
- aplicar os filtros solicitados;
- gerar um novo resultado consolidado.

### Resultado da V2

Evoluir de:

“buscar um arquivo”

para:

“encontrar e construir a informação solicitada.”

---

## 5. V3 — Intelligent Business Retrieval

### Conceito

O usuário sabe o problema ou atividade que precisa realizar, mas não necessariamente sabe quais relatórios ou informações precisa consultar.

Aqui aumentamos o nível de autonomia do agente.

Exemplo:

> Usuário: “Preciso investigar uma divergência de posição de ontem.”

O agente utiliza seu contexto/conhecimento para identificar que, para essa análise, pode precisar de:

- Position Report;
- Transaction Report;
- Movement Report.

A partir disso, utiliza as capacidades construídas anteriormente para obter as informações necessárias.

### Fluxo esperado

Problema/necessidade do usuário

↓

Entendimento do contexto

↓

Identificação das informações necessárias

↓

Identificação das fontes

↓

Seleção das ferramentas

↓

Extração / filtro / cruzamento, quando necessário

↓

Resultado

Caso o contexto seja insuficiente, o agente deve conversar com o usuário antes de executar.

> Usuário: “Preciso investigar uma divergência de posição.”
> Agente: “Para qual data ou período?”

### Resultado da V3

O usuário deixa de precisar conhecer previamente qual relatório ou dado deve solicitar.

A interação passa de:

> “Quero o relatório X.”

para:

> “Tenho este problema / preciso realizar esta atividade.”

e o agente determina o que precisa consultar para ajudar o usuário.

---

## 6. Evolução proposta

| Dimensao | V1 | V2 | V3 |
|---|---|---|---|
| Usuário sabe | Qual relatório quer | Qual informação quer | Qual problema quer resolver |
| Agente identifica | Como obter o relatório | Onde estão os dados e como processá-los | Quais informações são necessárias |
| Principal capacidade | Retrieval | Exploração e composição de dados | Entendimento de contexto/necessidade |
| Exemplo | “Baixe Transactions de ontem” | “Quero transações EUR >500k com nome do cliente” | “Preciso investigar divergência de posição” |
| Entrega | Arquivo existente | Informação/dataset personalizado | Informações necessárias para a necessidade apresentada |

### Hipótese de evolução

A lógica por trás dessa ordem seria aumentar gradualmente a autonomia:

Relatório → Informação → Necessidade de negócio

Mas essa ordem também faz parte da proposta a ser discutida. Dependendo da complexidade técnica, valor percebido e visão do grupo, V2 e V3 podem ser priorizadas ou organizadas de outra maneira.

---

## 7. Premissas iniciais para o desafio

Para manter o projeto viável dentro do prazo:

- trabalhar inicialmente com um universo pequeno e controlado de sistemas e relatórios;
- utilizar APIs/dados mockados quando necessário;
- assumir conectores previamente conhecidos/configurados;
- não buscar nesta etapa uma integração universal com qualquer API;
- utilizar o agente para entendimento, decisão e orquestração;
- utilizar backend/tools para operações determinísticas como chamadas de API, filtros, joins e geração de arquivos;
- tratar V1 como fundação e evoluir conforme capacidade do time.

A arquitetura deve, quando possível, evitar que uma evolução exija reconstruir completamente a versão anterior.

---

## 8. Pontos para discussão com o time

Gostaria principalmente de validar:

Visão: Faz sentido essa evolução do produto ou enxergamos outro caminho mais interessante?

Priorização: V2 e V3 estão na ordem correta? Faz mais sentido primeiro evoluir para exploração/manipulação dos dados ou para entendimento da necessidade de negócio?

Viabilidade: Quais partes parecem simples ou complexas tecnicamente?

Escopo: Qual seria o mínimo necessário para considerarmos a V1 realmente funcional?

Evolução: V2.1, V2.2 e V2.3 fazem sentido como incrementos separados?

Arquitetura: Conseguimos estruturar a V1 de maneira que suporte essas evoluções sem grande retrabalho?

Outras ideias: Que outras capacidades ou caminhos de evolução o time enxerga?
