# Documento de Levantamento de Requisitos

**Projeto:** Sistema de Gestao de Hospedagem
**Cliente:** Pousada Bela Vista
**Responsavel pelo levantamento:** Analista de Sistemas Emily Amorim
**Data da entrevista inicial:** 02 de abril de 2026
**Versao:** 1.0

---

## Sumario

1. [Contexto e Objetivo](#1-contexto-e-objetivo)
2. [Registro da Entrevista Inicial](#2-registro-da-entrevista-inicial)
3. [Problemas Identificados](#3-problemas-identificados)
4. [Historias de Usuario](#4-historias-de-usuario)
5. [Requisitos de Software](#5-requisitos-de-software)
   - 5.1 [Requisitos Funcionais](#51-requisitos-funcionais)
   - 5.2 [Requisitos Nao Funcionais](#52-requisitos-nao-funcionais)

---

## 1. Contexto e Objetivo

Este documento registra os resultados do levantamento de requisitos realizado junto ao proprietario da Pousada Bela Vista, estabelecimento com 25 anos de operacao que identificou a necessidade de informatizar seus processos de hospedagem. O objetivo e formalizar as necessidades do cliente e traduzi-las em requisitos tecnicos que orientem o desenvolvimento do sistema.

---

## 2. Registro da Entrevista Inicial

**Data:** 02 de abril de 2026
**Participantes:**
- Analista de Sistemas (condutora da entrevista)
- Sr. Manoel (proprietario da Pousada Bela Vista)

**Sintese da entrevista:**

O proprietario relatou que o aumento do movimento nos ultimos anos tornou insuficiente o controle manual até então adotado — caderno de anotacoes na recepcao e planilha de Excel operada pela secretaria de forma independente. Essa ausencia de integracao entre os controles tem gerado incidentes de overbooking, nos quais hospedes chegam ao estabelecimento sem encontrar acomodacao disponivel.

Foram identificados ainda problemas no registro de consumos extras, como itens de frigobar e lançamentos de lanchonete, frequentemente esquecidos durante o atendimento em dias de maior movimento, resultando em perda financeira direta. O controle do status de limpeza dos quartos e realizado verbalmente entre a recepcao e as camareiras, sem qualquer registro formal ou verificação antes da alocação de hóspedes.

O perfil de uso declarado pelo proprietario é de usuarios com pouca experiencia em sistemas informatizados, o que torna a simplicidade da interface um requisito central do projeto.

---

## 3. Problemas Identificados

| # | Problema | Impacto |
|---|----------|---------|
| P01 | Controle de reservas fragmentado entre caderno e planilha sem sincronizacao | Overbooking e conflito de reservas |
| P02 | Ausencia de verificacao do status de limpeza antes do check-in | Hospedes alocados em quartos nao preparados |
| P03 | Registro de consumos extras realizado em anotacoes fisicas sujeitas a perda | Prejuizo financeiro por lancamentos nao cobrados |
| P04 | Calculo manual de diarias e consumos no fechamento da conta | Erros de soma e lentidao no atendimento |
| P05 | Cadastro repetitivo de dados de hospedes a cada visita | Retrabalho e risco de inconsistencia de informacoes |

---

## 4. Historias de Usuario

As historias de usuario a seguir foram elaboradas a partir das necessidades levantadas na entrevista, seguindo o formato padrao: **Como** [ator], **quero** [funcionalidade], **para que** [objetivo de negocio].

| ID | Ator | Desejo | Finalidade |
|----|------|--------|------------|
| US01 | Proprietario | Visualizar um mapa de ocupacao com grade de quartos e datas | Identificar disponibilidade rapidamente e evitar reservas duplicadas (overbooking) |
| US02 | Recepcionista | Receber alerta ao tentar alocar um hospede em quarto com status "Sujo" | Garantir que nenhum cliente seja acomodado em quarto sem preparo previo |
| US03 | Proprietario | Consultar hospedes pelo CPF ou numero de telefone | Agilizar o processo de entrada e evitar o preenchimento repetitivo de dados cadastrais |
| US04 | Recepcionista | Lancar consumos extras de frigobar e lanchonete diretamente na ficha do quarto | Evitar prejuizos financeiros por esquecimento no momento do fechamento da conta |
| US05 | Proprietario | Ter o calculo automatico da conta com base na categoria do quarto e nos consumos registrados | Eliminar erros de soma manual e agilizar o atendimento no check-out |

---

## 5. Requisitos de Software

### 5.1 Requisitos Funcionais

Os requisitos funcionais descrevem as capacidades e comportamentos que o sistema deve apresentar para atender as necessidades do negocio.

| ID | Descricao |
|----|-----------|
| RF01 | O sistema deve permitir o cadastro de categorias de quartos com precos distintos por categoria. |
| RF02 | O sistema deve exibir uma interface grafica de calendario (Mapa de Ocupacao) representando a disponibilidade dos quartos por periodo. |
| RF03 | O sistema deve permitir o cadastro e a busca de hóspedes por CPF. |
| RF04 | O sistema deve permitir a alteracao do status de limpeza de cada quarto, com os estados "Limpo" e "Sujo". |
| RF05 | O sistema deve impedir a vinculacao de hospedes a quartos cujo status seja "Sujo", emitindo alerta ao operador. |
| RF06 | O sistema deve totalizar automaticamente o valor das diarias e dos consumos extras no momento do fechamento da conta. |

### 5.2 Requisitos Nao Funcionais

Os requisitos nao funcionais definem os atributos de qualidade que o sistema deve satisfazer, independentemente das funcionalidades especificas.

| ID | Categoria | Descricao |
|----|-----------|-----------|
| RNF01 | Segurança | Os dados devem ser armazenados e sincronizados em ambiente de nuvem, garantindo a recuperacao das informacoes em caso de falha ou perda do equipamento fisico da recepcao. |
| RNF02 | Usabilidade | A interface deve ser simples e intuitiva, projetada para usuarios com baixa experiencia tecnologica, minimizando a curva de aprendizado. |
| RNF03 | Confiabilidade | O sistema deve garantir a integridade dos dados de reserva, impedindo a sobreposicao de periodos para o mesmo quarto (restricao de conflito de datas). |

---

*Documento elaborado em 02 de abril de 2026. Sujeito a revisao após validação com o cliente.*