<!--
Transcricao fiel de resposta da Organizacao, repassada no Teams.
Preserva a acentuacao do original (os demais arquivos autorais do repositorio sao ASCII puro).
CONTEUDO INTERNO DA GFT - nao publicar, nao subir em plataforma nao homologada.
-->

# Guia Tecnico - resposta da Organizacao

**Nao existe um Guia Tecnico separado.**

O regulamento (sec. 12) diz que "requisitos tecnicos, arquiteturais, de integracao, seguranca, execucao e apresentacao estao no Guia Tecnico oficial, que e parte integrante das regras". Isso levou o time a procurar um documento que **nao existe como artefato proprio**.

- **Data da resposta:** 12/08/2026, 17h23
- **Origem:** Evelim Buratti (Organizacao), repassada no Teams por Michelle Carla da Silva
- **Natureza:** repasse, nao mensagem direta da Organizacao. Em duvida formal, reconfirmar pelo canal do Agent Lead.

## Texto, como repassado

> Evelim, respondeu:
> o guia tecnico é o que temos dentro do sharepoint e o que está já no regulamento Michelle, nada a mais que isso
>
> que as pessoas cuidem da questão de privacidade de dados, segurança e afins.

## O que isso significa na pratica

**1. A especificacao tecnica completa e o que o time ja tem.** Nada mais vai chegar. Os requisitos aplicaveis sao:

- **Regulamento, sec. 12** - o agente final deve estar implementado, configurado, integrado, executavel e disponivel para avaliacao nos padroes **Gemini Enterprise + GCP**. Descumprir desclassifica.
- **Regulamento, sec. 13** - regras de dados (mock, publico, sintetico, anonimizado com autorizacao previa).
- **Regulamento, sec. 14** - seguranca da informacao. Inclui a vedacao de subir documentos internos em plataformas nao homologadas, e a regra de que **todo material permanece nos ambientes indicados pela Organizacao**.
- **Pagina do SharePoint** - os quatro entregaveis obrigatorios, cronograma, criterios e juri. Ver `Brazil_NewsForYou.md`.

**2. Nao ha template nem checklist para o diagrama de arquitetura.** A pagina do SharePoint pede "diagrama simplificado da arquitetura tecnica" e nada alem. O time define o que isso quer dizer - liberdade, mas tambem ausencia de rubrica a satisfazer.

**3. A arquitetura escolhida deixou de estar em risco de invalidacao.** A ressalva que acompanhava a arquitetura sugerida em `oneask/AVALIACAO.md` - "o Guia Tecnico pode invalidar estas escolhas" - **cai**. Nao ha documento por vir.

**4. Privacidade e seguranca de dados sao expectativa nomeada da Organizacao.** A frase final da resposta e a unica exigencia que a Organizacao acrescentou de proprio punho. Isso eleva as regras de dados de "clausula no PDF" a **pedido explicito de quem organiza** - e portanto:

- mock ostensivamente sintetico, sem nome de cliente real (atencao ao campo `customer_name` do exemplo da V2.3)
- nada de base de producao, dado pessoal ou informacao sob sigilo contratual
- credenciais em Secret Manager, nunca em codigo ou em documento

## Consequencia de calendario

Esta resposta e de **12/08** - o mesmo dia do primeiro checkpoint deste repositorio, que nunca a registrou. O projeto carregou "Guia Tecnico nao obtido" como principal risco tecnico por quase um mes, quando a questao ja estava respondida. Vale como lembrete de que resposta obtida em canal de chat precisa aterrar no repositorio no mesmo dia.
