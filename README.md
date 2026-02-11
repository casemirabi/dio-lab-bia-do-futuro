# 🤖 Luna — Agente de Acompanhamento Estruturado com IA Generativa

## 📌 Contexto

Empreendedores digitais não travam por falta de informação — travam por falta de estrutura.

Recebem mensagens, respondem quando dá, improvisam, tentam organizar tudo ao mesmo tempo… e acabam sem clareza nem consistência.

A Luna foi criada para resolver isso.

Ela é um agente de acompanhamento estruturado em 4 semanas, focado em:

- Organizar comunicação
- Tomar decisões progressivas
- Executar micro-ações práticas
- Desenvolver autonomia operacional

Tudo isso rodando localmente com IA generativa leve via Ollama.

## 🎯 O Que a Luna Faz

A Luna ajuda o empreendedor a:

- Resolver uma coisa por vez
- Criar mensagens básicas de atendimento
- Organizar rotina de resposta
- Evoluir semana a semana
- Evitar pular etapas

Ela não:

- Cria funis complexos na Semana 1
- Propõe automação precoce
- Reinicia decisões já tomadas
- Promete resultados financeiros

## 🧠 Como Funciona

### 📆 Método das 4 Semanas

#### 🟢 Semana 1 — Base

- Mensagem de primeiro contato
- Mensagem de objeção (ex: preço)
- Mensagem de fechamento
- Rotina mínima de resposta

⚠️ Nada de funil ou script completo nessa fase.

#### 🟡 Semana 2 — Organização Leve

- Fluxo simples de atendimento
- Checklist curto
- Organização por blocos

#### 🟠 Semana 3 — Otimização

- 2–3 métricas simples
- Testes leves
- Ajustes práticos

#### 🔵 Semana 4 — Autonomia

- Documentação em 1 página
- Rotina semanal fixa
- Backlog de melhorias

## 🏗 Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Usuário] --> B[UI Streamlit]
    B --> C[FastAPI - app.py]
    C --> D[Arquivos Base]
    D --> E[Ollama - qwen2.5:3b]
    E --> C
    C --> F[Registro no CSV]
    F --> B
    B --> A

# 🌙 Luna — Agente Operacional 4 Semanas

---

## 🧩 Componentes

| Componente            | Tecnologia            |
|-----------------------|-----------------------|
| UI                    | Streamlit             |
| API                   | FastAPI               |
| LLM                   | qwen2.5:3b via Ollama |
| Persistência          | CSV                   |
| Controle comportamental | System Prompt      |

---

## 📂 Estrutura do Projeto

luna-agente-4semanas/
│
├── README.md
├── 01_perfil_agente.md
├── 02_perfil_empreendedor.yaml
├── 03_historico_conversas.csv
│
├── app.py
├── ui.py
│
├── docs/
│ ├── DOCUMENTACAO_AGENTE.md
│ ├── BASE_DE_CONHECIMENTO.md
│ ├── SYSTEM_PROMPT.md
│ ├── AVALIACAO_E_METRICAS.md
│ └── PITCH.md
│
└── requirements.txt

------------------------------------------------------------------------

## 🚀 Como Rodar o Projeto

### 1️⃣ Instalar dependências

``` bash
pip install fastapi uvicorn streamlit requests pydantic
```

### 2️⃣ Instalar e rodar Ollama

``` bash
ollama pull qwen2.5:3b
ollama serve
```

### 3️⃣ Rodar a API

``` bash
uvicorn app:app --reload --port 8000
```

### 4️⃣ Rodar a Interface

``` bash
streamlit run ui.py
```

Abrir no navegador:

    http://localhost:8501

------------------------------------------------------------------------

## 🛡 Segurança e Anti-Alucinação 

A Luna:

-   Só utiliza dados locais\
-   Não acessa APIs externas\
-   Não executa ações reais\
-   Não envia mensagens automaticamente\
-   Não compartilha dados de terceiros\
-   Não promete resultados

Controle feito via:

-   Prompt estruturado\
-   Controle de escopo\
-   Continuidade via histórico CSV

------------------------------------------------------------------------

## 📊 Avaliação

O agente é avaliado por:

-   Continuidade (não repetir decisões)\
-   Controle de escopo\
-   Micro-execução (10--30 min)\
-   Linguagem natural\
-   Limite de perguntas\
-   Segurança

**Maturidade atual:**\
Beta Avançado (\~90--95%)

------------------------------------------------------------------------

## 🔍 Diferencial

A maioria dos agentes:

-   Explica demais\
-   Sugere demais\
-   Complica demais

A Luna:

-   Reduz\
-   Organiza\
-   Estrutura\
-   Executa\
-   Evolui

Ela não ensina marketing.\
Ela cria base operacional.

------------------------------------------------------------------------

## 🎤 Pitch

A Luna organiza o básico.\
E o básico bem feito escala sozinho.
