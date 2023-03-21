<h1 align="center">Market Maker</h1>
<h2 align="center">O sistema de gerenciamento certo para o seu negócio!</h2>

<p>O projeto Market Maker visa gerenciar os pedidos realizados presencialmente em restaurantes e bares, provendo uma otimização de tempo do momento do pedido até a produção, facilitando a comunicação entre as equipes do estabelecimento.
O sistema automatiza o recebimento de pedidos, serviço de mesa, preparo e entrega de produtos.
Tudo é controlado através de eletrônicos, mantendo os registros de cada etapa.
A partir daí, Market Maker visa um sistema de qualidade, que evita erros humanos e falhas sistêmicas. 
</p>

<p>Mesmo com a tecnologia, muitos estabelecimentos tradicionais acabam mantendo antigos costumes, como anotar pedidos em um bloco de notas, o que, muitas vezes, pode causar confusão e perda de comandas, assim como um tempo mais longo de espera devido à falta de automatização, já que a equipe de garçons, por exemplo, teria que se deslocar do salão à cozinha a cada pedido.
Há também a questão de não manter registros e não realizar a soma automática da comanda. Assim realizando alguns trabalhos desnecessários. 
Da mesma forma, há locais que possuem um sistema falho, onde muitas vezes acabam recorrendo a métodos mais antiquados devido à quantidade de erros que o mesmo possui.
</p>

<p>Esta aplicação contará com um usuário adminstrador, este que fará todo o gerenciamento do bar/restaurante etc.. o usuário administrador poderá cadastrar seus funcionários no aplicativo, ca um deles poderá acessar a plataforma depois, com diferentes permissões.</p>
<p>Devido a isso, todas as rotas serão autenticadas.</p>

### Antes de prosseguirmos para as rotas, vamos entender melhor o fluxo da aplicação:
<p>O <strong>administrador</strong> será o dono do App, e iniciará fazendo a criação dos das categorias de produtos que irá vender, logo após fará a criação dos produtos que estarão relacionados a sua ctegoria.
</p>
<p> O administrador irá fazer a criação também, das mesas que estarão no seu bar/restaurante.</p>
<p> Por fim, ele criará todos os usuários sem a permissão de adminstrador, estes que serão os funcionários.</p>
<br/>

<p>Um funcionário agora, assim como o adminstrador, precisará logar na aplicação, o aplicativo listará automaticamente todas as mesas que estarão criadas no local, o funcionário poderá também, acessar a lista de produtos cadastrados, e acessar suas informações.</p>
<p>Sua responsabilidade será criar os pedidos, anotando qual a mesa em que foi requisitado os pedidos, e quais produtos foram pedidos.</p>

### Segue uma representação visual do fluxo de uma aplicação:
<a href="https://drive.google.com/file/d/1hiRtd-wh7dhQUcjocB0fzxJ6_Y0M1JaB/view?usp=share_link">Acessar representação</a>



# Funcionalidades do adminstrador

## Criação de usuários

`POST /users - FORMATO DE REQUISIÇÃO`

<p>Exemplo de requisição</p>

```json

{
	"username": "exampleReq",
	"name": "Teste", 
	"password": "1234",
	"isAdm": true
}
```

`POST /users - FORMATO DE RESPOSTA- Status Code - 401`
<P>Exemplo de resposta</p>

```json
{
    "updatedAt": "2023-01-17T16:34:26.848Z",
    "createdAt": "2023-01-17T16:34:26.848Z",
    "id": "7e76f619-511e-4fbf-8a2b-f0b937e2a779",
    "isAdm": true,
    "name": "Teste",
    "username": "exampleReq"
}
```

## Listagem de de usuários

### Buscar todos os usuários

`GET /users - FORMATO DE RESPOSTA- Status Code - 200`

<P>Exemplo de resposta</p>

