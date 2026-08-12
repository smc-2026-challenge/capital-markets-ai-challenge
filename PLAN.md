# Plano - Desafio Capital Markets AI Agents Challenge (SMC 2026)

Data do checkpoint: **12/08/2026**. Versao legivel por maquina: `checkpoint.json`.
Arquivos companheiros: `RULES.md` (resumo do regulamento), `IDEAS.md` (espaco de problemas e catalogo de solucoes), `NAMES.md` (candidatos a nome do time).

> Este arquivo esta em pt-BR sem acentuacao (ASCII puro), para nao quebrar em formularios, nomes de arquivo e terminais.

## Onde estamos

| Item | Situacao |
|---|---|
| Regulamento lido | Feito - regulamento de 22 paginas + pagina do SharePoint |
| Composicao do time / Agent Lead | Nao definida |
| Direcao de problema e solucao | Nao decidida - opcoes catalogadas em `IDEAS.md`, nenhuma aceita |
| Nome do time | Nao decidido - candidatos em `NAMES.md` |
| Inscricao | Nao enviada |
| Guia Tecnico | Nao obtido (e parte integrante das regras - solicitar) |

## Datas duras

Inscricao encerra em **28/08** - 16 dias a partir da data do checkpoint. Entrega do agente encerra em **30/09**. Finalistas anunciados em **16/10**. Apresentacao final e votacao do publico em **28/10**.

Cronograma completo em `RULES.md`.

## Caminho critico

1. **Confirmar a elegibilidade de cada integrante pretendido.** Somente CLT. Bench/Staff, aviso previo, qualquer afastamento, L7 ou superior quando impedido e processo disciplinar em curso desclassificam - e a parcela do premio de um integrante inelegivel **nao** e redistribuida ao resto do time. Verificar isso antes de escrever qualquer coisa.
2. **Solicitar o Guia Tecnico** a Organizacao (Evelim Buratti, emro@gft.com). Ele define os requisitos de arquitetura, integracao, seguranca, execucao e apresentacao, e parte formal das regras, e o descumprimento dos padroes Gemini Enterprise / GCP e gatilho explicito de desclassificacao. Construir antes de le-lo e construir no escuro.
3. **Fechar problema e solucao.** Ver o portao de decisao abaixo.
4. **Fechar nome do time e Agent Lead.**
5. **Cada integrante envia o formulario individual de inscricao** antes de 28/08. A inscricao e por pessoa mesmo em participacao em equipe, e as vagas sao limitadas - nao deixar para a ultima semana.
6. **Escrever o texto da proposta** para o formulario: problema, solucao, impacto esperado e por que importa para o Mercado de Capitais.

## Portao de decisao - escolha do problema

Os dois criterios mais pesados sao Valor de Negocio (25%) e Inovacao (25%), e a redacao do SharePoint ainda adiciona "Aderencia ao Mercado de Capitais" como criterio de primeira classe. Isso significa que a combinacao vencedora e *um problema sobre o qual o time fala com credibilidade* mais *um mecanismo que nao pareca obviamente um chatbot comum*.

Portanto a pergunta de selecao nao e "qual ideia e mais legal", mas:

- Qual das cinco dores em `IDEAS.md` o time encosta em trabalho real de cliente?
- A demo consegue terminar em um numero em vez de um dashboard? (O vencedor final e escolhido por **votacao do publico**, nao pelo juri tecnico.)
- Da para rodar com dados publicos ou sinteticos sem o prejuizo de credibilidade de ter tudo mockado?

Recomendacao vigente: **Covenant Watch** (monitoramento de covenants em credito privado). Vice: **normalizador de eventos corporativos**. Nenhuma das duas aceita ainda - o usuario segue explorando o espaco de problemas.

## Fases de construcao (apos fechar a direcao)

**Fase 1 - Proposta (ate 28/08)**
Enunciado do problema, usuario alvo, impacto esperado com um numero de ordem de grandeza, formato da solucao em um paragrafo. Nada construido ainda. E isto que o comite de selecao le entre 07/08 e 01/09.

**Fase 2 - Base de dados (13/08 a 31/08)**
Montar o acervo publico (ver regras de dados em `RULES.md` e a lista de fontes em `checkpoint.json`). Tudo precisa ser publico, sintetico, mockado ou anonimizado com autorizacao previa. Sem dados de cliente, sem bases de producao, sem codigo fonte da GFT ou de clientes, sem dados pessoais - violacao e desclassificacao imediata.

**Fase 3 - Construcao do agente (01/09 a 20/09)**
Implementar em Gemini Enterprise / GCP. Decomposicao multi-agente ganha de um prompt unico tanto em Inovacao quanto em Viabilidade Tecnica. Manter cada afirmacao do agente ligada por citacao ao documento de origem - e isso que transforma a demo de impressionante em confiavel para um juri de setor regulado.

**Fase 4 - Entregaveis (20/09 a 30/09)**
Quatro artefatos obrigatorios:
- One-pager em PDF: problema, solucao, impacto esperado
- Video com pitch e demo
- Demo funcional: prototipo navegavel ou simulado
- Diagrama de arquitetura em PDF

Reservar tempo real aqui. Times perdem pontos no video e no one-pager, nao no modelo.

**Fase 5 - Final (16/10 a 28/10)**
Se selecionado entre os tres finalistas, refazer o pitch para uma plateia *nao tecnica* - a sala e que vota. Abrir pela dor e pelo numero, mostrar o agente funcionando ao vivo, fechar em escala.

## Questoes abertas

1. Em qual dominio do Mercado de Capitais o time atua no dia a dia? (Isto desbloqueia a escolha do problema.)
2. Quem esta no time e quem sera o Agent Lead?
3. O Guia Tecnico ja foi recebido?
4. Todos os integrantes pretendidos estao elegiveis hoje e seguirao elegiveis ate a entrega do premio?
5. Alguem participou do kickoff de 12/08 as 14h, ou existe gravacao?

## Pontos que vale nao esquecer

- O premio e por projeto, dividido igualmente; rateio desigual e proibido independentemente da contribuicao individual.
- Toda a propriedade intelectual e da GFT - cessao gratuita, total e irrevogavel. A autoria recebe apenas reconhecimento institucional.
- Tudo sobre o desafio e confidencial, explicitamente incluindo os criterios de avaliacao e os resultados preliminares. Manter estes arquivos internos.
- O regulamento chama cada integrante de **Builder** e o representante de **Agent Lead** - usar esse vocabulario no pitch soa como fluencia nas regras.
