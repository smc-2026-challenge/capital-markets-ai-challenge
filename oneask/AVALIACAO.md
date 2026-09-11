# Avaliacao do OneAsk contra o Desafio Capital Markets - SMC 2026

Data desta avaliacao: **08/09/2026**. Fontes avaliadas: `OneAsk_Proposta_Evolucao_MVP.md` (extracao fiel da pagina do Loop) e `PROPOSTA_SUBMETIDA.md` (texto do formulario de inscricao - o escopo submetido).
Referencias: `../RULES.md` (regulamento), `../GUIA_TECNICO_RESPOSTA.md` (nao existe Guia Tecnico separado), `../IDEAS.md` (espaco de problemas), `../PLAN.md` (plano de trabalho), `../checkpoint.json`.

> Este arquivo esta em pt-BR sem acentuacao (ASCII puro), seguindo a convencao do repositorio.
> **Conteudo interno da GFT.** Nao publicar, nao subir em plataforma nao homologada.

---

## 0. Aviso de contexto - o que esta confirmado e o que nao esta

`../PLAN.md` e `../checkpoint.json` foram atualizados em **08/09/2026** e ja refletem a direcao OneAsk (checkpoint v8). Este arquivo e a versao longa do que aqueles dois resumem - se houver divergencia, este e o detalhamento e eles sao o indice.

**Resolvido em 08/09:** o texto submetido no formulario esta transcrito em `PROPOSTA_SUBMETIDA.md` (campos 7, 8 e 9 da secao "Dados do Agente"). Isso destrava a questao que bloqueava esta avaliacao inteira - e corrige duas recomendacoes. Ver secao 0.1.

**Tambem resolvido em 08/09:** o time e de **4 integrantes** - o maximo permitido - com **Raffaele Brivio** (Analista de Negocios III) como Agent Lead, mais Front-End II, Back-End I e Analista de Teste I. Todos PSU BR. Ver `../PLAN.md`, secao "O time".

Disso sai o achado que mais afeta esta avaliacao: **nenhum integrante e da Business Unit de Capital Markets**. Isso qualifica a correcao C1 - ver secao 3.1, "O custo de credibilidade". Em compensacao, a composicao encaixa surpreendentemente bem na arquitetura recomendada, incluindo um ativo raro: ter QA no time permite **demonstrar** o invariante anti-alucinacao em vez de apenas afirma-lo.

**Tambem resolvido:** nao existe Guia Tecnico separado - a especificacao tecnica e o regulamento mais a pagina do SharePoint (`../GUIA_TECNICO_RESPOSTA.md`). Isso remove a ressalva que acompanhava a secao 5.

**Resolvido em 10/09 pelo e-mail de aprovacao** (`../APROVACAO.md`): a proposta foi **APROVADA** pelo comite; o nome do **time** registrado e **OneAsk** (o e-mail abre com "Ola OneAsk!"); e o ambiente homologado do codigo e o **GitLab da GFT**, em diretorio da equipe - a pergunta sobre o GitHub perdeu o objeto.

O mesmo e-mail acrescenta um **quinto entregavel obrigatorio** - os artefatos de desenvolvimento no diretorio da equipe no GitLab - e estende a exigencia do padrao Google Enterprise AI a **todos** os entregaveis. Esta avaliacao foi escrita quando eram quatro; onde ela disser "os quatro entregaveis", leia cinco.

Seguem **nao confirmados**: o aceite das tres inscricoes individuais regularizadas em 09/09, a liberacao das licencas Gemini Enterprise, e **o provisionamento do acesso ao GitLab** (prometido para ate ~18/08). Em `../checkpoint.json` esses itens estao como `null`, que significa **nao confirmado**, nao `false`.

Ressalva remanescente sobre a premissa desta avaliacao: a **direcao** esta travada pelo formulario e isso nao muda mais. O que segue podendo mudar e o **plano de evolucao V1/V2/V3** - se o documento do Loop for proposta de um integrante que o grupo ainda nao adotou, aquela escada e candidata, nao decidida.

### Onde cada parte desta avaliacao vive no checkpoint

| Secao daqui | Chave em `../checkpoint.json` |
|---|---|
| 0.1 - o que o texto submetido muda | `proposta_submetida` |
| 1, 2 - veredito e nota por criterio | `avaliacao_da_direcao_atual` |
| 3 - as tres correcoes | `avaliacao_da_direcao_atual.tres_correcoes_de_maior_impacto` |
| 3.1 - o custo de credibilidade | `time.lacuna_de_dominio` |
| 3.1 - distribuicao do trabalho | `time.mapeamento_dos_papeis_para_o_trabalho` |
| 4 - o numero que falta | `avaliacao_da_direcao_atual.o_numero_que_falta` |
| 5 - arquitetura | `arquitetura_sugerida`, `restricoes_tecnicas.guia_tecnico` |
| 6, resposta 3 e 4 | `viabilidade_por_incremento`, `definicao_de_pronto_da_v1` |
| 7 - plano de 22 dias | `plano_ate_30_09` |
| 8 - coreografia da demo | `avaliacao_da_direcao_atual.coreografia_da_demo` |
| 9 - riscos | `riscos` |
| 10 - acoes imediatas | `proximas_acoes` (com dono), `questoes_abertas` |
| 11 - segunda opiniao externa | `segunda_opiniao_externa` |

---

## 0.1 O que o texto submetido muda nesta avaliacao

Tres fatos. Os dois primeiros corrigem recomendacoes que eu havia dado antes de ver o texto.

### Fato 1 - a proposta e horizontal, e o texto e neutro de dominio, nao errado de dominio

Nao ha **uma unica palavra de Mercado de Capitais** nos tres campos. O problema fala de "atividades operacionais"; o publico-alvo e "equipes de operacoes, negocio e tecnologia". Isso **confirma** a fragilidade em Aderencia ao Mercado de Capitais que a secao 2 apontava como suspeita.

A boa noticia esta na distincao: o texto e *neutro*, nao *contrario*. Se o formulario dissesse "e-commerce", a correcao estaria travada. Como ele diz "diferentes sistemas" e "atividades operacionais", demonstrar num caso de custodia **nao contradiz o texto - evidencia o texto**.

Isso mantem a correcao C1 valida, mas com uma restricao que eu nao tinha: **a afirmacao horizontal precisa sobreviver, como argumento de Escalabilidade (15%)**, em vez de ser substituida. A forma do pitch passa a ser:

| Momento | Conteudo | Ancoragem |
|---|---|---|
| Problema | Relatorios fragmentados entre sistemas, e o gargalo persiste **mesmo onde ja existem APIs** | campo 7, quase literal |
| Onde doi mais - a demo | Custodia e pos-negociacao: investigacao de divergencia de posicao | instancia do campo 7 |
| Mecanismo | Catalogo semantico, playbooks e conectores configuraveis | campo 8, quase literal |
| Escala | Mesmo motor, qualquer dominio: operacoes, negocio e tecnologia | campo 9, literal |

