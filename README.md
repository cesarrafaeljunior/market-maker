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

## Criação de usuários

`Post /users - FORMATO DA RESPOSTA - STATUS 200`

```json
  #Exemplo de requisição
{
	"username": "exampleReq",
	"name": "Teste", 
	"password": "1234",
	"isAdm": true
}
```




