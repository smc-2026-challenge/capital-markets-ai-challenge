# Espaco de problemas e catalogo de solucoes

Data do checkpoint: **12/08/2026**. Situacao: **nada aceito ainda** - o usuario segue explorando.
Ver `RULES.md` para as restricoes que estas ideias precisam respeitar.

> Este arquivo esta em pt-BR sem acentuacao (ASCII puro).

## Os tres filtros pelos quais toda ideia precisa passar

**1. Dados.** Apenas publicos, sinteticos, mockados ou anonimizados com autorizacao previa. Isso limita menos do que parece no Brasil, porque o mercado regulado publica acervos enormes: dados abertos da CVM (regulamentos de fundos, ITR/DFP, fatos relevantes, escrituras de debentures), manuais e avisos de eventos corporativos da B3, APIs do Bacen (SGS/PTAX), documentos publicos da ANBIMA, listas publicas de sancoes e a lista de punidos da CVM. Uma ideia ancorada em documentos genuinamente publicos evita o prejuizo de credibilidade que "esta tudo mockado" impoe a uma demo.

**2. Plataforma.** O agente precisa rodar em Gemini Enterprise + GCP, ou o time e desclassificado. Essa plataforma e forte em RAG sobre acervos de documentos, orquestracao multi-agente, conectores e extracao estruturada a partir de documentos nao estruturados. E fraca em computacao quantitativa customizada, streaming de dados de mercado em tempo real e caminhos de latencia baixa. Logo: escolher problemas intensivos em documentos e em operacoes, nao problemas de trading sensiveis a latencia.

**3. Plateia.** Duas audiencias diferentes pontuam. O juri tecnico aplica os criterios com peso (Inovacao 25%, Valor de Negocio 25%, Viabilidade 20%, UX 15%, Escalabilidade 15%). Depois, em 28/10, a **sala vota** o 1o, 2o e 3o lugares. Uma demo que termina em um numero duro ganha de uma demo que termina em um dashboard.

## Dores de negocio, ranqueadas por quao reais sao

### P1 - Monitoramento de covenants em credito privado
O volume de debentures, CRI/CRA e fundos de credito no Brasil cresceu rapido; o monitoramento de covenants continuou manual. Uma escritura tem de 80 a 150 paginas, com covenants espalhados por clausulas, testados trimestralmente contra as demonstracoes do emissor. Os times de credito conferem os maiores nomes e ficam as cegas na cauda da carteira.

Onde vaza dinheiro: deteccao tardia de quebra eleva a perda dada a inadimplencia, porque cada semana de atraso em iniciar a conversa de waiver custa posicao de negociacao. Mais 2 a 4 dias de analista por emissor por trimestre.

Dados: totalmente publicos - escrituras, ITR/DFP, indices do Bacen.

### P2 - Processamento de eventos corporativos na custodia
Avisos nao estruturados (AGO/AGE, fato relevante, grupamento, incorporacao) ainda sao digitados a mao como eventos estruturados. No mundo inteiro isso segue como uma das principais fontes de claims de perda operacional em custodia.

Onde vaza dinheiro: claims pagos por eventos perdidos ou lancados errado, mais horas extras no dia do evento.

Dados: avisos publicos, posicoes sinteticas.

### P3 - Falhas de liquidacao em ciclos comprimidos
A liquidacao global comprimiu para T+1 (EUA e Canada em 2024, Reino Unido e UE previstos para 2027) enquanto acoes na B3 seguem em D+2. Corretoras brasileiras com fluxo de BDR e offshore passaram a ter de afirmar alocacoes no mesmo dia.

Onde vaza dinheiro: custo de falha, funding e pre-funding, risco de buy-in, regimes de penalidade.

Dados: majoritariamente sinteticos - a menor credibilidade de demo entre as cinco.

### P4 - Vazao de mudancas regulatorias
CVM, Bacen e B3 publicam continuamente; bancos mantem times inteiros para ler, classificar impacto e cascatear para backlogs de sistemas.

Onde vaza dinheiro: semanas entre a publicacao e a avaliacao de impacto.

Contraponto honesto: e a ideia mais saturada de qualquer hackathon, o que ataca direto o peso de 25% de Inovacao.

### P5 - Falsos positivos em PLD e vigilancia de mercado
Taxas de falso positivo passam de 90% com frequencia, e analistas reescrevem narrativas de caso quase identicas.

Onde vaza dinheiro: custo puro de headcount.

Contraponto honesto: o juri fica desconfortavel com um agente que aparenta *decidir* sobre crime financeiro. Somente viavel se enquadrado estritamente como assistente com humano no circuito.

## Catalogo de solucoes

**A. Regulatorio / intensivo em documentos** - ponto forte da plataforma, dados publicos