```json
[
    {
        "updatedAt": "2023-01-17T16:34:26.848Z",
        "createdAt": "2023-01-17T16:34:26.848Z",
        "id": "7e76f619-511e-4fbf-8a2b-f0b937e2a779",
        "isAdm": true,
        "name": "Teste",
        "username": "exampleReq"
    }
]
```

### Buscar um usuário específico

`GET /users/id - FORMATO DE RESPOSTA- Status Code - 200`
<P>Exemplo de resposta</p>

```json
{
    "updatedAt": "2023-01-17T16:34:26.848Z",
    "createdAt": "2023-01-17T16:34:26.848Z",
    "id": "7e76f619-511e-4fbf-8a2b-f0b937e2a779",
    "isAdm": true,
    "name": "Teste",
    "username": "exampleReq"
}
```
## Atualização de usuários

### Atualizar um usuário

`PATCH /users/id - FORMATO DE REQUISIÇÃO`
<P>Exemplo de requisição</p>

```json
{
	"username": "adminAtualizado"
}
```

`PATCH /users/id - FORMATO DE RESPOSTA- Status Code - 200`
<P>Exemplo de resposta</p>

```json
{
    "updatedAt": "2023-01-17T16:42:43.353Z",
    "createdAt": "2023-01-17T16:34:26.848Z",
    "id": "7e76f619-511e-4fbf-8a2b-f0b937e2a779",
    "isAdm": true,
    "name": "Teste",
    "username": "adminAtualizado"
}
```

## Deleção de usuários

`DELETE /users/id - FORMATO DE RESPOSTA- Status Code - 204`
<P>Exemplo de resposta</p>

```json
```

## Login de usuários

`POST /login - FORMATO DE REQUISIÇÃO`
<P>Exemplo de requisição</p>

```json
{
	"username": "exampleReq",
	"password": "1234"
}
```

