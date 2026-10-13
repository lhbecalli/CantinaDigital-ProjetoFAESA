# Cantina Digital FAESA

Aplicação web para pedidos antecipados na cantina universitária da FAESA, com agente de inteligência artificial por chat, ticket de pedido e painel de gestão para a equipe da cantina.

Projeto Integrador do curso de Sistemas de Informação, 4º período, turma 4SC1, Faculdades Integradas Espírito-santenses (FAESA).

> **Status:** etapa de protótipo e planejamento. O sistema ainda não foi desenvolvido; este repositório contém o protótipo interativo, a apresentação e o relatório da etapa C2.

## O problema

Situações comuns na cantina:

- Enfrentar a fila e, ao chegar ao balcão, descobrir que o produto desejado não está disponível.
- Fila no horário do intervalo, que faz o aluno perder boa parte do tempo livre.
- Dúvidas simples (alergias, restrições, opções) que dependem de perguntar a um atendente.

## A solução

1. **Pede:** o aluno vê o cardápio e monta o pedido manualmente ou conversando com o agente de IA.
2. **Gera o ticket:** o pedido confirmado gera um ticket com número e QR. O pagamento é feito no balcão, na maquininha, e a cantina confirma no painel. O sistema não integra meio de pagamento.
3. **Retira:** o aluno acompanha o status do pedido e é notificado quando estiver pronto.

### Funcionalidades previstas

| Aluno | Equipe da cantina | Agente de IA |
| --- | --- | --- |
| Ver o cardápio do dia | Painel web com pedidos em tempo real | Responder dúvidas sobre o cardápio |
| Pedir pelo fluxo tradicional ou por chat | Confirmar o pagamento feito no balcão | Montar o pedido por conversa |
| Gerar o ticket e pagar no balcão | Atualizar o status do pedido | Informar o status do pedido |
| Acompanhar o status | Gerenciar o cardápio | Sugerir combos com base em pedidos anteriores |
| Ser notificado quando o pedido estiver pronto | Receber relatórios periódicos de vendas | |

## Arquitetura

Sistema em camadas:

- **Frontend:** React + TailwindCSS
- **Backend:** FastAPI (Python), API REST
- **Banco de dados:** PostgreSQL
- **Agente de IA:** API de modelo de linguagem com *function calling*
- **Automações:** n8n (notificação de pedido pronto e relatórios de vendas)

## Protótipo interativo

O arquivo `prototipo.html` simula o fluxo completo, com dados fictícios:

- app do aluno (cardápio, carrinho, ticket, acompanhamento, assistente de conversa e perfil);
- painel da equipe da cantina (pedidos em quadro, cardápio e relatório).

**Como abrir:** baixe o repositório e abra o `prototipo.html` no navegador. Mantenha a pasta `img/` ao lado do arquivo.

Observações:

- O assistente de IA do protótipo é simulado por regras. No sistema real será um modelo de linguagem com *function calling* via FastAPI.
- Para ver o fluxo completo: peça pelo assistente, gere o ticket, mude para a visão "Cantina" e avance o pedido até "Pronto".

## Estrutura do repositório