- **A1 - Radar Normativo** (P4): monitora publicacoes de CVM/Bacen/B3, classifica impacto por dominio de negocio e emite avaliacao de impacto mais backlog de acoes e casos de teste.
- **A2 - Auditor de Regulamento CVM 175** (P4): audita regulamentos publicos de fundos contra um checklist de clausulas da CVM 175, aponta lacunas com citacao de artigo e propoe redacao corretiva. *Ressalva: validar se a onda de adaptacao a 175 ainda esta viva em 2026 antes de pitchar como urgente.*
- **A3 - Covenant Watch** (P1): extrai covenants de escrituras publicas, monta calendario de verificacao, testa contra ITR/DFP publicos, projeta distancia da quebra e redige o memorando do analista e a carta de waiver.

**B. Pos-negociacao** - a melhor historia de corte de custo, dados sinteticos

- **B4 - Normalizador de eventos corporativos** (P2): avisos publicos de AGO/AGE e fatos relevantes convertidos em eventos no formato ISO 20022 / MT564, com ambiguidade encaminhada a um humano.
- **B5 - Triagem de breaks e falhas** (P3): trades sinteticos contra posicoes de custodia, classificacao de causa raiz, redacao da mensagem a contraparte e proposta de correcao.

**C. Front-office / cliente final** - as melhores demos para a votacao do publico

- **C6 - Analista de suitability e KYC** (P5): suitability conforme CVM 30 mais screening em listas publicas de sancoes e na lista de punidos da CVM.
- **C7 - Respondedor de DDQ/RFP**: responde questionarios de due diligence de gestoras, com cada resposta lastreada em citacao.
- **C8 - Triagem de vigilancia** (P5): fluxo de ordens sintetico, sinalizacao de layering e spoofing, narrativa do caso para um analista humano.

**D. Margem de delivery da propria GFT**

- **D9 - Agente de manual de regras para suite de testes**: le mudancas em manuais e regras operacionais da B3 e gera cenarios de teste executaveis para a plataforma de um cliente. Atinge o P&L que o proprio juri administra. Risco: pode ser lido como ferramenta interna e nao solucao de mercado - embora os criterios digam explicitamente "valor para cliente **ou** negocio".

## Recomendacao vigente (nao aceita)

**A3 Covenant Watch**, com **B4 Normalizador de eventos corporativos** como vice.

Por que A3 casa com a pontuacao:
- *Aderencia + valor de negocio (50% somados)*: os clientes de Capital Markets da GFT sao administradores, gestoras e custodiantes que operam exatamente esse fluxo.
- *Viabilidade tecnica (20%)*: RAG documental mais extracao estruturada mais reverificacao agendada e territorio nativo do Gemini Enterprise, construivel nas sete semanas disponiveis.
- *Escalabilidade (15%)*: o mesmo motor le qualquer contrato com formato de escritura e depois se estende a instrumentos offshore.
- *Votacao do publico*: a demo pode terminar em um numero - carregar uma escritura publica real, extrair 14 covenants, testar contra o ultimo ITR, um falha, mostrar o artigo, a aritmetica, o indice calculado e a carta de solicitacao de waiver ja redigida.

**Diferencial de inovacao que impede parecer RAG comum:** projecao de distancia da quebra - projetar cada indice a frente pela propria tendencia do emissor e ranquear a carteira por meses ate a quebra. Isso converte um leitor de documentos em um sistema de alerta antecipado, que e justamente a parte que ninguem faz a mao.

**Decomposicao em agentes** (quatro papeis, orquestracao real em vez de um prompt unico):

1. **Extrator** - PDF da escritura convertido em objetos de covenant: tipo, formula, limite, frequencia de teste, prazo de cura, referencia do artigo.
2. **Calculadora** - busca a metrica no ITR/DFP publico e calcula o indice (divida liquida/EBITDA, DSCR, ICR), mostrando a aritmetica.
3. **Vigia** - execucao agendada por data de teste; classifica cumprido / proximo da quebra / quebrado, com um numero de distancia da quebra.
4. **Narrador** - escreve o memorando do analista e a carta a contraparte, com cada afirmacao ligada por citacao a um artigo e a uma linha da demonstracao financeira.

## O que desbloqueia a decisao

A pergunta unica que muda a resposta: **qual das dores P1 a P5 o time encosta em trabalho real de cliente?** Aderencia e valor de negocio somam metade da nota, e um pitch sobre um fluxo que o time nunca viu soa generico, nao importa quao bom seja o agente.

- Time de renda fixa / credito: A3
- Pos-negociacao / custodia / back-office: B4 ou B5
- Compliance / risco / regulatorio: A1, A2, C6 ou C8
- Front-office / corretora / plataformas de gestao: C6 ou C7
- Modernizacao de plataforma / delivery: D9