Isso e melhor que a C1 original, porque transforma o enquadramento generico de passivo em ativo: ele deixa de ser o motivo da nota fraca em Aderencia e passa a ser a historia de Escalabilidade.

### Fato 2 - o texto submetido promete V3, nao V1

Esta e a correcao consequente. O campo 8 diz que o agente **"interpreta a necessidade do usuario, identifica quais relatorios e fontes sao necessarios, determina os parametros da consulta e orquestra as extracoes"**.

Isso e a **V3** do documento de evolucao. A V1 daquele documento parte da premissa oposta e explicita: *"o usuario sabe qual relatorio deseja"*.

Ou seja, existe uma **lacuna entre o escopo submetido e o plano de MVP**: o formulario prometeu identificacao de necessidade; o plano coloca isso na ultima versao, opcional.

Consequencia direta, e ela **corrige o que esta escrito na secao 6, resposta 4**: eu havia dito que a V1 sozinha ja seria submissao valida. **Contra este texto, nao e.** Entregar apenas "o usuario pede um relatorio pelo nome" subentrega contra o que foi submetido.

Portanto **um playbook de V3 ponta a ponta deixa de ser diferencial e passa a ser obrigatorio**. O plano da secao 7 foi reordenado por causa disso. E felizmente essa e a parte barata (ver secao 6, resposta 3): playbook e configuracao, nao engenharia de dados.

### Fato 3 - a arquitetura de conectores ja foi prometida

O campo 8 se compromete com **"uma arquitetura de conectores configuraveis, permitindo sua adaptacao a diferentes sistemas, APIs e mecanismos de automacao sem alterar a experiencia do usuario"**.

"Sem alterar a experiencia do usuario" e precisamente a propriedade de **catalogo como dado**. Logo a correcao C2 deixa de ser sugestao de inovacao e passa a ser **cumprimento do que foi prometido** - e os conectores mockados heterogeneos (secao 5) deixam de ser cortesia de credibilidade e passam a ser **a evidencia de uma afirmacao ja feita ao comite**.

### Uma frase do texto que vale carregar para o pitch

O campo 7 diz que a fragmentacao persiste **"mesmo quando ja existem APIs ou automacoes para parte dessas atividades"**. Isso preempta a objecao mais obvia que um juri tecnico faz a este tipo de agente - *"por que nao chamar a API direto?"*. O gargalo nao e integracao, e saber o que pedir e onde. Levar essa frase para o one-pager e para a abertura do video.

### O que o texto NAO resolve

Nao ha numero nele tambem. "Aumenta o esforco operacional" e o adjetivo, no lugar exato onde deveria estar a cifra. A secao 4 segue sendo a correcao de maior alavancagem por unidade de esforco, e agora se sabe que o one-pager nao herda nenhum numero do formulario - tem de produzi-lo.

---

## 1. Veredito em uma pagina

O OneAsk esta **tecnicamente bem pensado e estrategicamente mal posicionado**.

O que esta certo, e nao e pouco: a premissa de que o agente cuida de entendimento, decisao e orquestracao, enquanto backend e tools cuidam de operacoes deterministicas (chamada de API, filtro, join, geracao de arquivo). Essa e exatamente a divisao que o `../checkpoint.json` aponta como o ponto forte do Gemini Enterprise, e e a divisao que um juri tecnico premia, porque mostra um time que sabe onde o LLM **nao** deve entrar. A escada V1 -> V2 -> V3 tambem esta bem construida como sequencia de engenharia.

O que esta em risco: a proposta, como esta escrita, **poderia ser de qualquer setor**. "Relatorio de transacoes", "clientes", "moeda = EUR", "valor > 500 mil" descrevem um banco de varejo, uma telco, um e-commerce. O unico momento genuinamente de Mercado de Capitais em todo o documento e o exemplo da V3 - divergencia de posicao exigindo Position Report, Transaction Report e Movement Report. Isso e reconciliacao de custodia e back-office, e e a dor P2/P3 do `../IDEAS.md` e a solucao candidata B5. **Esta enterrado na secao 5 de 8.**

Isso ataca os dois criterios mais pesados ao mesmo tempo. "Aderencia ao Mercado de Capitais" e criterio de primeira classe na redacao do SharePoint, e "Inovacao e Criatividade" vale 25% - e um agente conversacional que baixa relatorio e a submissao mais comum que existe em hackathon.

**A correcao e de narrativa, nao de engenharia.** Trocar a pele do dominio e promover o caso da V3 para manchete nao muda quase nada do que precisa ser construido, e move duas notas de uma vez.

---

## 2. Nota por criterio

Pesos do regulamento (sec. 17), mais "Aderencia ao Mercado de Capitais", que o SharePoint enuncia como criterio proprio.

| Criterio | Peso | Situacao atual | Por que |
|---|---|---|---|
| Inovacao e Criatividade | 25% | **Fraca** | V1 e deteccao de intencao + extracao de parametro + chamada de API. V2 e NL2SQL. Nenhum dos dois surpreende. A originalidade real esta na V3 e nao tem mecanismo nomeado - "aumentamos o nivel de autonomia" nao e um mecanismo. |
| Valor agregado ao negocio | 25% | **Media** | A dor e real e reconhecivel. Mas o documento nao tem **um unico numero**. Sem numero, "ganho de eficiencia" e adjetivo. |
| Aderencia ao Mercado de Capitais | (1a classe no SharePoint) | **Fraca** | Generico, e confirmado pelo texto submetido (secao 0.1). Corrigivel, mas nao em uma tarde: nenhum integrante e de Capital Markets, o que torna a correcao dependente de revisao externa. Ver secao 3.1. |
| Viabilidade tecnica | 20% | **Forte** | Fronteira LLM/deterministico correta, escopo com premissas explicitas de contencao, mock permitido pelas regras. E o melhor aspecto da proposta. |
| Qualidade da experiencia do usuario | 15% | **Boa, com folga para ganhar** | O loop de pergunta esclarecedora ("Para qual data ou periodo?") ja esta desenhado, o que muitos times esquecem. Falta mostrar plano antes de executar e devolver procedencia junto com o arquivo. |
| Escalabilidade e potencial | 15% | **Forte, se dita da forma certa** | "Adicionar um sistema novo e uma entrada no catalogo mais um conector, nao uma mudanca no agente." A proposta implica isso; precisa afirmar. |

Desempate vai ao VP de Capital Markets, que decide por **maior valor agregado ao negocio** (sec. 17). Mais um motivo para o numero existir.

E o vencedor final e escolhido por **votacao do publico em 28/10**, nao pelo juri tecnico. Plateia nao tecnica vota dor reconhecivel e numero final, nao arquitetura.

---

## 3. As tres correcoes que valem mais

### 3.1 Vestir o dominio - promover a divergencia de posicao a manchete

Reescrever todos os exemplos de V1 e V2 dentro do mesmo caso de custodia/pos-negociacao que a V3 ja usa. Nao inventar dominio novo: **usar o que ja esta la**.

