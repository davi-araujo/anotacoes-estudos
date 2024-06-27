- [Voltar ao início](../README.md)

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