# BootCamp-IA-Criando-agentes

---

# 🤖 Sistema de Agentes para Planejamento de Carreira em Tecnologia

## 📌 Visão Geral

Este projeto implementa uma arquitetura baseada em **agentes de IA especializados** para orientar usuários na escolha e planejamento de carreira em tecnologia.

A solução é composta por dois agentes principais:

- 🧠 **Agent 1 — Entrevistador de Carreira**
- 🗺️ **Agent 2 — Planejador de Carreira**

A abordagem segue o princípio de **decomposição de tarefas complexas em agentes especializados**, garantindo maior qualidade, personalização e escalabilidade.

---

## 🏗️ Arquitetura do Sistema


Usuário
↓
[Agent 1 - Entrevistador]
↓ (dados estruturados)
[Agent 2 - Planejador]
↓
Plano de Carreira Personalizado

---

## 🤖 Agent 1 — Entrevistador de Carreira

### 🎯 Objetivo

Coletar informações estruturadas do usuário por meio de uma entrevista guiada e gerar recomendações de carreira.

### ⚙️ Funcionamento

O agente conduz uma entrevista com **7 perguntas sequenciais**, seguindo regras rígidas:

- Apenas **1 pergunta por vez**
- Aguarda resposta antes de continuar
- Coleta dados essenciais:
  - Interesses
  - Experiência
  - Disponibilidade
  - Preferências
  - Objetivos
  - Interesses técnicos
  - Experiência prévia

### 🧠 Processo de Decisão

Após a coleta:

- Aplica uma **matriz de decisão multicritério**:
  - Afinidade com interesses
  - Demanda de mercado
  - Tempo até nível júnior
  - Aproveitamento de experiência prévia

- Gera um ranking com **3 carreiras recomendadas**

### 🔄 Saída Estruturada (Handoff)

Após escolha do usuário, o Agent 1 envia para o Agent 2:

```json
{
  "carreira": "...",
  "horas_semana": "...",
  "experiencia": "...",
  "objetivo": "...",
  "preferencia": "...",
  "interesses": "..."
}
````

---

## 🗺️ Agent 2 — Planejador de Carreira

### 🎯 Objetivo

Transformar dados do usuário em um **plano de desenvolvimento completo e acionável**.

### 📦 Saída Gerada

O agente produz um plano estruturado contendo:

* 🧩 Visão do dia a dia da carreira
* 🧠 Mapa de skills (core + complementares)
* 📅 Roadmap de 90 dias
* 🚀 Projeto de portfólio
* 💬 Roteiro de entrevistas
* 🎓 Trilha recomendada (DIO)

### ⚙️ Personalização

O plano é ajustado dinamicamente com base em:

#### ⏱️ Tempo disponível

* < 5h → foco essencial
* 5–10h → padrão
* > 15h → aprofundamento

#### 📊 Experiência

* Zero → foco em fundamentos
* Iniciante → teoria + prática
* Alguma → foco em gaps

#### 🎯 Objetivo

* Primeiro emprego → portfólio + entrevistas
* Transição → transferência de skills
* Crescimento → especialização

---

## 🔗 Comunicação entre Agentes (Handoff)

A comunicação entre agentes segue um modelo de **contrato de dados estruturado**, garantindo:

* Baixo acoplamento
* Alta previsibilidade
* Facilidade de integração (ex: APIs, pipelines, RAG)

---

## 🧠 Justificativa Técnica da Abordagem com Agentes

### 1. 🔍 Separação de Responsabilidades (SoC)

Cada agente possui uma função bem definida:

| Agente  | Responsabilidade           |
| ------- | -------------------------- |
| Agent 1 | Coleta e análise de perfil |
| Agent 2 | Planejamento e execução    |

➡️ Isso reduz complexidade e melhora a qualidade das respostas.

---

### 2. 🧩 Modularidade e Escalabilidade

A arquitetura permite:

* Adicionar novos agentes (ex: mentor, avaliador técnico)
* Substituir agentes sem impactar o sistema inteiro
* Escalar horizontalmente

---

### 3. 🎯 Especialização de Prompts

Cada agente possui:

* Contexto próprio
* Regras específicas
* Estrutura de saída definida

➡️ Isso evita:

* Respostas genéricas
* Mistura de responsabilidades
* Perda de foco

---

### 4. 🔄 Pipeline Cognitivo (Multi-step Reasoning)

O sistema implementa um fluxo em etapas:

1. Coleta de dados
2. Análise
3. Tomada de decisão
4. Planejamento

➡️ Similar a pipelines de:

* Machine Learning
* ETL (Extract → Transform → Load)

---

### 5. 📊 Estruturação de Dados

O uso de dados estruturados entre agentes permite:

* Integração com:

  * APIs
  * Bancos de dados
  * Sistemas educacionais
* Uso em RAG (Retrieval-Augmented Generation)
* Persistência e rastreabilidade

---

### 6. 🤖 Redução de Alucinação

Ao dividir tarefas:

* O Agent 1 foca em **perguntar corretamente**
* O Agent 2 foca em **planejar corretamente**

➡️ Menos inferências incorretas e mais precisão.

---

### 7. 🧪 Reprodutibilidade

Com prompts bem definidos:

* Resultados mais consistentes
* Facilidade de testes
* Possibilidade de versionamento de agentes

---

## 🚀 Possíveis Evoluções

* 🧠 Agent 3: Mentor contínuo (acompanhamento semanal)
* 📊 Agent 4: Avaliador técnico (testes e feedback)
* 🔗 Integração com RAG (conteúdos personalizados)
* 📈 Tracking de progresso do usuário

---

## 🛠️ Tecnologias Compatíveis

Essa arquitetura pode ser implementada com:

* Semantic Kernel
* LangChain
* OpenAI Assistants / GPTs
* Ollama (modelos locais)
* APIs REST
* Sistemas WPF / Web

---

## 📚 Conclusão

A abordagem baseada em agentes:

✔ Melhora a qualidade das respostas
✔ Permite personalização profunda
✔ Facilita manutenção e evolução
✔ Reduz erros e inconsistências

Trata-se de uma aplicação prática de **arquitetura cognitiva modular**, altamente alinhada com sistemas modernos de IA.

---

## ✨ Resultado Final

O usuário sai com:

* Clareza de carreira
* Plano estruturado
* Direcionamento prático
* Preparação para o mercado

---