| Onde | Hoje | Trocar por |
|---|---|---|
| V1 exemplo | "Baixe o relatorio de transacoes entre 01/09 e 05/09" | "Baixe o Position Report do fundo X em 05/09" |
| V2.1 exemplo | "Quais informacoes existem no relatorio de transacoes?" | "O que tem no Movement Report?" -> tipo de movimento, quantidade, financeiro, data de liquidacao, contraparte |
| V2.2 exemplo | "moeda = EUR e valor > 500 mil" | "movimentos de liquidacao pendente acima de 500 mil, por contraparte" |
| Join (hoje V2.3, agora dentro do playbook) | transactions + customers por client_id | Position Report + Movement Report por instrumento e data, para achar o movimento sem par |
| V3 | ja esta certo | promover para secao 2, como caso de abertura |

O ganho: a mesma engenharia, mas agora o juri de Capital Markets reconhece o fluxo no primeiro paragrafo. E o exemplo de join deixa de ser um join de demonstracao e passa a ser **a propria investigacao** - o resultado do cruzamento e a resposta, nao um dataset.

#### O custo de credibilidade - o que os papeis do time mudam aqui

**Nenhum dos quatro integrantes e da Business Unit de Capital Markets.** Os cargos sao Analista de Negocios III, Front-End II, Back-End I e Analista de Teste I, todos em PSU BR.

O `../IDEAS.md` ja tinha enunciado o teste, em agosto: *qual das dores o time encosta em trabalho real de cliente?* A resposta honesta e **nenhuma**.

Isso nao invalida a correcao desta secao - mas **muda o seu preco**. Vestir o dominio deixa de ser um ganho gratuito de narrativa e passa a ser uma aposta que precisa de lastro:

| Sem revisao de Capital Markets | Com revisao de Capital Markets |
|---|---|
| A pele de dominio vira **passivo**. Um juri de lideranca de CM identifica detalhe inventado mais rapido do que penalizaria uma demo generica e honesta. | A pele de dominio faz o que se espera dela: move Inovacao e Aderencia ao mesmo tempo. |

**A acao que fecha a lacuna e a de maior alavancagem disponivel ao time hoje:** uma conversa de 30 a 60 minutos com uma pessoa da BU de Capital Markets, para validar o cenario, o vocabulario e o formato dos relatorios. Isso **nao** afeta o limite de 4 integrantes - consultar alguem nao a torna Builder. Perfil natural para conduzir: o Agent Lead, por ser Analista de Negocios e por ja ser o canal externo do time.

Apoio publico enquanto isso: manuais e procedimentos operacionais da B3 sobre custodia e liquidacao, guias operacionais da ANBIMA, dados abertos da CVM.

**Plano B, se a revisao nao acontecer:** manter o enquadramento horizontal do formulario como narrativa principal e escolher um cenario de custodia deliberadamente **simples e publicamente documentado**, em vez de simular profundidade que o time nao tem. Perde nota em Aderencia, e nao perde credibilidade - que e o dano mais caro diante deste juri.

**Restricao imposta pelo texto submetido** (ver secao 0.1, Fato 1): trocar os exemplos, sim; trocar a *afirmacao*, nao. O campo 7 do formulario enuncia um problema horizontal e o campo 9 um publico-alvo amplo. O caso de custodia entra como **onde a dor morde mais forte**, nao como redefinicao do escopo - e o alcance horizontal continua no pitch, no lugar onde ele rende nota: Escalabilidade e potencial de aplicacao, 15%.

### 3.2 Nomear o mecanismo - catalogo semantico e playbooks declarativos

Inovacao nao se ganha dizendo "o agente e inteligente". Ganha-se nomeando uma engrenagem que o juri consiga repetir depois.

**Catalogo semantico.** O agente nao "sabe" dos relatorios por prompt. Ele consulta um registro legivel por maquina: para cada relatorio, os sinonimos pelos quais o usuario o chama, o sistema de origem, o conector, o schema de parametros, as colunas com rotulo em portugues, o grao e as **chaves de join**. Isso e o que faz V1, V2 e V3 serem um sistema so em vez de tres, e e a resposta direta a pergunta de arquitetura da secao 8 do documento.

**Playbooks declarativos.** A V3 nao precisa de autonomia aberta - precisa de **um punhado de playbooks**, e para submeter basta **um**, ponta a ponta (secao 7). Um playbook e um objeto: a necessidade de negocio, seus sinonimos, os datasets exigidos, os passos de montagem, e as **verificacoes de consistencia** (por exemplo: soma dos movimentos do dia deve fechar com a variacao de posicao; se nao fecha, esse e o achado). A V3 passa a ser selecao de playbook mais coleta de parametro, reusando exatamente as tools da V1 e V2.

Isso resolve tres coisas de uma vez: da a V3 um mecanismo demonstravel, torna a V3 barata (nao precisa de capacidade de execucao nova), e e **auditavel** - o que importa para um juri de setor regulado, onde autonomia aberta assusta.

### 3.3 Manifesto de procedencia - o diferencial de setor regulado

Todo resultado entregue sai acompanhado de um manifesto: sistema de origem, horario da extracao, parametros usados, filtros aplicados, chaves de join, contagem de linhas antes e depois de cada filtro.

Por que isso vale desproporcionalmente: em Mercado de Capitais, o problema de um numero nao e produzi-lo, e **defende-lo**. Um analista que leva um numero para o gestor precisa dizer de onde veio. Nenhum outro time vai fazer isso, custa pouco (o backend ja conhece tudo isso), aparece na tela na demo, e converte "demo legal" em "ferramenta auditavel".

Vem junto o invariante que vale escrever no one-pager: **o agente nunca escreve um numero que nao tenha vindo de uma tool.** Toda cifra na tela e renderizada verbatim da saida do backend. Isso e uma definicao de pronto testavel e uma frase de pitch forte.

E aqui a composicao do time vira ativo: **ha um Analista de Teste na equipe.** O invariante e uma afirmacao *testavel*, e ter quem a comprove transforma promessa em evidencia - a diferenca entre dizer ao juri "o agente nao inventa numeros" e mostrar a suite que prova. Diante de um juri de setor regulado, esse e provavelmente o argumento mais forte da proposta, e e o unico que pode ser demonstrado em vez de afirmado. Quase nenhum time de hackathon tem QA para isso.

---

## 4. O numero que falta

Nada aqui exige dado real - o `../RULES.md` proibe dado real de cliente. Basta um conjunto de premissas declaradas, com ordem de grandeza, assinado pelo time.

Esqueleto para preencher com a experiencia de quem esta no time:

- Extracoes manuais por analista por dia: **N**
- Tempo medio por extracao, incluindo achar o sistema, logar, parametrizar, exportar e tratar: **T** minutos
- Analistas na operacao: **A**
- Horas por mes = N x T x A x 21 / 60

