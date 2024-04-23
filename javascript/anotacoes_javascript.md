- [Voltar ao início](../README.md)

### Operações matemáticas

- **Raiz Quadrada de x**: x ** 1/2. 

### Laço **while** e **do while**

- `while (condição) {...}`: verifica a condição e depois executa o código.
- `do {...} while (condição)`: executa o código e depois verifica a confição.

- **break**: quebra o laço.
- **continue**: passa para a próxima iteração.

### Laço **for**

- `for (i = 0; i < 3; i++) {...}`

- **break**: quebra o laço.
- **continue**: passa para a próxima iteração.

#### For in

- `for (i in vetor){...}`: i retorna as posições dentro do vetor

#### For of

- `for (i of vetor){...}`: i retorna os valores dentro do vetor

#### forEach

- `array.forEach((valor, indice, array) => {...})`: i retorna as posições dentro do vetor
    - **valor**: corresponde aos valores dentro do array.
    - **indice**: corresponde aos índices dentro do array.
    - **array**: corresponde ao array completo.

### Operadores ternários

- **if else**: `x = (condição) ? <valor verdadeiro> : <valor falso>`

- **ou**: `x = idade || 'não inserida'`
    - neste caso, se o valor booleano de `idade` for *false*, a variável **x** receberá `'não inserida'`.

### String

- `.charAt(x)`: retorna o valor na posição **x** e retorna string vazia se estiver fora do range.
- `.indexOf('x')`: retorna a primeira posição do caractere **x**. Retorna **-1** se não encontrar.
- `lastIndexOf('x')`: similar ao `.indexOf('x')`, porém inicia a busca no final da string.
- `.replace('x', 'y')`: substitui a primeira aparição de x por y.
    - para que todas as aparições de **x** sejam substituídas, deve-se colocar `/x/g`.
    - entre barras, pode-se utilizar ReGex.
- `.length`: retorna o tamanho da string.
- `.slice(x, y+1)`: retorna a string fatiada de **x** a **y**.
- `.split(' ')`: separa a string por espaços dentro de um array e a retorna.
    - o caracter a ser separado pode ser qualquer um. Ex: `.split('a')` vai separar a string sempre que achar um 'a' sem o incluir.
- `.toUpperCase()` ou `toLowerCase()`: coloca a string toda em maiúsculo ou minúsculo, respectivamente.

- Há várias outras funções relacionadas a strings.

### Array

- `.push(x)`: adiciona x ao final da array.
- `.unshift(x)`: adiciona x no começo da array.
- `.pop()`: remove e retorna o último elemento da array.
- `.shift()`: remove e retorna o primeiro elemento da array.
- `.splice(x, 1)`: remove e retorna o elemento da posição x da array.
- `.slice(x, y+1)`: retorna a array fatiada de **x** a **y**.

- **rest operator**

```javascript
const numeros = [1, 2, 3, 4, 5, 6, 7];
const [primeiro, segundo, ...resto] = numeros;
const [um, , tres, , cinco, , sete] = numeros;

console.log(primeiro, segundo, resto);
console.log(um, tres, cinco, sete);
```

```terminal
1 2 [ 3, 4, 5, 6, 7 ]
1 3 5 7
```

- Há várias ouras funções relacionadas a arrays.

### Função

- Declaração:

```javascript
//Declarações tradicionais
function nome (atributos) { //atributos opcionais
    ...
    return ...; //opcional
}


const nome = function (atributos) { //atributos opcionais
    ...
    return ...; //opcional
};

//Arrow function
const nome = (atributos) => { //atributos opcionais
    ...
    return ...; //opcional
};
```

### Objetos

- Exemplo de implementação:

```javascript
pessoa {
    nome: 'Davi',
    idade: 20,
    altura: 1.8
};
```

- Acessando dados de um objeto:

```javascript
console.log(pessoa.nome);
console.log(pessoa["idade"]);
```
```terminal
Davi
20
```

### Intervalos

- `setInterval(função, tempo (em ms))`: cria um intervalo que executará a função de acordo com o tempo, em ms.

- `setTimeout(função, tempo (em ms))`: a função será executada depois que o tempo, em ms, passar.

- `clearInterval(intervalo)`: quebra um intervalo que está sendo executado.

```javascript
timer = setInterval(() => {
    ...
}, 1000);

setTimeout(() => {
    ...
}, 1000);

clearInterval(timer);
```

### Erros

- Tratando erros: 

    - A função `try` tenta executar um código. Caso gere algum erro, o código vai ser direcionado ao `catch`, que recebe o erro e roda o código, podendo printar o erro para tratá-lo. A função `finally` roda o código presente independente se deu erro ou não.

```javascript
try {
    ...
} catch (erro) {
    ...
} finally {
    ...
}
```

- Lançando erros:

    - `thow new Error ('...')`: lança um erro completo no programa.