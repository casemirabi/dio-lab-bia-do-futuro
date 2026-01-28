# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Utilização no Agente |
|--------|--------|----------------------|
| historico_conversas.csv | CSV | Contextualizar interações anteriores, identificar objeções recorrentes e estágio do funil |
| perfil_negocio.json | JSON | Definir proposta de valor, tom de voz e diferenciais da mentoria |
| oferta_mentoria.json | JSON | Fornecer detalhes da mentoria, benefícios, CTAs e respostas para objeções |
| leads.csv | CSV | Acompanhar status dos leads e apoiar sugestões de follow-up |

---

## Estratégia de Integração

### Como os dados são carregados?
Os JSON/CSV são carregados no início da sessão e incluídos no contexto do prompt

### Como os dados são usados no prompt?
Os dados vão no system prompt e são consultados dinamicamente na pasta data.

---

## Exemplo de Contexto Montado

```text
Dados do Negócio:
- Nome: Mentoria Conversão Digital
- Proposta de valor: Estruturar atendimento e comunicação focados em conversão em até 30 dias
- Diferenciais: acompanhamento individual, método validado, scripts prontos de vendas
- Garantia: 7 dias incondicional

Oferta ativa:
- Produto: Mentoria Conversão Digital
- Duração: 4 semanas
- Principais benefícios: feedback individual, plano de ação semanal, exemplos reais de conversas que convertem

Lead atual:
- Canal: site_chat
- Etapa do funil: decisão
- Objeção identificada: caro

Histórico recente:
- Lead perguntou valor da mentoria
- Demonstrou dúvida sobre retorno do investimento

Instrução ao agente:
Responder de forma direta, profissional e acessível, tratando objeções com empatia e conduzindo o lead ao próximo passo.
```