Depois o segundo andar, que e onde esta o dinheiro de verdade: uma investigacao de divergencia de posicao hoje custa **M** minutos entre tres sistemas e uma planilha; com o playbook, custa a conversa. Esse e o numero que vai para o slide de fechamento.

Regra de honestidade: rotular como premissa, nao como medicao. Um juri de Capital Markets perdoa premissa declarada e nao perdoa numero inventado apresentado como fato.

**Refinamento vindo da revisao externa (secao 11): melhor que declarar premissa e CITAR.** Um numero de fonte publica de industria - ANBIMA, B3, relatorio de associacao setorial, pesquisa de operacoes de custodia - vale mais que uma premissa do time, porque o desempate do juri e por valor de negocio e uma cifra com fonte carrega sozinha.

**Mas a ordem importa, e aqui a revisao externa erra por excesso de confianca.** Ela sugeriu uma citacao especifica com numero e ano, apresentada como fato, que ninguem do time abriu. **Citacao fabricada e infinitamente pior que premissa honesta** - diante deste juri, uma fonte que nao existe e o unico erro que destroi a submissao inteira. Logo:

1. Se alguem do time **abrir a fonte e ler o numero**, cite com referencia completa.
2. Se nao houver fonte verificavel a tempo, **declare como premissa do time**, com o esqueleto acima.
3. Nunca o meio do caminho - numero com aparencia de fonte, sem fonte conferida.

---

## 5. Arquitetura sugerida - Gemini Enterprise e GCP

Restricao dura (sec. 12): o agente final tem de estar implementado, configurado, integrado, executavel e disponivel para avaliacao nos padroes **Gemini Enterprise + GCP**. Fora disso, desclassificacao.

**Ressalva removida em 08/09.** O que estava aqui - "o Guia Tecnico pode invalidar estas escolhas" - **caiu**: nao existe Guia Tecnico separado (`../GUIA_TECNICO_RESPOSTA.md`). Os limites aplicaveis sao o regulamento sec. 12, 13 e 14 mais a pagina do SharePoint, e nada mais vai chegar. As escolhas abaixo podem ser assumidas.

### Camadas

| Camada | Componente | Papel |
|---|---|---|
| Conversa | Agente no Gemini Enterprise | Entendimento, elicitacao de parametro, selecao de tool, apresentacao. Nunca calcula. |
| Contrato | Tools via OpenAPI | Fronteira unica entre linguagem natural e execucao |
| Execucao | Cloud Run (backend deterministico) | Valida spec, chama conectores, executa filtro e join, gera arquivo e manifesto |
| Dados | **Em memoria no proprio Cloud Run** (DuckDB ou pandas) | Motor de filtro e join. **Trocado em 08/09** - ver abaixo |
| Entrega | Cloud Storage + URL assinada | Arquivo final para o usuario |
| Registro | Cloud Logging | Toda spec executada fica registrada - e isso que sustenta a procedencia |
| Segredo | Secret Manager | Chaves das APIs mockadas |

**BigQuery saiu, e essa e uma correcao a minha propria recomendacao anterior.** Eu havia posto BigQuery como zona de pouso e motor de join. A revisao externa (secao 11) apontou o obvio: o acervo mockado e minusculo. BigQuery acrescenta dataset a provisionar, custo, latencia e um passo de deploy a mais - e **zero valor de demo**, porque ninguem no juri ve onde o join aconteceu. Era eu fazendo casamento de padrao com "plataforma de dados corporativa" para um problema que nao tem volume.

Join em memoria no proprio Cloud Run resolve, e o contrato de tools nao muda em nada: `run_query(spec)` continua recebendo a mesma spec validada. Se algum dia houver volume real, BigQuery entra atras da mesma tool, sem tocar no agente - o que, aliais, e a prova de que a fronteira esta no lugar certo.

### Contrato de tools - o que faz V1 servir a V3 sem retrabalho

- `list_reports(query)` - devolve subconjunto do catalogo
- `describe_report(report_id)` - colunas, parametros, grao (esta tool **e** a V2.1)
- `fetch_report(report_id, params)` - referencia do arquivo, contagem de linhas, manifesto
- `run_query(spec)` - `spec` = `{sources[], select[], filters[], joins[], limit}`, validado por JSON Schema e executado pelo backend (SQL em DuckDB sobre os extratos em memoria)
- `deliver(result_ref, format)` - CSV ou XLSX via URL assinada
- `list_playbooks(need)` / `get_playbook(id)` - a V3

**A regra que sustenta tudo:** o LLM emite **spec**, nunca SQL livre e nunca numero. O backend valida a spec contra schema e so entao executa. Isso remove a classe inteira de risco de alucinacao em cifra, e e a resposta a pergunta 6 da secao 8 do documento - sim, a V1 suporta as evolucoes sem reconstrucao, sob duas regras: **catalogo como dado** e **LLM so emite spec**.

### Seguranca e conformidade - a caixa que faltava no diagrama

**Esta e a lacuna que a revisao externa encontrou e eu nao tinha.** O diagrama que eu propus tinha Secret Manager e Cloud Logging, mas nao tinha uma **historia de seguranca** - e a unica exigencia que a Organizacao acrescentou de proprio punho foi justamente "que as pessoas cuidem da questao de privacidade de dados, seguranca e afins" (`../GUIA_TECNICO_RESPOSTA.md`). Um diagrama de arquitetura para setor regulado sem caixa de seguranca e um sinal negativo, nao uma omissao neutra.

Custa quase nada desenhar, e sinaliza ao juri que o time conhece o ambiente:

| Controle | O que dizer no diagrama |
|---|---|
| **Nenhum dado bruto no contexto do agente** | O agente trafega **referencias** (report_id, result_ref), nunca linhas de dado. E o controle mais forte da lista, e cai de graca da regra "o LLM emite spec" |
| Perimetro | VPC Service Controls em volta do projeto |
| Cifragem | CMEK em Cloud Storage; cifragem em repouso declarada |
| Trilha de auditoria | Cloud Audit Logs com sink imutavel - e o que sustenta o manifesto de procedencia |
| Segredos | Secret Manager; nunca em codigo, nunca em documento |
| IAM | Service account propria por conector, com o menor privilegio; o agente nao tem acesso direto as fontes |
| Dados | Somente mock/sintetico/publico. Sem dado pessoal, sem base de producao (sec. 13) |

O primeiro item merece destaque no pitch: **o agente nunca ve o dado, so a referencia.** Isso e simultaneamente um controle de privacidade e a razao pela qual o agente nao consegue inventar uma cifra - o mesmo desenho serve aos dois argumentos.

### Nomear as primitivas, pelo parceiro que esta no juri

O juri inclui o **Google** como parceiro tecnologico. "Agente no Gemini Enterprise" e vago demais para quem constroi a plataforma. O diagrama e o one-pager devem nomear as primitivas concretas que estao sendo usadas - agente e ferramentas no Gemini Enterprise, execucao serverless em Cloud Run, Cloud Storage, Secret Manager, Cloud Logging - e evitar qualquer coisa que pareca VM ou infraestrutura administrada a mao. Um desenho que se le como "o jeito Google de fazer" ganha o parceiro; um desenho genericamente nublado nao.

