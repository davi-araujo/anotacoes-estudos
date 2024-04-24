- [Voltar ao início](../README.md)

### Componentes em formato de classe

O React trabalha com a possibilidade de criar componentes utilizando classes para ter acesso aos estados. A seguir está um exemplo de estrutura básica de um componente com classes: 

```javascript
class App extends Component {
    state = {
        counter: 0
    };

    addCounter = (event) => {
        // código do método
    };

    render () {
        const { counter } = this.state;

        return (
            // código JSX
        );
    }
}
```

#### Métodos de ciclo de vida

A classe `Component` conta com métodos que controlam o ciclo de vida de um componente. Abaixo há o exemplo de alguns desses métodos (para ver todos, basta buscar por "lifecycle methods"):

- `componentDidMount()`: o método é executado quando o componente é montado;
- `componentDidUpdate()`: o método é executado quando o componente atualiza;
- `componentWillUnmount()`: o método é executado quando o componente é desmontado.