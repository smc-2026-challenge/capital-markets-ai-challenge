<!--
Extracao fiel de pagina do Microsoft Loop. Nao editar este arquivo - ele espelha a fonte.
Origem: Microsoft Loop / SharePoint gft365 (contentstorage), acesso Read-Only.
Pagina: "OneAsk - Proposta de Estrutura de Refinamento"
Extraido em: 14/09/2026, via sessao autenticada do navegador do usuario.
Comentarios na pagina de origem: nenhum no momento da extracao.
Compartilhada por Raffaele Brivio no chat OneAsk do Teams em 14/09/2026, 13h30.
Este arquivo preserva a acentuacao do original (os demais arquivos do repositorio sao ASCII puro).
Niveis de titulo do original: Epic a 24px, Feature a 32px, US a 20px - mapeados aqui para H2/H2/H3.
Negrito parcial dentro de paragrafo preservado span a span.
CONTEUDO INTERNO DA GFT - nao publicar, nao subir em plataforma nao homologada.
-->

# OneAsk - Proposta de Estrutura de Refinamento

## Epic — OneAsk: Acesso Inteligente e Orquestrado a Informações

O OneAsk permitirá que usuários solicitem informações em linguagem natural, reduzindo a necessidade de conhecer previamente sistemas, relatórios, APIs ou mecanismos de extração.

A evolução ocorrerá de forma incremental:

**V1 — “Me dê este relatório”**

O usuário sabe qual relatório deseja.

**V2 — “Me dê esta informação”**

O usuário sabe qual informação deseja, mas não necessariamente onde encontrá-la.

**V3 — “Me ajude com esta necessidade”**

O usuário informa uma necessidade/problema e o OneAsk identifica quais informações e fontes são necessárias para atendê-la.

A V3 representa o objetivo funcional que precisamos alcançar, pois a proposta submetida já prevê interpretação da necessidade, identificação das fontes necessárias, determinação de parâmetros e orquestração das extrações.

---

## Feature 01 — Interação e Orquestração Inteligente

**Objetivo:** concentrar a experiência conversacional e a evolução da autonomia do OneAsk.

Essa Feature representa a jornada principal entre usuário e agente: entender a solicitação, identificar o que é necessário, esclarecer informações faltantes, preparar um plano, obter confirmação e coordenar sua execução.

### [V1] US01 — Solicitar e extrair relatório conhecido

O usuário solicita em linguagem natural um relatório que já conhece.

O OneAsk deverá compreender qual relatório foi solicitado e seus parâmetros, identificar informações obrigatórias ausentes e conversar com o usuário até possuir informações suficientes.

Quando a solicitação estiver completa, deverá preparar e apresentar o plano de execução. A extração somente ocorrerá após confirmação do usuário. Caso o usuário corrija alguma informação, o plano deverá ser recalculado antes de uma nova confirmação.

**Exemplo conceitual:** “Quero o relatório X referente a ontem.”

Essa US representa o **fluxo ponta a ponta principal da V1**.

### [V2] US02 — Solicitar e explorar informações sem conhecer o relatório

O usuário informa qual informação deseja obter, sem precisar conhecer previamente o relatório ou fonte correspondente.

O OneAsk deverá interpretar a informação solicitada, descobrir onde ela está disponível dentro das capacidades configuradas e permitir a obtenção do conjunto de dados necessário.

Essa evolução poderá contemplar seleção de campos e filtros sobre os dados disponíveis.

**Exemplo conceitual:** “Quero as transações de ontem com identificador do cliente e valor.”

O usuário passa a conhecer **o que quer**, mas não precisa saber **de qual relatório vem**.

### [V3] US03 — Solicitar atendimento de uma necessidade de negócio

O usuário descreve uma necessidade, atividade ou problema sem precisar saber quais relatórios ou informações serão necessários.

O OneAsk deverá interpretar a necessidade, determinar as informações necessárias, identificar as fontes disponíveis, solicitar contexto adicional quando necessário e construir um plano para atender à necessidade.

**Exemplo conceitual:** “Preciso investigar uma divergência de posição de ontem.”

