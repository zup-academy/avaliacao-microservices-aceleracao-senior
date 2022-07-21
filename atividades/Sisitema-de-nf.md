# Sistema de Nota Fiscal

Sitema de Notas Ficais é um modulo importante do ecosistema de microsserviços, é através deste que as vendas tem suas notas geradas, e os usuarios recebem a confirmação da compra, junto a nota fiscal.

Este sistema deve ouvir o topico de `Venda` do Kafka, e para cada evento de venda, deverá processar a nota, e armazena-la no banco de dados com um identificador numero de 5 caracteres.

Quando uma notafiscal é processada, ela pode ficar em dois estados: 

- GERADA: significa que a nota foi gerada com sucesso e esta pronta para ser enviada pelo cliente.

- GERADA_E_ENVIADA: significa que a nota foi gerada e enviada para o cliente através do email.


A Nota fiscal quando processada deve corresponder ao seguinte schema: 

```json

{
    "numeroDaNota":"1536478",
    "criadoEm":"2022-05-15 15:45:13",
    "nomeComprador": "Welligton Moura Borges",
    "cpf":"12345678910",
    "endereco":"Rua Presidente Vargas n 89 APT 294, Jardim Europa - Porto Seguro, BA - 38951-222",
    "itens":[
        {
            "nome": "Playstation 5 512 SSD",
            "quantidade": 1,
            "valor": 4900
        },
        {
            "nome": "JoyStisck Playstation 5",
            "quantidade": 1,
            "valor": 620
        }
    ],
    "valorTotal": 5520,
}
```

Da tempo em tempo, todas as notas geradas com o status: `GERADA`, devem ser enviadas em XML para o email do usuario junto a uma mensagem de confirmação de compra para o numero do pedido. E quando uma nota for enviada por email seu status deve ser alterado para `GERADA_E_ENVIADA`.
