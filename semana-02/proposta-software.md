# Proposta de Intervenção Técnica e Ética
**Atividade: O Dilema da IA Contratadora**  
**Componente:** Engenharia de Software  
**Data:** 03/03/2026
**Time** Bianca Schiavo e Emily Amorim

---

## 1. Identificação do Problema

O algoritmo de triagem desenvolvido pela startup replica e amplifica **vieses históricos** presentes nos dados de treinamento, discriminando candidatos de grupos minoritários ou sub-representados. Isso configura um risco simultâneo em três dimensões:

- **Ético:** a ferramenta causa dano real a pessoas reais
- **Jurídico:** viola o Art. 20 da LGPD, que garante ao cidadão o direito de revisão de decisões automatizadas
- **Financeiro:** multas e processos judiciais podem superar amplamente o custo de correção

---

## 2. Análise das Opções Técnicas

| Solução | O que resolve | Limitação |
|---|---|---|
| **Human-in-the-loop** | Reduz descarte injusto imediato; cumpre parcialmente a LGPD | Não corrige o algoritmo; depende do recrutador humano ser imparcial |
| **XAI (Explicabilidade)** | Aumenta transparência; facilita auditorias externas | Expõe a lógica interna do produto; não elimina o viés, só o torna visível |
| **Auditoria de Dados** | Ataca a causa raiz do problema | Atraso de 4 semanas; custo adicional pontual |

---

## 3. Nossa Proposta: Combinação em Duas Fases

Em vez de escolher apenas uma solução, propomos uma **abordagem em fases** que equilibra os interesses do negócio com a responsabilidade ética.

### Fase 1 — Lançamento Imediato com Salvaguarda (Semana 1)

Lançar o produto **com Human-in-the-loop ativado por padrão:**

- A IA passa a **ranquear**, não a **decidir**
- Um recrutador humano é obrigado a revisar os **20% inferiores** da lista antes de qualquer descarte
- Isso reduz o risco jurídico imediato e já coloca o produto em conformidade parcial com o Art. 20 da LGPD

### Fase 2 — Correção Estrutural (Semanas 2 a 5)

Em paralelo ao lançamento, executar a **Auditoria de Dados:**

- Limpeza estatística dos dados de treinamento enviesados
- Retreinamento do modelo com dados mais representativos
- Atualização do produto em produção ao fim das 4 semanas

---

## 4. Fundamentação Ética (Código ACM/IEEE)

**Cláusula 1.03 — Aprovação pública:**  
O engenheiro de software deve aprovar software apenas se acreditar que é seguro, atende às especificações, passa nos testes e não diminui a qualidade de vida. Lançar o algoritmo sem correção, ciente do viés, viola diretamente esse princípio.

**Cláusula 3.01 — Produto de alta qualidade:**  
Os engenheiros devem buscar excelência e não comprometer a qualidade do produto por pressão de prazo ou custo. A solução em fases permite cumprir o prazo de negócio **sem abrir mão da qualidade ética do produto**.

---

## 5. Análise Financeira: Atraso vs. Processo Judicial

| Cenário | Custo Estimado |
|---|---|
| **Atraso de 4 semanas para auditoria** | Custo operacional da equipe + possível perda de receita inicial |
| **Multa por violação da LGPD** | Até **2% do faturamento**, limitado a R$ 50 milhões por infração (Art. 52 da LGPD) |
| **Processo judicial coletivo** | Indenizações individuais + honorários + dano reputacional incalculável |

> **Conclusão financeira:** o custo de 4 semanas de atraso é **ordens de grandeza menor** do que o risco jurídico de lançar um produto discriminatório.

---

## 6. Conclusão

A pressão por velocidade de lançamento é legítima, mas não justifica colocar em risco candidatos reais nem a própria empresa. Nossa proposta mostra que **engenharia responsável e viabilidade de negócio não são opostos** — com planejamento, é possível lançar, gerar receita e corrigir o problema de forma estruturada.

> *"A qualidade de um software não se mede apenas por sua performance técnica, mas pelo impacto que causa na vida das pessoas."*