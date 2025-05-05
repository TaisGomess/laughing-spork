Modelagem e Consultas em MongoDB Cenário

Você está desenvolvendo uma aplicação de entregas de comida, similar ao iFood ou Uber Eats. Cada pedido é realizado por um cliente, contém uma lista de produtos, e é entregue por um entregador. Os dados devem permitir análises sobre os pedidos, os produtos mais vendidos e os entregadores mais ativos.

Sua tarefa é:

- Definir a modelagem correta dos dados.

- Escrever consultas para resolver os problemas propostos.


1. Modelagem
Decida quais dados devem ser embutidos (embedded) e quais devem ser referenciados.

Entidades:

Cliente

Entregador

Pedido

Produto

Justifique sua decisão considerando os padrões de acesso esperados na aplicação.



2. Consultas

Dado para as consultas
db.pedidos.insertOne({
  cliente_id: ObjectId("64b3f"),
  entregador_id: ObjectId("64b3e..."),
  nome:"Carlos Mendes"
  data: ISODate("2024-04-01T00:00:00Z"),
  status: "entregue",
  local: {
    type: "Point",
    coordinates: [-46.6333, -23.5505]
  },
  produtos: [
    { nome: "Pizza Calabresa", preco: 35 },
    { nome: "Coca-Cola 2L", preco: 10 }
  ]
})
Escreva as seguintes consultas:

a) Retorne todos os pedidos entregues por "Carlos Mendes".

b) Liste os nomes dos produtos e os totais de vendas (quantidade vendida) agrupados.

c) Encontre pedidos entregues perto da coordenada [-46.634, -23.551] com raio de 1 km.

d) Retorne todos os pedidos que contenham o item "Pizza Calabresa".

e) Projete apenas o nome do cliente e os nomes dos produtos do pedido.