Conferir os nomes exatos dos servicos e dos modelos no console antes de publicar o PDF. A revisao externa citou uma geracao de modelo desatualizada - lembrete de que nome de servico e algo para copiar da tela, nao de memoria.

### Dois detalhes baratos que compram credibilidade

**Conectores heterogeneos - dois, nao tres.** Os "sistemas" mockados devem ser servicos separados com estilos de acesso de verdade diferentes. Se forem rotas do mesmo servidor, o juri percebe e a abstracao de conector perde o argumento - e o campo 8 do formulario **prometeu** "adaptacao a diferentes sistemas, APIs e mecanismos de automacao", entao isso e evidencia de uma afirmacao ja feita, nao enfeite.

A revisao externa (secao 11) recomendou cortar para **um** mock. Discordo pela metade: com um so, a promessa do campo 8 fica sem prova. Com dois de naturezas opostas - **um REST/JSON paginado com auth e modos de erro, e um arquivo em Cloud Storage simulando entrega batch** - a abstracao fica demonstrada. O terceiro (XML) era luxo: mesma prova, mais horas de um dev junior. **Cortado.**

**Uma integracao real dentro do mundo mockado.** Conversao de moeda usando a serie de PTAX do Bacen (SGS) e dado publico, permitido pelo `../RULES.md`, custa quase nada e quebra o cheiro de "esta tudo mockado" que o `../IDEAS.md` aponta como prejuizo de credibilidade de demo. Alternativas publicas: dados abertos da CVM, manuais e avisos da B3.

Cuidado de LGPD: `customer_name` no exemplo da V2.3 e um convite a alguem popular a base com nome de cliente real. Mock ostensivamente sintetico, e dito em voz alta para o time.

Isso ganhou peso em 08/09: ao responder sobre o Guia Tecnico, a **unica exigencia que a Organizacao acrescentou de proprio punho** foi *"que as pessoas cuidem da questao de privacidade de dados, seguranca e afins"*. Deixou de ser clausula no PDF e passou a ser pedido explicito de quem organiza - e de quem monta o juri.

---

## 6. Respostas as sete perguntas da secao 8 do documento

**1. Visao - faz sentido essa evolucao?**
Sim como sequencia de engenharia. Nao como sequencia de narrativa. Construir de baixo para cima (V1 primeiro), **contar** de cima para baixo (abrir pela necessidade de negocio). Hoje o documento conta de baixo para cima, e por isso a leitura de abertura e "chatbot que baixa relatorio".

**2. Priorizacao - V2 e V3 estao na ordem correta?**
A ordem de construcao esta correta, e ha um motivo estrutural: cada incremento adiciona **um conjunto de campos ao mesmo catalogo**. V2.1 precisa de colunas e rotulos. V2.2 precisa de tipos e dominios para virar filtro. V2.3 precisa de chaves de join. V3 precisa de playbooks apontando para report_ids. Nao ha como fazer V2.3 antes de V2.2 sem trabalho jogado fora.
Uma correcao de escopo, nao de ordem: a V3 nao deve ser tentativa de autonomia geral. **Playbooks fechados** entregam a demo e sao honestos sobre o que o sistema faz - um basta para submeter, dois se houver folga.

E uma correcao de prioridade, vinda do texto submetido: **pelo menos um playbook nao e opcional** - o campo 8 do formulario o prometeu. Na pratica isso puxa a V3 para *antes* da V2.2 na ordem de entrega, ainda que a V2.1 continue vindo primeiro por sair de graca do catalogo. Ver secao 0.1, Fato 2.

**3. Viabilidade - o que e simples e o que e complexo?**

| Simples | Medio | Arriscado dentro do prazo |
|---|---|---|
| V1 ponta a ponta | V2.2 - spec validada por schema | V2.3 com join arbitrario entre fontes quaisquer |
| V2.1 - e so ler o catalogo | V2.3 com conjunto fixo de chaves | V3 como autonomia aberta |
| Entrega de arquivo e manifesto | Elicitacao de parametro multi-turno | Estado conversacional em sessao longa |
| Playbooks declarativos | Conectores heterogeneos | Casos de borda de formato de arquivo (encoding, decimal, data) |

Observacao contraintuitiva: **os playbooks da V3 sao mais faceis que a V2.3 aberta.** Playbook e configuracao. Join arbitrario e problema de engenharia de dados. Se o prazo apertar, cortar V2.3 aberta e manter playbook - o resultado demonstravel e melhor.

**4. Escopo - qual o minimo para a V1 ser realmente funcional?**
Definicao de pronto, para congelar hoje:
- 1 agente no Gemini Enterprise, 3 tools, 3 relatorios, 2 sistemas de origem distintos
- Caminho feliz completo: pedido -> identifica relatorio -> extrai parametro -> **mostra o plano** -> usuario confirma -> executa -> entrega arquivo + manifesto
- Tres caminhos de falha tratados: parametro ausente (pergunta), relatorio desconhecido (oferece os candidatos mais proximos do catalogo), resultado vazio (diz que veio vazio e mostra os filtros aplicados)
- Invariante verificado: nenhum numero na tela que nao tenha vindo de tool

Se isso esta de pe, a V1 esta funcional como **fundacao**, mesmo que V2 e V3 nao existam.

**Correcao, apos ver o texto submetido:** eu havia escrito aqui que a V1 sozinha ja seria submissao valida. **Nao e.** O campo 8 do formulario promete que o agente identifica quais relatorios e fontes sao necessarios - comportamento de V3. A V1 sozinha subentrega contra o escopo submetido. O minimo para *submeter* passa a ser **V1 como fundacao mais um playbook de V3 ponta a ponta**. Ver secao 0.1, Fato 2.

**5. Evolucao - V2.1, V2.2 e V2.3 fazem sentido como incrementos separados?**
Sim, e o teste e este: cada um e demonstravel sozinho e mapeia 1 para 1 em campos do catalogo (ver resposta 2). Sao incrementos de verdade, nao fatiamento artificial.

Ressalva de escopo desta entrega: a **V2.3 com join arbitrario saiu do plano** (secao 7). Isso nao contradiz o desenho - o join de que a demo precisa vive dentro do playbook, com chaves fixas. Se a V2.3 aberta voltar depois, volta nesta mesma posicao, nunca antes da V2.2.

**6. Arquitetura - a V1 suporta as evolucoes sem grande retrabalho?**
Sim, sob duas regras nao negociaveis: **catalogo como dado**, nunca como prompt; e **o LLM emite spec, nunca execucao**. Violar a primeira faz cada relatorio novo virar edicao de prompt. Violar a segunda faz a V2.3 exigir reescrita e traz risco de alucinacao em cifra.

