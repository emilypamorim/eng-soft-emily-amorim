# Documento de Requisitos de Software (SRS)

## Informações do Projeto

| Campo | Descrição |
|---|---|
| **Nome do Projeto** | Sistema de Gestão de Hospedagem |
| **Dono do Projeto** | Pousada Bela Vista |
| **Versão** | 1.0 |
| **Data** | 02/04/2026 |

---

## 1. Introdução

O objetivo deste documento é descrever os requisitos para o desenvolvimento do Sistema de Gestão de Hospedagem da Pousada Bela Vista. Este documento servirá como guia para a equipe de desenvolvimento, garantindo que todas as características e funcionalidades necessárias sejam implementadas conforme as expectativas dos stakeholders.

A Pousada Bela Vista opera há 25 anos e identificou a necessidade de informatizar seus processos de hospedagem, substituindo o controle manual por caderno e planilha Excel por um sistema integrado que elimine falhas operacionais e perdas financeiras.

---

## 2. Escopo

O escopo do Sistema de Gestão de Hospedagem inclui, mas não se limita às seguintes funcionalidades:

- **Gestão de Reservas:** Controle centralizado de reservas com mapa de ocupação por quarto e período, eliminando conflitos e overbooking.
- **Gestão de Quartos:** Controle de status de limpeza e ocupação dos quartos com alertas automáticos no check-in.
- **Gestão Financeira:** Registro de consumos extras e fechamento automático de contas com cálculo de diárias e consumos.

---

## 3. Requisitos Funcionais

### 3.1 Gestão de Reservas

| ID | Descrição do Requisito |
|---|---|
| RF 1.1 | O sistema deve permitir o cadastro de categorias de quartos com preços distintos por categoria. |
| RF 1.2 | O sistema deve exibir uma interface gráfica de calendário (Mapa de Ocupação) representando a disponibilidade dos quartos por período. |
| RF 1.3 | O sistema deve impedir a criação de reservas com conflito de datas para o mesmo quarto. |

### 3.2 Gestão de Hóspedes

| ID | Descrição do Requisito |
|---|---|
| RF 2.1 | O sistema deve permitir o cadastro e a busca de hóspedes por CPF, evitando o preenchimento repetitivo de dados a cada visita. |
| RF 2.2 | O sistema deve manter o histórico de estadias associado ao cadastro do hóspede. |

### 3.3 Gestão de Quartos

| ID | Descrição do Requisito |
|---|---|
| RF 3.1 | O sistema deve permitir a alteração do status de limpeza de cada quarto, com os estados "Limpo" e "Sujo". |
| RF 3.2 | O sistema deve impedir a vinculação de hóspedes a quartos cujo status seja "Sujo", emitindo alerta ao operador. |

### 3.4 Gestão Financeira

| ID | Descrição do Requisito |
|---|---|
| RF 4.1 | O sistema deve permitir o lançamento de consumos extras de frigobar e lanchonete diretamente na ficha do quarto. |
| RF 4.2 | O sistema deve totalizar automaticamente o valor das diárias e dos consumos extras no momento do fechamento da conta. |

---

## 4. Requisitos Não Funcionais

- **RNF 4.1:** A interface deve ser simples e intuitiva, projetada para usuários com baixa experiência tecnológica, minimizando a curva de aprendizado.
- **RNF 4.2:** Os dados devem ser armazenados e sincronizados em ambiente de nuvem, garantindo a recuperação das informações em caso de falha ou perda do equipamento físico da recepção.
- **RNF 4.3:** O sistema deve garantir a integridade dos dados de reserva, impedindo a sobreposição de períodos para o mesmo quarto (restrição de conflito de datas).

---

## 5. Design da Interface do Usuário (UI)

- **Design 1:** A interface deve priorizar clareza visual e simplicidade. O Mapa de Ocupação deve ser o elemento central da tela principal, exibindo quartos em linhas e datas em colunas, com codificação por cores para os status disponível, reservado e ocupado.
- **Design 2:** O fluxo de navegação deve minimizar o número de cliques para as operações mais frequentes (check-in, check-out e lançamento de consumos). Formulários devem ser curtos e com campos de preenchimento automático a partir do CPF do hóspede.

---

## 6. Arquitetura do Sistema

- **Arquitetura 1:** Arquitetura em camadas (apresentação, negócio e dados), com acesso via navegador web para garantir compatibilidade com os equipamentos já existentes na recepção.
- **Arquitetura 2:** Banco de dados relacional hospedado em nuvem para garantir disponibilidade e backup automático. A camada de apresentação deve ser responsiva para suportar uso em tablets e computadores desktop.

---

## 7. Requisitos de Dados

- **RD 7.1:** As entidades principais são: Hóspede, Quarto, CategoriaQuarto, Reserva, ItemConsumo e Conta. Um hóspede pode ter múltiplas reservas. Cada reserva está associada a um quarto e gera uma conta. Uma conta pode conter múltiplos itens de consumo.
- **RD 7.2:** Os dados de reserva devem ter restrição de unicidade por quarto e período. O sistema deve realizar backup automático diário em nuvem e manter histórico de todas as transações financeiras.

---

## 8. Requisitos de Segurança

- **RS 8.1:** O sistema deve exigir autenticação por login e senha para acesso. Devem existir ao menos dois perfis de acesso: recepcionista (operações do dia a dia) e proprietário (acesso completo incluindo relatórios financeiros).
- **RS 8.2:** O tráfego de dados deve ser protegido via HTTPS. Dados sensíveis de hóspedes, como CPF, devem ser armazenados com criptografia.

---

## 9. Requisitos de Desempenho

- **RP 9.1:** O sistema deve suportar o uso simultâneo de pelo menos 5 usuários sem degradação de desempenho, atendendo ao porte atual da pousada.
- **RP 9.2:** As operações de busca de hóspede por CPF e carregamento do Mapa de Ocupação devem responder em menos de 2 segundos em condições normais de uso.

---

## 10. Requisitos de Teste

- **RT 10.1:** Devem ser realizados testes unitários nas regras de negócio críticas: bloqueio de quarto sujo, impedimento de overbooking e cálculo automático de conta. A cobertura mínima esperada é de 80% do código de negócio.
- **RT 10.2:** Os testes de aceitação devem ser conduzidos com o proprietário e ao menos um recepcionista da pousada, validando os cinco fluxos principais: cadastro de hóspede, realização de reserva, check-in, lançamento de consumo e check-out com fechamento de conta.

---

## 11. Cronograma do Projeto

| Tarefa | Data de Início | Data de Término |
|---|---|---|
| Levantamento de Requisitos | 02/04/2026 | 09/04/2026 |
| Design e Prototipagem | 10/04/2026 | 24/04/2026 |
| Desenvolvimento | 25/04/2026 | 30/06/2026 |
| Testes | 01/07/2026 | 18/07/2026 |
| Implantação | 21/07/2026 | 25/07/2026 |

---

## Revisões

| Versão | Data | Descrição |
|---|---|---|
| 1.0 | 02/04/2026 | Versão inicial — baseada na entrevista com o proprietário |
| 1.1 | [Data] | Atualização dos requisitos funcionais baseada no feedback inicial |

---

## Assinaturas

**Dono do Projeto:** ___________________________________________________

**Gerente de Projeto:** __________________________________________________