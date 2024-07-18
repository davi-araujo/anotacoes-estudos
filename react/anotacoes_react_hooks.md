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