`POST /login - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de reposta</p>

```json
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImV4YW1wbGVSZXEiLCJpc0FkbSI6dHJ1ZSwiaWF0IjoxNjczOTczNDk2LCJleHAiOjE2NzQwNTk4OTYsInN1YiI6IjdlNzZmNjE5LTUxMWUtNGZiZi04YTJiLWYwYjkzN2UyYTc3OSJ9.8-kInSIjRZ6FqXeXCEThskyQtbfwt5CV8oNGHiQdjEI"
}
```

# Categorias
## Criação de uma categoria de alimentos

`POST /categories - FORMATO DE REQUISIÇÃO`
<P>Exemplo de requisição</p>

```json
{
	"name": "Bebidas"
}
```

`POST /categories - FORMATO DE RESPOSTA - Status Code - 401`
<P>Exemplo de resposta</p>

```json
{
    "name": "Bebidas",
    "id": "6b59e941-432d-4f1e-978b-00e15c5ef99d",
    "createdAt": "2023-01-17T16:49:45.941Z",
    "updatedAt": "2023-01-17T16:49:45.941Z"
}
```
## Listagem de categorias

### Buscar uma categoria específica

`GET /categories/id - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
[
    {
        "id": "6b59e941-432d-4f1e-978b-00e15c5ef99d",
        "name": "Bebidas",
        "createdAt": "2023-01-17T16:49:45.941Z",
        "updatedAt": "2023-01-17T16:49:45.941Z"
    }
]
```
### Buscar todas as caategorias

`GET /categories - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
[
    {
        "id": "6b59e941-432d-4f1e-978b-00e15c5ef99d",
        "name": "Bebidas",
        "createdAt": "2023-01-17T16:49:45.941Z",
        "updatedAt": "2023-01-17T16:49:45.941Z"
    }
]
```

### Listar todos os produtos de uma categoria

`GET /categories/product/id - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
[
    {
        "in_stock": true,
        "price": "2.99",
        "category": {
            "name": "Bebidas",
            "id": "d8cfb040-1f09-4f4e-b8cd-8200f54fef91"
        },
        "name": "Refrigerante atualizado",
        "id": "7312d555-86aa-4a97-b7d4-24faac49add3"
    }
]
```
## Atualização de categorias

`PATCH /categories/id - FORMATO DE REQUISIÇÃO`
<P>Exemplo de requisição</p>

```json
{
	"name":"Bebidas Atualizado"
} 
```

`PATCH /categories/id - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
{
    "id": "6b59e941-432d-4f1e-978b-00e15c5ef99d",
    "name": "Bebidas Atualizado",
    "createdAt": "2023-01-17T16:49:45.941Z",
    "updatedAt": "2023-01-17T16:51:57.067Z"
}
```
## Deleção de categorias

`DELETE /categories/id - FORMATO DE RESPOSTA - 204`
<P>Exemplo de resposta</p>

```json
```

# Produtos

## Criação de um produto

`POST /products - FORMATO DE REQUISIÇÃO`
<P>Exemplo de requisição</p>

```json
{
	"name": "Coca Cola 2",
	"category": "Bebidas",
	"price": "2.99",
	"in_stock": true
}
```

`POST /products - FORMATO DE RESPOSTA - Status Code - 401`
<P>Exemplo de resposta</p>

```json
{
    "name": "Coca Cola 2",
    "price": "2.99",
    "in_stock": true,
    "category": {
        "id": "d8cfb040-1f09-4f4e-b8cd-8200f54fef91",
        "name": "Bebidas",
        "createdAt": "2023-01-17T16:55:37.311Z",
        "updatedAt": "2023-01-17T16:55:37.311Z"
    },
    "deletedAt": null,
    "id": "7312d555-86aa-4a97-b7d4-24faac49add3",
    "createdAt": "2023-01-17T17:03:43.903Z",
    "updatedAt": "2023-01-17T17:03:43.903Z"
}
```

## Atualização de um produto

`PATCH /products/id - FORMATO DE REQUISIÇÃO`
<P>Exemplo de requisição</p>

```json
{
	"name":"Refrigerante atualizado"
}
```

`PATCH /products/id - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
{
    "id": "7312d555-86aa-4a97-b7d4-24faac49add3",
    "name": "Refrigerante atualizado",
    "price": "2.99",
    "in_stock": true,
    "createdAt": "2023-01-17T17:03:43.903Z",
    "updatedAt": "2023-01-17T17:06:06.755Z",
    "deletedAt": null,
    "category": {
        "id": "d8cfb040-1f09-4f4e-b8cd-8200f54fef91",
        "name": "Bebidas",
        "createdAt": "2023-01-17T16:55:37.311Z",
        "updatedAt": "2023-01-17T16:55:37.311Z"
    }
}
```

## Deleção de um produto

`DELETE /products/id - FORMATO DE RESPOSTA - Status Code - 204`
<P>Exemplo de resposta</p>

```json
```

# Mesas

## Criação de uma mesa

`POST /tables - FORMATO DE REQUISIÇÃO`
<P>Exemplo de requisição</p>

```json
{
	"seats": 10,
	"isActive": true,
	"table_number": 22
}
```

`POST /tables - FORMATO DE RESPOSTA - Status Code - 401`
<P>Exemplo de resposta</p>

```json
{
    "seats": 10,
    "isActive": false,
    "table_number": 22,
    "id": "e830c64b-43df-47dd-bd85-b9ce15270b7a",
    "createdAt": "2023-01-17T17:18:03.279Z",
    "updatedAt": "2023-01-17T17:18:03.279Z"
}
```

## Atualização de uma mesa

`PATCH /tables/id - FORMATO DE REQUISIÇÃO`
<P>Exemplo de requisição</p>

```json
{
	"table_number": 25
}
```
`PATCH /tables/id - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
{
    "id": "e830c64b-43df-47dd-bd85-b9ce15270b7a",
    "seats": 10,
    "isActive": false,
    "table_number": 25,
    "createdAt": "2023-01-17T17:18:03.279Z",
    "updatedAt": "2023-01-17T17:24:12.231Z"
}
```

## Deleção de uma mesa

`DELETE /tables/id - FORMATO DE RESPOSTA - Status Code - 204`
<P>Exemplo de resposta</p>

```json
```

# Funcionalidades do funcionário

# Mesas

## Listar mesas

`GET /tables - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
[
    {
        "id": "e830c64b-43df-47dd-bd85-b9ce15270b7a",
        "seats": 10,
        "isActive": false,
        "table_number": 22,
        "createdAt": "2023-01-17T17:18:03.279Z",
        "updatedAt": "2023-01-17T17:18:03.279Z"
    }
]
```

## Listar mesa específica

`GET /tables - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
{
    "id": "e830c64b-43df-47dd-bd85-b9ce15270b7a",
    "seats": 10,
    "isActive": false,
    "table_number": 22,
    "createdAt": "2023-01-17T17:18:03.279Z",
    "updatedAt": "2023-01-17T17:18:03.279Z"
}
```

## Listar pedidos de uma mesa

`GET /tables/id/orders - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
{
    "orders": [],
    "table_number": 22,
    "isActive": false,
    "seats": 10,
    "id": "e830c64b-43df-47dd-bd85-b9ce15270b7a"
}
```

# Produtos

## Listar produtos

`GET /products - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
[
    {
        "id": "7312d555-86aa-4a97-b7d4-24faac49add3",
        "name": "Coca Cola 2",
        "price": "2.99",
        "in_stock": true,
        "createdAt": "2023-01-17T17:03:43.903Z",
        "updatedAt": "2023-01-17T17:03:43.903Z",
        "deletedAt": null,
        "category": {
            "id": "d8cfb040-1f09-4f4e-b8cd-8200f54fef91",
            "name": "Bebidas",
            "createdAt": "2023-01-17T16:55:37.311Z",
            "updatedAt": "2023-01-17T16:55:37.311Z"
        }
    }
]
```

## Listar produto específico

`GET /products/id - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
{
    "id": "7312d555-86aa-4a97-b7d4-24faac49add3",
    "name": "Coca Cola 2",
    "price": "2.99",
    "in_stock": true,
    "createdAt": "2023-01-17T17:03:43.903Z",
    "updatedAt": "2023-01-17T17:03:43.903Z",
    "deletedAt": null,
    "category": {
        "id": "d8cfb040-1f09-4f4e-b8cd-8200f54fef91",
        "name": "Bebidas",
        "createdAt": "2023-01-17T16:55:37.311Z",
        "updatedAt": "2023-01-17T16:55:37.311Z"
    }
}
```

# Pedidos

## Criar pedidos

`POST /orders - FORMATO DE REQUISIÇÃO`
<P>Exemplo de requisição</p>

```json
{
	"table_id":"e830c64b-43df-47dd-bd85-b9ce15270b7a",
	"user_id":"ecd036d0-9d13-4213-97c3-e2187c9e8e6f",
	"client_name": "cliente_1",
	"products": [{
		"id": "7312d555-86aa-4a97-b7d4-24faac49add3"	
	}]
}
```

`POST /orders - FORMATO DE RESPOSTA - Status Code - 401`
<P>Exemplo de resposta</p>

```json
{
    "products": [
        {
            "category": {
                "name": "Bebidas",
                "id": "d8cfb040-1f09-4f4e-b8cd-8200f54fef91"
            },
            "in_stock": true,
            "price": "2.99",
            "name": "Refrigerante atualizado",
            "id": "7312d555-86aa-4a97-b7d4-24faac49add3"
        }
    ],
    "table": {
        "table_number": 25,
        "isActive": false,
        "seats": 10,
        "id": "e830c64b-43df-47dd-bd85-b9ce15270b7a"
    },
    "user": {
        "isAdm": true,
        "username": "exampleReq",
        "id": "ecd036d0-9d13-4213-97c3-e2187c9e8e6f",
        "name": "Teste"
    },
    "client_name": "cliente_1",
    "id": "3ef50d63-2c9b-4d32-9550-b89a6d0fc576"
}
```

## Listar todos os pedidos

`GET /orders - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
[
    {
        "productsToOrder": [
            {
                "product": {
                    "category": {
                        "name": "Bebidas",
                        "id": "d8cfb040-1f09-4f4e-b8cd-8200f54fef91"
                    },
                    "in_stock": true,
                    "price": "2.99",
                    "name": "Refrigerante atualizado",
                    "id": "7312d555-86aa-4a97-b7d4-24faac49add3"
                },
                "id": "8facf584-f93a-46fc-a722-c5ef16de3b03"
            },
            {
                "id": "63fe4cd6-7075-4a10-8ab5-c2923f4b2811",
                "product": null
            }
        ],
        "user": {
            "isAdm": true,
            "username": "exampleReq",
            "name": "Teste",
            "id": "ecd036d0-9d13-4213-97c3-e2187c9e8e6f"
        },
        "tabe": {},
        "client_name": "cliente_1",
        "id": "3ef50d63-2c9b-4d32-9550-b89a6d0fc576"
    },
    {
        "productsToOrder": [
            {
                "id": "614bcfe2-f1f6-4dd7-9eab-a8141d6b70f7",
                "product": null
            },
            {
                "id": "a2751b25-506a-43bc-b079-4a8f0a6fd33a",
                "product": null
            }
        ],
        "user": {
            "isAdm": true,
            "username": "exampleReq",
            "name": "Teste",
            "id": "ecd036d0-9d13-4213-97c3-e2187c9e8e6f"
        },
        "tabe": {},
        "client_name": "cliente_1",
        "id": "bc5f4f55-f31c-4004-84bd-0b211b944518"
    }
]
```

## Listar todos os pedidos fechados

`GET /orders - FORMATO DE RESPOSTA - Status Code - 200`
<P>Exemplo de resposta</p>

```json
{
    "id": "3ef50d63-2c9b-4d32-9550-b89a6d0fc576",
    "client_name": "cliente_1",
    "createdAt": "2023-01-17T21:39:48.033Z",
    "deletedAt": "2023-01-17T21:44:30.428Z",
    "table": {
        "id": "e830c64b-43df-47dd-bd85-b9ce15270b7a",
        "seats": 10,
        "isActive": false,
        "table_number": 25,
        "createdAt": "2023-01-17T17:18:03.279Z",
        "updatedAt": "2023-01-17T17:24:12.231Z"
    },
    "user": {
        "id": "ecd036d0-9d13-4213-97c3-e2187c9e8e6f",
        "name": "Teste",
        "username": "exampleReq",
        "isAdm": true,
        "createdAt": "2023-01-17T16:45:03.487Z",
        "updatedAt": "2023-01-17T16:45:03.487Z",
        "deletedAt": null
    },
    "products": [
        {
            "id": "8facf584-f93a-46fc-a722-c5ef16de3b03",
            "product": {
                "id": "7312d555-86aa-4a97-b7d4-24faac49add3",
                "name": "Refrigerante atualizado",
                "price": "2.99",
                "in_stock": true,
                "createdAt": "2023-01-17T17:03:43.903Z",
                "updatedAt": "2023-01-17T17:06:06.755Z",
                "deletedAt": null,
                "category": {
                    "id": "d8cfb040-1f09-4f4e-b8cd-8200f54fef91",
                    "name": "Bebidas",
                    "createdAt": "2023-01-17T16:55:37.311Z",
                    "updatedAt": "2023-01-17T16:55:37.311Z"
                }
            }
        },
        {
            "id": "63fe4cd6-7075-4a10-8ab5-c2923f4b2811",
            "product": null
        }
    ]
}
```

## Deletar pedidos

`DELETE /orders/id - FORMATO DE RESPOSTA - Status Code - 204`
<P>Exemplo de resposta</p>
```json
```





