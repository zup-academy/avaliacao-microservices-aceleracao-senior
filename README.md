## Zup Edu Commerce

Neste desafio você será responsavel pela criação de dois microsserviços para auxiliar na entrega de um MarketPlace.

O primeiro microserviço a ser desenvolvido é o **_MarketPlace_** que é responsavel receber a solicitação de compra de produtos de um usuario. E caso uma Venda seja concretizada comunicar-se com o Microsserviço de **_Notas Fiscais_**.


O Segundo microsserviço a ser desenvolvido é o serviço de **_Notas Fiscais_** responavel por consumir as vendas realizadas, e gerar uma notafiscal para cada venda. E em segundo plano deverá notificar o usuario compradaor através do email com a notagerada e a confirmação de compra.

A imagem abaixo ilustra o fluxo descrito acima.

![Ecosistema de Microsserviços](/imagens/ecosistema.png)

Para subir a infraestrutura necessária para construção do desafio, você ira utilizar o seguinte [docker-compose.yaml](/setup/docker-compose.yml), este ira disponibilizar os demais serviços da rede.

## Atividades
- [Construção do sistema de **_MarketPlace_**](/atividades/sistema-de-compras.md)
- [Construção do sistema de **_Notas Fiscais_**](/atividades/Sisitema-de-nf.md)