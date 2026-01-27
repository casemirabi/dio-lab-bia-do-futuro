# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Identificar objeções recorrentes, estágio do funil e padrões de conversão |
| `perfil_investidor.json` | JSON | Definir tom de voz, proposta de valor e diferenciais da mentoria |
| `produtos_financeiros.json` | JSON | Fornecer detalhes da oferta, benefícios, CTAs e respostas para objeções |
| `transacoes.csv` | CSV | Acompanhar status dos leads e apoiar sugestões de follow-up |

---

## Adaptações nos Dados

Os dados utilizados foram adaptados a partir de modelos genéricos para o contexto de infoprodutos e mentoria digital. Foram incluídos campos relacionados ao estágio do funil de vendas, objeções comuns (como preço e confiança), provas sociais, CTAs e status de conversão. Também foram criados registros simulados de leads e histórico de conversas para permitir que o agente reconheça padrões de atendimento e sugira abordagens mais eficazes.

---

## Estratégia de Integração

### Como os dados são carregados?

Existem duas possibilidades, injetar os dados diretamente no prompt (Ctrl + c, Ctrl + V) ou carregar os arquivos via prompt.
```
import pandas as pd
import json

# CSVs
historico_conversas = pd.read_csv('data/historico_conversas.csv')
leads = pd.read_csv('data/leads.csv')

# JSONs
with open('data/perfil_investidor.json', 'r', encoding='utf-8') as f:
    perfil_negocio = json.load(f)

with open('data/produtos_financeiros.json', 'r', encoding='utf-8') as f:
    oferta = json.load(f)

```

### Como os dados são usados no prompt?
Para simplificar, podemos simplesmente "injetar" os dados em nosso prompt, garantindo que o Agente tenha o melhor contexto para que possa ganhar flexibilidade.
```text
Dados do cliente e perfil:
{
  "negocio": {
    "nome": "Loja Aurora",
    "segmento": "e-commerce de skincare",
    "publico_alvo": "Mulheres 20-40, interessadas em cuidados com a pele e rotina simples",
    "proposta_valor": "Skincare prático com resultados visíveis e orientação na compra",
    "tom_de_voz": "direto, cordial, profissional e acessível",
    "canais": ["Instagram", "WhatsApp", "Site"],
    "horario_atendimento": "Seg-Sex 09:00-18:00",
    "diferenciais": [
      "curadoria de produtos",
      "envio rápido",
      "suporte para escolher rotina"
    ],
    "politicas": {
      "prazo_entrega_medio": "3-7 dias úteis",
      "troca_devolucao": "7 dias após recebimento",
      "frete_gratis_acima": 199.00,
      "formas_pagamento": ["Pix", "Cartão", "Boleto"]
    },
    "objetivos": {
      "principal": "aumentar conversão no WhatsApp e Instagram",
      "secundarios": ["reduzir abandono por objeção de preço", "padronizar atendimento"]
    }
  }
}

Histórico de necessidades do cliente:
{
  "negocio": {
    "nome": "Loja Aurora",
    "segmento": "e-commerce de skincare",
    "publico_alvo": "Mulheres 20-40, interessadas em cuidados com a pele e rotina simples",
    "proposta_valor": "Skincare prático com resultados visíveis e orientação na compra",
    "tom_de_voz": "direto, cordial, profissional e acessível",
    "canais": ["Instagram", "WhatsApp", "Site"],
    "horario_atendimento": "Seg-Sex 09:00-18:00",
    "diferenciais": [
      "curadoria de produtos",
      "envio rápido",
      "suporte para escolher rotina"
    ],
    "politicas": {
      "prazo_entrega_medio": "3-7 dias úteis",
      "troca_devolucao": "7 dias após recebimento",
      "frete_gratis_acima": 199.00,
      "formas_pagamento": ["Pix", "Cartão", "Boleto"]
    },
    "objetivos": {
      "principal": "aumentar conversão no WhatsApp e Instagram",
      "secundarios": ["reduzir abandono por objeção de preço", "padronizar atendimento"]
    }
  }
}

Históricos de atendimento do cliente:
data,canal,etapa_funil,tema,resumo,status,proxima_acao,resultado
2026-01-10,instagram_dm,consideracao,Preco,Cliente pediu valor do plano e formas de pagamento,em_andamento,Enviar tabela de planos e bônus,
2026-01-12,whatsapp,decisao,Objeção: "caro",Cliente achou caro e comparou com concorrente,resolvido,Reforçar diferenciais + prova social,fechou
2026-01-14,site_chat,consideracao,Prazos,Cliente perguntou prazo de entrega e política de troca,resolvido,Enviar link de políticas + estimativa,fechou
2026-01-18,instagram_dm,topo_funil,Duvida geral,Cliente perguntou “como funciona?”,resolvido,Explicar passo a passo + CTA para orçamento,nao_fechou
2026-01-20,email,decisao,Boleto/Nota fiscal,Cliente pediu nota fiscal e opção boleto,resolvido,Confirmar dados e enviar link de pagamento,fechou

```


---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

O exemplo de contexto mostrado abaixo, se baseia nos dados originais da base de conhecimento, mas os sintetiza deixando apenas as informções mais relevantes, otimizando assim o consumo de tokens. Entretando, vale lembrar que mais importante do que economizar tokens, é ter todas as informações relevantes disponíveis em seu contexto.

```
Dados do Negócio:
- Nome: Mentoria Conversão Digital
- Proposta de valor: Estruturar atendimento e comunicação focados em conversão em até 30 dias
- Diferenciais: acompanhamento individual, método validado, suporte durante o programa
- Garantia: 7 dias incondicional

Oferta ativa:
- Produto: Mentoria Conversão Digital
- Valor: R$ 997
- Duração: 4 semanas
- Principais benefícios: scripts de venda, feedback individual, plano de ação personalizado

Lead atual:
- Origem: site_chat
- Etapa do funil: decisão
- Objeção identificada: caro

Respostas recomendadas para objeção “caro”:
- “Entendo — por isso sempre comparo o valor com o custo de continuar sem vender. A mentoria foi criada para se pagar com os primeiros fechamentos.”
- “Muitos alunos também acharam caro no início, mas recuperaram o investimento ainda durante o programa.”

Instrução ao agente:
Responder de forma direta, profissional e acessível, conduzindo o lead à conversão sem pressionar.

```