**7. Outras ideias**
- Manifesto de procedencia (secao 3.3) - o diferencial de setor regulado
- Mostrar plano antes de executar, com confirmacao - UX e auditabilidade no mesmo gesto
- Verificacoes de consistencia dentro do playbook - transformam "buscar dados" em "achar o problema", que e o salto de valor real da V3
- Previa das primeiras linhas na conversa, alem do arquivo - o usuario nao precisa abrir o download para saber se acertou
- Falar as colunas no vocabulario do usuario, nao do schema
- PTAX do Bacen como integracao real dentro do mundo mockado

---

## 7. Plano de 22 dias - de 08/09 a 30/09

Prazo duro: **30/09** e o ultimo dia para enviar o agente. Sao 22 dias corridos, e a janela de entregaveis e ensaio vai de 25/09 a 29/09. Ou seja: **restam cerca de 12 dias de construcao**, nao 22.

Reordenado duas vezes em 08/09. Primeiro apos a leitura do texto submetido: o playbook de V3 subiu de "se houver folga" para **obrigatorio**, porque e o que o campo 8 prometeu (secao 0.1, Fato 2), e o join arbitrario da V2.3 desceu para fora de escopo. Depois apos a revisao externa (secao 11), que fez a conta de horas de backend que eu nao tinha feito: **o corte anterior nao era suficiente**.

**Aritmetica que muda a conversa.** O nucleo deterministico e trabalho de um unico dev junior, em horario voluntario, com cerca de 12 dias uteis. Isso da uma ordem de grandeza de **60 a 80 horas de backend** - e a lista que eu havia recomendado (conectores, validacao, joins, arquivo, manifesto, camada OpenAPI, BigQuery, deploy, seguranca) passa facil de **120**. Nao fecha. Logo:

| Fora de escopo | Por que |
|---|---|
| **BigQuery** | Acervo mockado e minusculo; join em memoria resolve. Zero valor de demo (secao 5) |
| **V2.3 com join arbitrario** | O playbook cobre o join que a demo precisa, com chaves fixas |
| **Terceiro conector (XML)** | Dois de naturezas opostas ja provam a abstracao (secao 5) |
| **V2.2 como capacidade de usuario** | Filtro em linguagem natural e bonito e nao aparece no roteiro do video. Os filtros de que a demo precisa vivem no playbook |

**Continua dentro:** catalogo semantico como dado, um playbook ponta a ponta, manifesto de procedencia, passo de plano-e-confirmacao, V2.1 (que e so ler o catalogo), dois conectores, caixa de seguranca no diagrama, e a suite que prova o invariante.

| Janela | Foco | Saida |
|---|---|---|
| 08/09 - 10/09 | Congelar escopo **contra o texto submetido**. Confirmar homologacao do repositorio de codigo. Fechar o conjunto de premissas do numero. | Escopo congelado, numero acordado |
| 08/09 - 15/09 | Catalogo semantico como dado. Dois servicos mockados heterogeneos. V1 ponta a ponta no Gemini Enterprise. | Fundacao pronta |
| 15/09 - 21/09 | **Um playbook de V3 ponta a ponta** - divergencia de posicao, com verificacao de consistencia. V2.1, que sai quase de graca do catalogo. Manifesto de procedencia. Passo de plano e confirmacao. | **A demo que o texto submetido promete** |
| 22/09 - 24/09 | Caixa de seguranca no diagrama. Integracao. **Congelar codigo em 24/09.** Segundo playbook ou V2.2 somente se houver folga real - e provavelmente nao havera. | Demo completa |
| 24/09 - 28/09 | **Roteiro do video primeiro**, depois gravacao, incluindo take de reserva. One-pager e PDF de arquitetura. | Pacote de submissao |
| 29/09 | Folga deliberada. Revisao, ensaio, correcao do que aparecer. | Margem |
| 30/09 | Enviar de manha, nao no fim do dia | Submetido |

**A folga de 29/09 e proposital.** A revisao externa apresentou um cronograma de 12 dias com "buffer: 0 dias" como se fosse virtude. Em projeto voluntario com prazo duro, folga zero nao e plano - e a primeira coisa que quebra. O congelamento de codigo em 24/09 e o dia livre em 29/09 existem para absorver o imprevisto que certamente aparece.

O ponto que mais derruba time e este: os entregaveis obrigatorios sao **100% do que o juri ve**, e a pagina do Loop planeja evolucao de produto sem mencionar nenhum deles.

**Sao cinco, nao quatro** - o e-mail de aprovacao de 10/09 acrescentou o GitLab (`../APROVACAO.md`).

| Entregavel | O que nao pode faltar |
|---|---|
| One-pager (PDF) | O numero. A dor em uma frase reconhecivel por quem e de Capital Markets. |
| Video com pitch e demo | Take de reserva gravado. Demo ao vivo falha, e falha na hora errada. |
| Demo funcional | Rodando em Gemini Enterprise, nao em notebook local |
| Arquitetura (PDF) | A fronteira LLM/deterministico **desenhada**. E o argumento de viabilidade tecnica em forma visual. |
| **GitLab GFT** *(novo, 10/09)* | Artefatos de desenvolvimento no diretorio da equipe. Unico entregavel que nao se produz no fim - precisa acumular historico durante a construcao. |

**E uma exigencia que atravessa os cinco:** o padrao Google Enterprise AI e obrigatorio em **todos os entregaveis**, nao so no agente que roda. Isso sobe a barra do PDF de arquitetura e do video.

---

## 8. Coreografia - sao DUAS pecas, para DUAS plateias

**Correcao de 08/09, vinda da revisao externa (secao 11).** Eu tratava a coreografia como uma coisa so. Sao duas, com publicos e prazos diferentes:

| Peca | Plateia | Quando | Criterio que serve |
|---|---|---|---|
| **Video com pitch e demo** | Plateia nao tecnica que **vota** | Gravado ate 29/09, visto na final de 28/10 | A votacao do publico decide 1o, 2o e 3o |
| **Demo funcional** | Juri tecnico + parceiro Google | Avaliacao de 01/10 a 15/10 | Viabilidade tecnica (20%), UX (15%) |

**Consequencia de ordem: escrever o roteiro do video PRIMEIRO, e tratar a demo ao vivo como um subconjunto dele.** Isso inverte o instinto natural do time - construir e depois filmar. Toda decisao tecnica deveria passar pelo teste "isso aparece no video?"; o que nao aparece compete por horas de um dev junior contra o que aparece.

### O roteiro do video - o que a plateia entende

A plateia **nao** entende catalogo semantico, manifesto de procedencia nem playbook declarativo. Entende antes e depois.

