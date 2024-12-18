# ApiEcommerce

## Descrição

Este é um exemplo de especificação de API E-commerce baseado na especificação OpenAPI 3.0. Você pode encontrar mais informações sobre o Swagger em [https://swagger.io](https://swagger.io).

## Estrutura do Projeto

- `openapi.yaml`: Contém a especificação OpenAPI 3.0 para a API de E-commerce.
- `README.md`: Este arquivo.

## Endpoints

### Produtos

- **Adicionar Produto**
  - **POST** `/product`
  - Adiciona um novo produto ao catálogo.
  - **OperationId**: `addproduct`

- **Encontrar Produtos por Status**
  - **GET** `/product/findByStatus`
  - Encontra produtos por status.
  - **OperationId**: `findproductsByStatus`

- **Encontrar Produtos por Região**
  - **GET** `/product/findByRegion`
  - Encontra produtos por região.
  - **OperationId**: `findproductsByRegion`

- **Encontrar Produto por ID**
  - **GET** `/product/{productId}`
  - Retorna um único produto.
  - **OperationId**: `getproductById`

- **Atualizar Produto**
  - **PUT** `/product/{productId}`
  - Atualiza um produto existente.
  - **OperationId**: `updateproduct`

- **Deletar Produto**
  - **DELETE** `/product/{productId}`
  - Deleta um produto.
  - **OperationId**: `deleteproduct`

- **Upload de Imagem**
  - **POST** `/product/{productId}/uploadImage`
  - Faz upload de uma imagem para um produto.
  - **OperationId**: `uploadFile`

### Clientes

- **Criar Cliente**
  - **POST** `/customer`
  - Cria um novo cliente.
  - **OperationId**: `createcustomer`

- **Atualizar Cliente**
  - **PUT** `/customer/{idCustomer}`
  - Atualiza um cliente existente.
  - **OperationId**: `updatecustomer`

- **Deletar Cliente**
  - **DELETE** `/customer/{idCustomer}`
  - Deleta um cliente.
  - **OperationId**: `deletecustomer`

- **Obter Cliente por ID**
  - **GET** `/customer/{idCustomer}`
  - Obtém um cliente pelo ID.
  - **OperationId**: `getcustomerByName`

- **Criar Lista de Clientes**
  - **POST** `/customer/createWithList`
  - Cria uma lista de clientes com base em um array de entrada.
  - **OperationId**: `createcustomersWithListInput`

### Pedidos

- **Fazer Pedido**
  - **POST** `/order`
  - Faz um pedido para um cliente.
  - **OperationId**: `placeOrder`

- **Obter Pedido por ID**
  - **GET** `/order/{orderId}`
  - Obtém um pedido pelo ID.
  - **OperationId**: `getOrderById`

- **Deletar Pedido**
  - **DELETE** `/order/{orderId}`
  - Deleta um pedido pelo ID.
  - **OperationId**: `deleteOrder`

- **Obter Pedidos por Cliente**
  - **GET** `/customer/{idCustomer}/orders`
  - Obtém pedidos de um cliente pelo ID do cliente.
  - **OperationId**: `getOrdersByCustomerId`

### Estoque

- **Adicionar Inventário**
  - **POST** `/stock/add/{idProduct}`
  - Adiciona inventários de produtos ao estoque.
  - **OperationId**: `addInventory`

- **Subtrair Inventário**
  - **POST** `/stock/subtract/{idProduct}`
  - Subtrai inventários de produtos do estoque.
  - **OperationId**: `subtractInventory`

- **Transferir Inventário**
  - **POST** `/stock/transfer/{idProduct}`
  - Transfere inventários de produtos entre locais.
  - **OperationId**: `transferInventory`

- **Obter Inventário por ID do Produto**
  - **GET** `/stock/{idProduct}`
  - Retorna inventários de produtos por ID do produto.
  - **OperationId**: `getInventory`

- **Deletar Inventário**
  - **DELETE** `/stock/{idProduct}`
  - Deleta um inventário de produto.
  - **OperationId**: `deleteInventory`

## Componentes

### Schemas

- **Product**
- **Order**
- **Customer**
- **Address**
- **Category**
- **OrderItem**
- **Transfer**
- **ApiResponse**

## Segurança

- **Ecommerce_auth**
  - Tipo: `oauth2`
  - Flows: `implicit`
  - Authorization URL: `https://Ecommerce3.swagger.io/oauth/authorize`
  - Scopes:
    - `write:products`: Modificar produtos na sua conta
    - `read:products`: Ler seus produtos

- **api_key**
  - Tipo: `apiKey`
  - Nome: `api_key`
  - Local: `header`

## Licença

Licenciado sob a [Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).