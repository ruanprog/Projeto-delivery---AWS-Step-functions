# 🍕 Assistente de Delivery com AWS Step Functions 🚀

Este repositório apresenta um **assistente de delivery serverless** desenvolvido com **AWS Step Functions**, simulando um fluxo de trabalho de entrega simples e eficiente. Ele inclui etapas como receber pedidos, confirmar pagamentos, preparar pedidos, atualizar status de entrega e notificar clientes.

## 📋 Funcionalidades

- **🛒 Receber Pedido**: Processa os detalhes do pedido do cliente.
- **💳 Confirmar Pagamento**: Verifica se o pagamento foi aprovado ou rejeitado.
- **🍳 Preparar Pedido**: Organiza e processa o pedido, pronto para entrega.
- **🚚 Atualizar Status de Entrega**: Atualiza o status para cada etapa, como "Em preparação" ou "A caminho".
- **📩 Notificar Cliente**: Envia notificações via e-mail, SMS ou aplicativo para manter o cliente informado.

---

## 🚀 Fluxo de Trabalho do Step Functions

O assistente segue um fluxo de trabalho criado em **AWS Step Functions** utilizando o **Amazon States Language (ASL)**. Aqui está um resumo das etapas:

1. **ReceberPedido** 🛒  
   Recebe os detalhes do pedido do cliente e retorna a confirmação.  
   - **Entrada:** ID do pedido, itens e informações do cliente.  
   - **Saída:** Dados estruturados do pedido.

2. **ConfirmarPagamento** 💳  
   Verifica o status do pagamento:  
   - **Aprovado**: Continua para preparar o pedido.  
   - **Rejeitado**: Encerra o fluxo com erro.  

3. **PrepararPedido** 🍳  
   Processa o pedido, como embalar itens ou preparar refeições.

4. **AtualizarStatusEntrega** 🚚  
   Atualiza o status do pedido em tempo real (ex.: "Preparado", "Saiu para entrega").

5. **NotificarCliente** 📩  
   Envia uma mensagem ao cliente informando o status final do pedido.

---

## 📂 Estrutura do Projeto

📦 **AssistenteDeDelivery** <br>
 ┣ 📜 state-machine.json     # Definição do Step Functions em ASL <br>
 ┣ 📂 lambdas                # Funções Lambda para cada etapa <br>
 ┃ ┣ 📜 receber_pedido.py <br>
 ┃ ┣ 📜 confirmar_pagamento.py <br>
 ┃ ┣ 📜 preparar_pedido.py <br>
 ┃ ┣ 📜 atualizar_status.py <br>
 ┃ ┗ 📜 notificar_cliente.py <br>
 ┣ 📜 README.md              # Este arquivo <br>


## 🛠️ Configuração e Implantação

- 1️⃣**Pré-requisitos**
Conta AWS ativa
AWS CLI configurada
Permissões para criar funções Lambda e executar Step Functions
Conhecimento básico de Python
- 2️⃣ **Implantação Manual**
Criar as funções Lambda
Implante cada arquivo no diretório lambdas/ como uma função Lambda separada.

Configurar o Step Functions
Importe o arquivo state-machine.json no console do Step Functions para criar o fluxo de trabalho.

Testar o Fluxo
Envie um evento de teste no Step Functions para simular o pedido.

🧪 Exemplos de Entrada e Saída
- Entrada: Receber Pedido
json

{
  "id": "12345",<br>
  "itens": ["Pizza", "Refrigerante"],
 <br>"cliente": {
    "nome": "João Silva",
    <br>"telefone": "+55 11 98765-4321"
  }
}
<br> - Saída: Notificar Cliente
json
<br>
{
  "mensagem": "Olá João Silva, seu pedido está a caminho!"
}
<br>

## 📦 Tecnologias Utilizadas
- AWS Step Functions
- AWS Lambda
- Python 3.9
- Amazon SNS (para notificações)
- Amazon CloudWatch (para monitoramento)

## 🌟 Próximos Passos

- 📍 Rastreamento em tempo real: Adicione integração com o Amazon Location Service para mostrar a localização da entrega.
- 🗂️ Armazenamento persistente: Use DynamoDB para armazenar informações de pedidos.
- 📊 Dashboards: Crie visualizações com Amazon QuickSight para monitorar desempenho.
- 🛡️ Segurança

### Certifique-se de:

Configurar roles IAM com permissões mínimas necessárias.
Armazenar dados sensíveis de forma segura (ex.: usando AWS Secrets Manager).

### 📜 Licença
Este projeto é licenciado sob a Licença MIT-0. Consulte o arquivo LICENSE para mais informações.


### 🌐 Website: AWS Step Functions

Se este projeto foi útil, 🌟 dê uma estrela no repositório e contribua! 😊