1. **A dor, visceral, nos primeiros 15 segundos.** Nao um diagrama: gravacao de tela real de alguem abrindo tres sistemas, exportando CSV e fazendo PROCV numa planilha. O tedio precisa ser visivel.
2. **Uma frase para o agente:** "preciso investigar a divergencia de posicao do fundo X de ontem".
3. **O agente mostra o plano** - quais relatorios, de quais sistemas, com quais parametros - e o usuario confirma. E aqui que a plateia ve **raciocinio em vez de caixa preta**, e e o que separa isto de um chatbot.
4. **Executa:** dois sistemas de naturezas diferentes, join, verificacao de consistencia, e acha o movimento sem par.
5. **O momento do recibo:** manifesto na tela - origem, horario, contagem de linhas, e a verificacao que falhou destacada. O que a plateia precisa pensar e *"eu conseguiria defender isso para o auditor"*.
6. **Fecha no numero:** de **M minutos** para segundos.
7. **Uma frase de escala:** adicionar um sistema e uma entrada no catalogo - nao uma mudanca no agente.

O passo 3 separa a demo de um chatbot. O passo 5 e o que um juri de setor regulado guarda. O passo 6 e o que ganha voto.

### A demo funcional - o que o juri tecnico ve

Mesmo fluxo, mas com o que a plateia nao precisa: a spec validada, o catalogo como dado, a fronteira LLM/deterministico, a caixa de seguranca, e a suite de teste que prova o invariante anti-alucinacao. Rodando em Gemini Enterprise, nao em maquina local.

---

## 9. Riscos

| Risco | Gravidade | Mitigacao |
|---|---|---|
| ~~Reposicionamento contradiz a proposta aprovada~~ | resolvido | Texto lido em 08/09 (`PROPOSTA_SUBMETIDA.md`). E neutro de dominio, nao contrario: a demo em custodia evidencia o texto em vez de contradize-lo. |
| **Entregar so V1 subentrega contra o texto submetido** | **Alta** | O campo 8 prometeu identificacao de necessidade. Um playbook de V3 ponta a ponta e obrigatorio, e entra na janela de 15/09 a 21/09. |
| Perder a afirmacao horizontal ao vestir o dominio | Media | O alcance amplo dos campos 7 e 9 e o argumento de Escalabilidade (15%). Custodia e onde a dor morde, nao o novo escopo. |
| **Pele de dominio sem lastro - nenhum integrante e de Capital Markets** | **Alta** | Revisao do cenario por alguem da BU de CM antes de fechar demo e one-pager. Consultar nao torna a pessoa integrante, logo nao afeta o limite de 4. Sem isso, preferir cenario simples e publicamente documentado a profundidade simulada. |
| Nucleo deterministico concentrado em um unico dev de nivel I | Media | Cortar V2.3 com join arbitrario. Conectores mockados simples de construir, ainda que heterogeneos em estilo. Front-End e QA absorvem parte do trabalho de tool e fixture. |
| ~~Guia Tecnico nao obtido - pode invalidar arquitetura~~ | resolvido | Nao existe documento separado (`../GUIA_TECNICO_RESPOSTA.md`). Nada mais vai chegar. Segue valendo que descumprir o padrao Gemini Enterprise/GCP desclassifica. |
| ~~Codigo do desafio em plataforma possivelmente nao homologada~~ | **respondido, e trocado por outro** | O e-mail de aprovacao de 10/09 nomeou o ambiente: **GitLab da GFT**, diretorio da equipe (`../APROVACAO.md`). Sai a duvida sobre homologacao, entra o risco novo: **o acesso ao GitLab nao foi confirmado** e era para ate ~18/08. Como o diretorio da equipe virou o **quinto entregavel obrigatorio**, acesso ausente ou diretorio vazio em 30/09 e entregavel faltando - cobrar hoje, nao na ultima semana. |
| Escopo espalhado por V1, V2 e V3 sem nenhum completo | Alta | Congelar definicao de pronto da V1 hoje. Freeze de codigo em 25/09. |
| Leitura de "chatbot generico" pelo juri | Alta | Pele de dominio + mecanismo nomeado + procedencia (secao 3) |
| Ausencia de numero | Alta | Conjunto de premissas fechado esta semana. Desempate e por valor de negocio. |
| Agente alucina cifra | Media | Invariante: nenhum numero fora de saida de tool. Renderizar verbatim. |
| "Esta tudo mockado" corroi credibilidade | Media | Uma integracao publica real (PTAX/Bacen, CVM, B3) |
| Falha da demo ao vivo | Media | Take de reserva gravado |
| Dado pessoal entrando no mock | Media | Mock ostensivamente sintetico. Violacao e desclassificacao imediata (sec. 13). |
| Entregaveis comprimidos na ultima semana | Media | Reservar 25/09 a 29/09 e nao usar para codigo |
| Ponto unico de falha na submissao - so o Agent Lead envia | Media | Plano B por escrito, e envio antes do dia 30 |
| **Backend rodando fora do padrao Gemini Enterprise/GCP** | **Alta - desclassificacao** | Tentacao real quando o prazo aperta, e a revisao externa chegou a recomendar backend local com tunel. Sec. 12 exige o agente executavel e disponivel para avaliacao NO padrao GE/GCP. Cloud Run e um comando de deploy - nao e aqui que se economiza hora |
| Diagrama de arquitetura sem historia de seguranca | Media | Caixa de seguranca e conformidade (secao 5). Privacidade e seguranca foram a unica exigencia que a Organizacao acrescentou de proprio punho |
| Numero de impacto com fonte inventada | **Alta** | Citar somente fonte que alguem do time abriu; senao, declarar como premissa. Fonte inexistente e o unico erro que derruba a submissao inteira (secao 4) |
| Video tratado como embalagem, e nao como entregavel | Media | Roteiro do video primeiro; demo ao vivo como subconjunto. A plateia que vota ve o video, nao a arquitetura (secao 8) |
| Elegibilidade de 4 pessoas nao verificada | Media | Conferencia individual; vale ate a divulgacao do resultado, nao so na inscricao |

---

## 10. Acoes imediatas

Donos registrados em `../checkpoint.json`, chave `proximas_acoes`.

