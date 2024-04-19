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