Esse exemplo permanece apenas ilustrativo até o caso de Capital Markets ser validado.

Essa US representa a evolução de maior autonomia do agente e o comportamento necessário para atender ao escopo submetido no desafio.

---

## Feature 02 — Catálogo, Fontes e Conectores

**Objetivo:** permitir que o OneAsk conheça quais informações pode acessar e como acessá-las, mantendo fontes e integrações configuráveis.

A intenção é evitar que o agente dependa de conhecimento implícito ou “invente” fontes, relatórios ou formas de relacionamento.

### [V1] US04 — Disponibilizar fontes e relatórios configuráveis ao agente

As fontes e relatórios disponíveis ao OneAsk deverão estar previamente configurados em um catálogo.

Esse catálogo deverá fornecer informações suficientes para que o agente entenda, no mínimo:

- o que a fonte/relatório disponibiliza;
- quais informações/campos estão disponíveis;
- quais parâmetros são necessários;
- qual conector/capacidade deve ser utilizado para acessá-la.

O objetivo é permitir adicionar ou alterar fontes sem modificar a experiência conversacional do usuário.

**Exemplo conceitual:** o agente sabe que o “Relatório X” existe, o que contém, que precisa de período e qual conector consegue extraí-lo.

A forma técnica de armazenamento desse catálogo ainda não precisa ser definida pelo refinamento funcional.

### [V2] US05 — Descobrir e relacionar informações entre múltiplas fontes

O OneAsk poderá identificar que as informações solicitadas estão distribuídas entre diferentes fontes e relacioná-las quando houver uma relação segura entre os dados.

Dois comportamentos são previstos:

**Relacionamento previamente configurado:** o agente conhece a relação existente e poderá utilizá-la no planejamento.

**Relacionamento semanticamente inferido:** o agente identifica que dois campos potencialmente representam a mesma informação, explica ao usuário a relação encontrada e solicita confirmação antes de utilizá-la.

**Exemplo conceitual:** uma fonte contém `CPF` e outra contém `document_number`. O agente poderá identificar semanticamente uma possível relação, mas não deverá realizar o cruzamento baseado somente nessa inferência. Primeiro deverá informar o usuário e obter confirmação explícita.

Se não houver relação conhecida nem relação inferida aceita pelo usuário, o agente deverá informar que não possui segurança suficiente para realizar o cruzamento.

---

## Feature 03 — Entrega e Rastreabilidade

**Objetivo:** garantir que o resultado entregue pelo OneAsk seja utilizável e que o usuário consiga compreender o que foi executado e de onde vieram as informações.

Além dos dados, queremos preservar contexto e procedência da execução.

### [V1] US06 — Entregar resultado da extração com rastreabilidade

Após uma extração bem-sucedida, o OneAsk deverá disponibilizar inicialmente o resultado em **CSV**.

Junto ao resultado, deverá apresentar um resumo contendo minimamente:

- o que foi executado;
- fonte(s) utilizada(s);
- parâmetros aplicados;
- quantidade de registros;
- avisos ou informações relevantes sobre a execução.

Resultado vazio não deverá ser tratado automaticamente como erro. O agente deverá informar que a consulta foi executada corretamente, mas nenhum registro correspondente foi encontrado.

Falhas de execução deverão ser diferenciadas de resultados válidos sem registros.

Essa direção também é consistente com a recomendação existente nos documentos de retornar arquivo acompanhado de informações de procedência/manifesto.

### [V2/V3] US07 — Entregar resultado consolidado com evidências

Quando a solicitação utilizar múltiplas fontes ou representar uma necessidade de negócio, o OneAsk deverá entregar um resultado consolidado acompanhado das evidências necessárias para que o usuário compreenda sua origem.

A resposta deverá permitir identificar quais fontes contribuíram para o resultado, quais operações foram realizadas e quais premissas ou relacionamentos foram utilizados.

Quando uma relação entre dados tiver sido inferida e confirmada pelo usuário, essa informação deverá permanecer visível no resultado/rastreabilidade.

O formato final dessa entrega além do CSV ainda poderá evoluir durante o refinamento.
