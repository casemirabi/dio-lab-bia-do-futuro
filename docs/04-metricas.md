# 📊 Avaliação e Métricas

## Como Avaliar o Agente

A avaliação da Luna pode ser feita de duas formas complementares:

- **Testes estruturados:** conjunto de perguntas com respostas esperadas.
- **Feedback real:** usuários simulam interações e avaliam a experiência.

Recomenda-se que 3 a 5 pessoas testem o agente e atribuam notas de 1 a 5 para cada métrica.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|--------|-------------|------------------|
| Assertividade | A Luna respondeu exatamente ao que foi perguntado? | Perguntar como funciona a mentoria e receber explicação clara |
| Segurança | A Luna evita inventar informações? | Perguntar algo fora do escopo e ela admitir que não sabe |
| Coerência | A resposta faz sentido para o estágio do lead? | Tratar objeção de preço com empatia e valor, não com pressão |
| Clareza | A resposta é fácil de entender? | Explicação objetiva do programa |
| Orientação à ação | A Luna conduz para o próximo passo? | Finalizar respostas com CTA apropriado |

---

## Exemplos de Cenários de Teste

### Teste 1 — Funcionamento da mentoria
**Pergunta:**  
"Como funciona essa mentoria?"

**Resposta esperada:**  
Explicação das 4 semanas, metodologia e benefícios.

Resultado: [x] Correto [ ] Incorreto

---

### Teste 2 — Objeção de preço
**Pergunta:**  
"Achei caro."

**Resposta esperada:**  
Empatia + explicação de valor + referência à garantia.

Resultado: [ ] Correto [ ] Incorreto

---

### Teste 3 — Pergunta fora do escopo
**Pergunta:**  
"Você vende produtos físicos?"

**Resposta esperada:**  
A Luna informa que atua apenas com a mentoria e comunicação digital.

Resultado: [x] Correto [ ] Incorreto

---

### Teste 4 — Informação inexistente
**Pergunta:**  
"Quantos alunos fecharam contrato ontem?"

**Resposta esperada:**  
A Luna admite não ter essa informação.

Resultado: [ ] Correto [ ] Incorreto

---

### Teste 5 — Falta de confiança
**Pergunta:**  
"Isso realmente funciona?"

**Resposta esperada:**  
Uso de prova social + explicação do método + garantia.

Resultado: [ ] Correto [ ] Incorreto

---

## Resultados

Após os testes, registrar:

**O que funcionou bem:**
- [ ]

**O que pode melhorar:**
- [ ]

---

## Métricas Avançadas (Opcional)

- Tempo médio de resposta do agente
- Frequência de CTAs por conversa
- Taxa de respostas fora do escopo
- Logs de interações para análise qualitativa

Ferramentas de observabilidade de LLM podem ser utilizadas, caso desejado, mas não são obrigatórias para o MVP.
