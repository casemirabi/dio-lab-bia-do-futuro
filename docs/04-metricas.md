# 📊 Avaliação e Métricas

**Versão Atual — Agente 4 Semanas (Ollama / qwen2.5:3b)**

---

## 🎯 Objetivo da Avaliação

Avaliar se a Luna está:

- Mantendo continuidade  
- Respeitando o método das 4 semanas  
- Controlando escopo corretamente  
- Entregando micro-ações executáveis  
- Utilizando linguagem humana e natural  
- Evitando complexidade precoce  
- Não repetindo decisões já tomadas  

---

## 🧪 Como Avaliar o Agente

A avaliação pode ser feita em três níveis:

### 1️⃣ Testes Estruturados

Sequência controlada de perguntas com respostas esperadas.

### 2️⃣ Teste de Continuidade

Enviar mensagens sequenciais e verificar se o agente:

- Lembra decisões anteriores  
- Avança estado  
- Não reinicia processo  

### 3️⃣ Experiência Real

Simulação prática de uso por 15–30 minutos.

Recomenda-se que **3–5 pessoas** testem o agente e atribuam notas de **1 a 5** para cada métrica.

---

## 📈 Métricas de Qualidade

| Métrica | O que avalia | Como testar |
|----------|--------------|-------------|
| Continuidade | O agente evita repetir decisões já tomadas? | Enviar mesma dor 2x e verificar se ele avança |
| Controle de Escopo | Evita propor soluções grandes cedo demais? | Dizer “meu atendimento está confuso” e ver se ele não cria funil/script |
| Micro-execução | Sugere ações pequenas (10–30 min)? | Dizer que tem pouco tempo |
| Linguagem Natural | A resposta soa como WhatsApp real? | Verificar ausência de tom institucional |
| Objetividade | A resposta é direta e prática? | Avaliar tamanho e clareza |
| Limitação de Perguntas | Faz no máximo 1 pergunta? | Mensagem vaga como “tá tudo errado” |
| Segurança | Não inventa dados externos? | Pergunta fora do escopo |

---

## 🧩 Testes Essenciais

### 🟢 Teste 1 — Controle de Escopo

**Pergunta:**  
“Meu atendimento está confuso.”

**Resposta esperada:**

- Não propor script completo  
- Não propor funil  
- Focar em UMA mensagem  
- Micro-ação prática  

**Resultado:**  
[x] Correto  
[ ] Incorreto  

---

### 🔁 Teste 2 — Continuidade

**Sequência:**

1. “Tenho 5 leads por semana e demoro pra responder.”  
2. “Meu atendimento ainda está confuso.”

**Resposta esperada:**

- Não repetir decisão inicial  
- Avançar para execução ou ajuste  
- Não reiniciar processo  

**Resultado:**  
[x] Correto  
[ ] Incorreto  

---

### ⏱ Teste 3 — Limite de Tempo

**Pergunta:**  
“Só tenho 15 minutos por dia.”

**Resposta esperada:**

- Micro-ação compatível com 15 min  
- Nada de plano amplo  
- Nenhuma pergunta desnecessária  

**Resultado:**  
[x] Correto  
[ ] Incorreto  

---

### 🗣 Teste 4 — Linguagem Natural

**Pergunta:**  
“Me dá uma mensagem de primeiro contato.”

**Resposta esperada:**

- Linguagem natural  
- Não usar:
  - “Agradecemos”
  - “Estamos empenhados”
  - “É um prazer”
  - “Ficamos felizes”
- Tom humano e simples  

**Resultado:**  
[x] Correto  
[ ] Incorreto  

---

### 🔒 Teste 5 — Fora de Escopo

**Pergunta:**  
“Qual a previsão do tempo?”

**Resposta esperada:**

- Recusar educadamente  
- Redirecionar para organização de atendimento  

**Resultado:**  
[x] Correto  
[ ] Incorreto  

---

### 🧠 Teste 6 — Resistência Emocional

**Pergunta:**  
“Tô cansado de responder e ninguém valoriza.”

**Resposta esperada:**

- Reconhecer brevemente  
- Voltar para ação prática  
- Não virar discurso motivacional  

**Resultado:**  
[x] Correto  
[ ] Incorreto  

---

## 📊 Critério de Aprovação

Para considerar o agente pronto para uso real:

- 90% dos testes devem ser “Correto”  
- Nenhum erro crítico de escopo  
- Nenhum tom institucional  
- Nenhuma reinicialização indevida de decisão  

---

## 🚨 Erros Críticos

Se ocorrer qualquer um abaixo, deve ser ajustado:

- Propor funil antes da Semana 2  
- Propor automação na Semana 1  
- Repetir decisão já tomada  
- Usar linguagem institucional  
- Fazer múltiplas perguntas  
- Gerar resposta longa demais  
- Prometer resultado  

---

## 📉 Métricas Técnicas (Modelo Leve)

| Métrica | Objetivo |
|----------|----------|
| Tamanho médio da resposta | Curto e objetivo |
| Número médio de bullets | Máximo 3 |
| Perguntas por resposta | Máximo 1 |
| Tempo de resposta | < 3 segundos localmente |
| Consistência de formato | Sempre seguir estrutura fixa |

---

## 🔍 Avaliação Qualitativa

Após rodar os testes, registrar:

**O que funcionou bem:**  
[Diagnostico com solução breve]

**Onde ainda escapa:**  
[Contextos longos]

**Ajustes necessários:**  
[Testes maiores]

---

## 📈 Métricas Futuras (Opcional)

- Extração automática de decisão para CSV  
- Percentual de avanço de semana  
- Frequência de repetição de decisão  
- Score de naturalidade do texto  
- Monitoramento automático de escopo  

---

## 🏁 Estado Atual

**Maturidade:** Beta Avançado (~90–95%)

O agente já demonstra:

- Continuidade funcional  
- Estrutura consistente  
- Micro-execução adequada  
- Controle de escopo parcialmente consolidado  

