### Objeto Number

- `.toString()`: retorna o valor como string.
- `.toString(2)`: retorna a representação em binário.
- `.toFixed(x)`: arredonda o número para x casas decimais.
- `Number.isInteger(x)`: verifica se x é inteiro e retorna boolean.
- `Number.isNaN(x)`: verifica se x é NaN e retorna boolean.

- Há várias outras funções do objeto.

### Objeto Math

- `Math.floor(x)`: arredonda x para baixo (inteiro).
- `Math.ceil(x)`: arredonda x para cima (inteiro).
- `Math.round(x)`: arredonda x para o inteiro mais próximo.
- `Math.max(...)` ou `Math.min(...)`: retorna o maior ou o menor número da sequência, respectivamente.

- Há várias outras funções do objeto.

### Objeto Date

- Responsável por retornar a hora exata em que o código é rodado.
```javascript
const data = new Date();

//com parametros (ano e mes obrigatórios)
const data = new Date(ano, mes-1, dia, hora, min, seg);

//outra opção
const data = new Date('ano-mes-dia hora:min:seg.ml');;
```

- Extraindo informações a partir de uma data:
    - `data.getDate()`: retorna o dia.
    - `data.getMonth()`: retorna o mês.
    - `data.getFullYear()`: retorna o ano.
    - `data.getHours()`: retorna a hora.
    - `data.getMinutes()`: retorna os minutos.
    - `data.getSeconds()`: retorna os segundos.
    - `data.getMilliseconds()`: retorna os milisegundos.
    - `data.getDay()`: retorna o dia da semana.
        - 0 -> domingo.
        - 6 -> sábado.

- Recebendo somente o horário:

```javascript
data.toLocaleTimeString('pt-BR', {
    hour12: false,       // retira o AM e PM
    hour: '2-digit',     // dois dígitos sempre na hora
    minute: '2-digit',   // dois dígitos sempre nos minutos
    second: '2-digit',   // dois dígitos sempre nos segundos
});
```

- Há várias outras funções do objeto.