1. **Fechar o escopo minimo como V1 mais um playbook de V3**, nao V1 sozinha - e o que o campo 8 do formulario prometeu, e e a decisao que reordena o cronograma (secao 0.1, Fato 2; secao 7). *Decisao coletiva.*
2. **Achar e agendar uma pessoa da BU de Capital Markets** para revisar o cenario da demo, o vocabulario e o formato dos relatorios. Sem isso a manchete de custodia fica sem lastro (secao 3.1). **Acao de maior alavancagem disponivel hoje.** *Agent Lead.*
3. ~~Confirmar se o GitHub usado pelo time e ambiente homologado.~~ **Respondido: e o GitLab da GFT.** No lugar: **cobrar o provisionamento do acesso ao GitLab e comecar a versionar os artefatos no diretorio da equipe** - prazo estourado desde ~18/08, e o diretorio e o quinto entregavel obrigatorio (`../APROVACAO.md`). *Agent Lead para cobrar, Back-End para povoar.*
4. **Fechar o conjunto de premissas do numero** (secao 4), com o insumo da revisao da acao 2 - ninguem no time tem a vivencia operacional, e o formulario nao traz numero algum. *Agent Lead.*
5. **Escolher o caso de custodia da demo** e trocar os exemplos de V1 e V2 para ele, **mantendo** a afirmacao horizontal como argumento de escala (secao 3.1). *Decisao coletiva.*
6. **Distribuir o trabalho conforme os papeis** - mapeamento em `../PLAN.md`, "Como os papeis encaixam no trabalho". Dois dos tres diferenciais sao front-end, e o invariante anti-alucinacao e trabalho de QA. *Time.*
7. ~~Confirmar a **aprovacao pelo comite** e o nome do **time** registrado.~~ **Feito - aprovada em 10/09, time OneAsk** (`../APROVACAO.md`). No lugar: **cobrar o aceite das tres inscricoes individuais** regularizadas em 09/09. *Agent Lead.*
8. Confirmar se as **licencas Gemini Enterprise** estao liberadas para os 4. *Agent Lead.*
9. **Cada integrante confere a propria elegibilidade** e a autorizacao do gestor imediato para dedicacao em expediente. Com 4 pessoas, um inelegivel custa R$ 750 que ninguem recebe em caso de primeiro lugar - a parcela nao e redistribuida (sec. 19). *Cada um dos 4.*
10. Combinar um **plano B de submissao** caso o Agent Lead esteja indisponivel em 30/09, e nao deixar o envio para o proprio dia 30. *Agent Lead.*
11. **Escrever o roteiro do video antes de construir o resto** - a plateia que decide o 1o lugar ve o video, nao a arquitetura (secao 8). *BA, com o Front-End.*
12. **Desenhar a caixa de seguranca e conformidade** no PDF de arquitetura, comecando por "o agente nunca ve dado bruto, so referencia" (secao 5). *Back-End com o BA.*
13. **Reservar 24/09 a 28/09 para os entregaveis de documento e video**, com 29/09 de folga deliberada, e nao usar nenhuma das duas janelas para codigo. O quinto entregavel - o diretorio no GitLab - **nao cabe nesta janela**: ele se constroi desde o primeiro commit. *Time.*
14. Reatualizar `../PLAN.md` e `../checkpoint.json` quando as confirmacoes restantes chegarem.

**Ja resolvido, e por isso fora da lista:** o texto submetido (`PROPOSTA_SUBMETIDA.md`), a composicao do time, o Agent Lead e os papeis profissionais (`../PLAN.md`, "O time"), e o Guia Tecnico - que nao existe (`../GUIA_TECNICO_RESPOSTA.md`).

---

## 11. Segunda opiniao externa - o que foi aceito e o que foi rejeitado

Em 08/09 esta avaliacao foi submetida a um modelo externo, com instrucao explicita de **contestar** em vez de validar. O briefing enviado descrevia o concurso, o texto submetido, a escada V1/V2/V3, as recomendacoes desta avaliacao e a composicao do time **por papel, sem nome, e-mail ou horario de ninguem**.

**Procedencia, e ela importa para o peso da opiniao:** os modelos de topo da cadeia falharam e a resposta veio de um modelo gratuito de porte menor. Sinal concreto de desatualizacao: ele citou uma geracao de modelo Gemini de 2024. Logo, leitura externa util - nao autoridade.

### O que ele encontrou e eu nao tinha - aceito

| Achado | O que mudou aqui |
|---|---|
| **Faltava historia de seguranca no diagrama** | Nova subsecao na secao 5. O melhor item e dele: *nenhum dado bruto no contexto do agente, so referencia* - controle de privacidade e explicacao de por que o agente nao inventa cifra, no mesmo desenho |
| **Video e demo ao vivo sao pecas diferentes** | Secao 8 reescrita. Duas plateias, dois prazos, e a ordem inverte: **roteiro do video primeiro** |
| **O parceiro Google esta no juri e precisa ver a stack dele** | Nova subsecao na secao 5: nomear primitivas concretas em vez de "agente no Gemini Enterprise" |
| **A conta de horas de backend nao fechava** | Secao 7: cortes mais fundos. BigQuery, terceiro conector e V2.2 sairam. Meu corte anterior (so a V2.3) era insuficiente |
| **Citar e melhor que declarar premissa** | Secao 4, com a ressalva de que citacao nao conferida e pior que premissa honesta |

O achado de horas e o mais valioso: eu havia recomendado cortar a V2.3 e mantido BigQuery, camada OpenAPI e tres conectores para um dev junior em horario voluntario. Era otimismo disfarcado de plano.

### O que rejeitei, e por que

| Recomendacao dele | Por que nao |
|---|---|
| **Rodar o backend localmente, atras de tunel** | **Gatilho de desclassificacao.** O argumento dele - "o juri avalia o agente, nao sua maturidade de ops em GCP" - le a psicologia do juri e ignora a regra: sec. 12 exige o agente implementado, configurado, integrado, **executavel e disponivel para avaliacao nos padroes Gemini Enterprise/GCP**. Tunel para maquina local e exatamente o que a clausula veda, e ainda trafegaria conteudo interno por terceiro |
| **Camada OpenAPI e trabalho inutil** | A integracao nativa de ferramentas do Gemini Enterprise espera schema OpenAPI. Chamar HTTP cru pode nem ser caminho suportado - conferir no console antes de cortar |
| **Cortar a V2 inteira** | Impreciso. A V2.1 e a tool `describe_report` lendo o catalogo que ele mesmo mantem: custo proximo de zero e um beat de conversa a mais. Cortei a V2.2, nao a V2 |
| **Um unico conector mockado** | Deixaria sem prova a promessa do campo 8 de "adaptacao a diferentes sistemas, APIs e mecanismos de automacao". Fiquei em dois, de naturezas opostas |
| **"Buffer: 0 dias. That's the plan."** | Folga zero em projeto voluntario com prazo duro nao e plano. Mantive congelamento em 24/09 e 29/09 livre |
| **Abandonar o dominio de custodia** | Ele abre dizendo que C1 e o erro mais provavel e fecha recomendando *"demo on one CM workflow (position break) using real CM vocabulary from a 1-hour SME session"* - que e a C1 com o pre-requisito de revisao que ela ja tinha. Convergencia apresentada como refutacao |

### O que vale roubar da forma dele de dizer

- **"We solved the pattern, not one instance"** - enquadramento forte para Escalabilidade (15%), e resolve a tensao entre proposta horizontal e demo vertical melhor que a minha redacao.
- **"Se insistir em custodia, o caso da V3 tem de ser o UNICO cenario da demo"** - estreitar ate caber numa conversa de uma hora com quem e do dominio. Aperto util da C1.
- **"O momento do recibo"** para o manifesto, e *"eu conseguiria defender isso para o auditor"* como o pensamento que se quer na plateia.

### O que sobreviveu intacto

Fronteira LLM/deterministico, catalogo como dado, playbooks como configuracao, manifesto de procedencia, verificacoes de consistencia, o invariante anti-alucinacao, e o minimo de V1 mais um playbook. A revisao nao derrubou o nucleo - encontrou uma lacuna (seguranca), uma distincao (video e demo) e cortou mais fundo que eu no escopo.
