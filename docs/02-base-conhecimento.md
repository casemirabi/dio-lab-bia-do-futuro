# 📚 Base de Conhecimento

**Versão Atual — Agente 4 Semanas (Ollama / qwen2.5:3b)**

---

## 1️⃣ Dados Utilizados

| Arquivo                         | Formato   | Utilização no Agente |
|----------------------------------|-----------|----------------------|
| 01_perfil_agente.md             | Markdown  | Define personalidade, método, regras de escopo e estrutura obrigatória de resposta |
| 02_perfil_empreendedor.yaml     | YAML      | Armazena contexto do negócio, objetivos, gargalos e estado atual da jornada |
| 03_historico_conversas.csv      | CSV       | Mantém continuidade, decisões tomadas e evolução ao longo das semanas |

---

## 2️⃣ Função de Cada Arquivo

### 🧠 01_perfil_agente.md

Responsável por definir:

- Método das 4 semanas  
- Controle de escopo  
- Regras de continuidade  
- Estrutura fixa da resposta  
- Limitação de perguntas  
- Tom de voz permitido e proibido  

Esse arquivo garante que o modelo:

- Não pule etapas  
- Não proponha soluções complexas cedo demais  
- Não reinicie decisões já tomadas  
- Não utilize linguagem institucional  

---

### 📊 02_perfil_empreendedor.yaml

Responsável por armazenar:

- Nome e contexto do negócio  
- Canal principal  
- Volume de leads  
- Objetivos das 4 semanas  
- Gargalo atual  
- Semana ativa  
- Progresso estimado  
- Métricas mínimas  

Esse arquivo permite:

- Personalização real  
- Decisões baseadas no contexto atual  
- Controle do estágio da jornada  

---

### 🗂 03_historico_conversas.csv

Responsável por registrar:

- Data e canal  
- Semana ativa  
- Tema da conversa  
- Resumo da interação  
- Decisão tomada  
- Próxima ação  
- Prazo  
- Status  
- Resultado  

Função principal:

- Evitar repetição de decisões  
- Garantir continuidade  
- Forçar avanço de estado (decidir → executar → testar → ajustar)  

---

## 3️⃣ Estratégia de Integração

### Como os dados são carregados?

A cada requisição no `app.py`:

- Os três arquivos são lidos  
- O histórico recente é limitado (ex.: últimas 50 linhas)  
- O conteúdo é injetado como contexto no LLM  
- O modelo não armazena memória própria  
- Toda continuidade depende dos arquivos locais  

---

### Como os dados são usados no prompt?

O agente recebe:

- System Prompt (regras fixas)  
- Perfil do agente  
- Perfil do empreendedor  
- Histórico recente  

⚠️ Os arquivos não são inseridos como texto irrelevante.
O conteúdo é enviado porque o modelo é leve e o volume é pequeno.

---

## 4️⃣ Lógica de Continuidade

A continuidade funciona da seguinte forma:

1. O histórico é consultado  
2. Se existir decisão anterior registrada:
   - O agente não repete  
   - Avança para execução  
3. Se não existir decisão:
   - O agente define uma nova  

Cada nova interação pode gerar:

- Decisão  
- Próxima ação  
- Prazo  

Isso garante evolução progressiva.

---

## 5️⃣ Exemplo de Contexto Montado (Atual)

### Perfil do Agente

- Método estruturado em 4 semanas  
- Controle de escopo ativo  
- Linguagem natural de WhatsApp  
- Proibido pular etapas  

### Perfil do Empreendedor

- Canal principal: WhatsApp  
- Leads/semana: 5  
- Gargalo atual: responder rápido  
- Semana atual: 1  
- Objetivo: organizar atendimento  

### Histórico recente

- Decisão tomada: padronizar primeiro contato  
- Próxima ação: escrever mensagem base  
- Status: pendente  

**Instrução ao modelo:**

- Avançar para execução, sem redefinir decisão  
- Entregar ação prática de até 30 minutos  
- Manter linguagem humana  

---

## 6️⃣ Princípios da Base de Conhecimento

A base foi desenhada para garantir:

- 🔁 Continuidade real  
- 🔒 Controle de escopo  
- 📈 Evolução progressiva  
- 🧩 Decisões rastreáveis  
- ⚖️ Baixo consumo computacional  

---

## 7️⃣ Diferença da Versão Anterior

| Antes | Agora |
|-------|--------|
| Mentoria explicativa | Acompanhamento operacional |
| Foco em explicar metodologia | Foco em executar micro-passos |
| Estrutura comercial | Estrutura técnica e progressiva |
| Dados genéricos | Dados estruturados por estágio |

---

## 8️⃣ Limitações da Base

- Não acessa APIs externas  
- Não conecta com CRM  
- Não envia mensagens automaticamente  
- Não valida dados externos  
- Não aprende sozinho (depende dos arquivos)  

---

## 9️⃣ Próximas Evoluções Técnicas Possíveis

- Extração automática de decisão e próxima ação do texto  
- Separação de histórico por `session_id`  
- Compactação inteligente do contexto  
- Indexação por estágio da semana  
- Sistema de métricas automatizado  

---

## 🔟 Estado Atual

Base funcional para:

- Agente local via Ollama  
- UI própria (Streamlit)  
- Persistência em CSV  
- Evolução semana a semana  
- Controle comportamental via prompt  

**Maturidade atual:** Beta Avançado
