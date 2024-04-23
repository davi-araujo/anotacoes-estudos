- [Voltar ao início](../README.md)

### PROMISE

Uma classe `promise` tem como objetivo de construir funções para processamento assíncrono de um valor não necessariamente conhecido. 

A classe recebe uma função como parâmetro, que por sua vez recebe duas funções:

- `resolve`: cria uma promise resolvida;
- `reject`: cria uma promisse rejeitada.

A classe ainda conta com dois métodos:

- `.then`: define o bloco a ser executado a partir de um `resolve`;
- `.catch`: define o bloco a ser executado a partir de um `reject`.

É importante clarificar que o método `.then` sempre espera um `resolve` para que o bloco definido execute, da mesma forma que o método `.catch` sempre espera um `reject` para executar seu bloco.

Exemplo: 

```javascript
const getUserById = (id) => {
    return new Promise ((resolve, reject) => {
        if (typeof id !== 'number') {
            reject('Id inválido');
            return
        }

        //função para encontrar o usuário de acordo com o id

        resolve(usuario);
    });
}

getUserById(32)
    .then(usuario => console.log(usuario))
    .catch(error => console.log(error));

getUserById('81')
    .then(usuario => console.log(usuario))
    .catch(error => console.log(error));
```

```terminal
{ id: 32, nome: Davi }
Id inválido
```

#### Outros métodos

- `Promise.all`: retorna todas as `promises` de uma lista resolvidas. Se algum der erro, retorna apenas o erro.

```javascript
const usuarios = [
    getUserById(53),
    getUserById(15),
    getUserById(86)
]

Promise.all(usuarios)
    .then(lista => console.log(lista))
    .catch(error => console.log(error));
```

```terminal
[
    { id: 53, nome: Lucas },
    { id: 15, nome: Maria },
    { id: 86, nome: Guilherme }
]
```

- `Promise.race`: retorna a primeira `promises` que for resolvida, seja `resolve` ou `reject`. Muito utilizada quando tem tempo de execução envolvido.

- `Promise.resolve`: retorna uma `promises` resolvida.

- `Promise.reject`: retorna uma `promises` rejeitada.

### ASYNC e AWAIT

Uma outra forma possível de tratar com funções assíncronas são as palavras-chave `async` e `await`. Sua funcionalidade é bem similar à de `promise` com `.then` e `.catch`. Veja: 

```javascript
const getUserById = (id) => {
    return new Promise ((resolve, reject) => {
        if (typeof id !== 'number') {
            reject('Id inválido');
            return
        }

        //função para encontrar o usuário de acordo com o id

        resolve(usuario);
    });
}

async function trocaNome() {
    try {
        const usuario = await getUserById(53);
        usuario.nome = 'Lucas';
        console.log(usuario);
    } catch (error) {
        console.log('Tivemos problema para encontrar o usuário')
    }
}

trocaNome();
```

```terminal
{ id: 53, nome: Lucas }
```

- obs: Pela falta do `.catch`, é interessante que se utilize o `try catch` para cobrir a possibilidade da `promise` retornar `reject`.

### FETCH

O uso do `fetch()` fornece uma forma fácil e lógica de buscar recursos de forma assíncrona através da rede. Por padrão o `fetch()` retorna uma `promise`. É importante salientar que a `promise` não faz a tratativa de erro do HTTP.

#### RESPONSE

O objeto `Response` é retornado como resposta do `promise` retornado pelo `fetch()`. Sua estrutura está descrita na imagem a seguir, juntamente com a descrição das principais propriedades: 

![Estrutura do objeto Response](./images/estrutura-response.png "Estrutura do objeto Response")

- `Resonse.ok`: Valor booleano que indica se a `Response` obteve sucesso (status entre 200-299) ou não;

- `Response.status`: Status code da `Response`;

- `Response.statusText`: Mensagem correspondente ao status code.

Além disso, o objeto `Response` também possui métodos que podem auxiliar bastante na hora de tratar os dados retornados pelo `fetch()`. A seguir estão listados os 2 principais: 

- `.json()`: Retorna uma `promise` que se resolve retornando `Response.body` no formato JSON;

- `.text()`: Retorna uma `promise` que se resolve retornando `Response.body` no formato de string.

Veja um exemplo do uso de `fetch()` a seguir:

```javascript
fetch('usuarios.json')
    .then(response => {
        if (response.ok === false) throw new Error('Problemas para encontrar o usuário');
        return response.json();
    })
    .then(json => {
        json.foreach(usuario => {
            console.log(usuario.nome)
        });
    })
    .catch(e => console.error(e));
```

```terminal
Lucas
Davi
Caio
```