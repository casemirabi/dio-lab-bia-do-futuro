# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Utilização no Agente |
|--------|--------|----------------------|
| historico_conversas.csv | CSV | Contextualizar interações anteriores e identificar estágio da jornada do usuário |
| perfil_negocio.json | JSON | Definir proposta da mentoria, tom de voz e abordagem de acompanhamento |
| oferta_mentoria.json | JSON | Fornecer estrutura do programa, objetivos, benefícios e próximos passos |
| participantes.csv | CSV | Acompanhar estado da jornada dos participantes e sugerir ações educativas |

---

## Estratégia de Integração

### Como os dados são carregados?
Os arquivos CSV e JSON são carregados no início da sessão do agente e mantidos em memória local.

### Como os dados são usados no prompt?
Os dados não são inseridos integralmente no system prompt. Apenas os trechos relevantes (como estágio da jornada, informações da mentoria e histórico recente) são recuperados dinamicamente e adicionados ao contexto da conversa.

---

## Exemplo de Contexto Montado

```text
Dados da Mentoria:
- Nome: Mentoria Conversão Digital
- Proposta: Organizar atendimento e comunicação ao longo de 4 semanas
- Diferenciais: acompanhamento individual, metodologia prática, plano de ação semanal
- Garantia: 7 dias para avaliação

Programa ativo:
- Nome: Mentoria Conversão Digital
- Duração: 4 semanas
- Objetivos principais: estruturar comunicação, organizar processo e desenvolver autonomia

Participante atual:
- Canal: site_chat
- Etapa da jornada: onboarding
- Situação: iniciando diagnóstico do negócio

Histórico recente:
- Usuário pediu explicação da metodologia
- Demonstrou insegurança sobre próximos passos

Instrução ao agente:
Responder de forma clara, profissional e acessível, orientando o usuário e sugerindo ações práticas de acordo com sua etapa na mentoria.
