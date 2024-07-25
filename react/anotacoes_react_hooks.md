- [Voltar ao início](../README.md)

**IMPORTANTE**: Não se deve utilizar hooks dentro de loops, regras condicionais ou em funções dentro de funções, pois a ordem de chamada pode não respeitar o código. Caso o hook esteja atrelado a alguma condição ou repetição, utilize o laço ou bloco dentro do hook.

### useState

O hook `useState` serve para definir um estado no componente, similar ao que o `state` faz com componentes de classe. Veja a sua utilização:

```javascript
function App() {
    const [reverse, setReverse] = useState(<estado_inicial>);

    const handleClick = () => {
        setReverse(<alteração_do_estado>);
    }

    return (
        ...
    )
}
```

### useEffect

O hook `useEffect` trabalha com efeitos colaterais, similar aos _life cycle methods_, com a mudança de que é possível utilizar dependências para a execução do código. Veja sua utilização com comentários para ajudar no entendimento:

```javascript
function App() {
    const [reverse, setReverse] = useState(<estado_inicial>);

    //sempre que houver mudança de estado, o código será executado
    useEffect(() => {
        ...
    });

    //sempre que o componente carregar, o código será executado
    useEffect(() => {
        ...
    }, []);

    //sempre que houver mudança no estado reverse, o código será executado
    useEffect(() => {
        ...
    }, [reverse]);

    return (
        ...
    )
}
```

- O hook `useEffect` ainda pode ter uma função como *return* para executar assim que o componente é desmontado:

```javascript
function App() {
    const [reverse, setReverse] = useState(<estado_inicial>);

    useEffect(() => {
        ...

        //será executado quando o componente for desmontado
        return () => {
            ...
        }
    }, [reverse]);

    return (
        ...
    )
}
```

### useRef

O hook `useRef` cria uma referência a algum componente da página para substituir a função *document.querySelector* do JavaScript. Veja sua utilização: 

```javascript
function App() {
  const input = useRef(<estado_inicial>);

  return (
    <div className="App">
        <label>Insira seu nome</label>
        <input type='text' ref={input}/>
    </div>
  );
}
```

Da forma feita acima, a referência `input` aponta para a tag `<input />` por meio do parâmetro `ref`. É importante pontuar que, para acessar o input em si, deve-se utilizar o parâmetro `.current`.

### useContext

O hook `useContext` serve para passar um contexto entre componentes de forma mais fácil, facilitando a utilização de informações em diferentes componentes.

#### Criação do contexto

Para criar o contexto é necessário utilizar uma função padrão do React de criação, além de um objeto, variável ou etc para servir como o contexto propriamente dito. Veja: 

```javascript
const Context = React.createContext()

const loggedUser = {
  name: 'Davi Matias Araújo',
  age: 22,
  address: 'CNB 2 lote 5 apt 803'
}
```

#### Utilização do contexto

Para a utilização do contexto é utilizado o hook propriamente dito. Para acessar o contexto é utilizado uma tag do contexto. Veja: 

```javascript
function App() {
  return (
    <Context.Provider value={loggedUser}>
      ...
    </Context.Provider>
  );
}
```

Dentro da tag `<Context.Provider value={...}>` qualquer componente pode acessar o contexto da seguinte forma: 

```javascript
function UserCard() {
  const user = useContext(Context);

  return (
    ...
  )
}
```