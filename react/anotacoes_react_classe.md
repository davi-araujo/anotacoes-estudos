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

#### Alterando o valor do estado (state)

A classe `Component` disponibiliza o método `setState` para ser feita a troca do valor do estado. A seguir é possível ver este método sendo utilizado:

```javascript
class App extends Component {
    state = {
        counter: 0
    };

    addCounter = (event) => {
        this.setState({ counter: 2 });
    };

    //resto do componente
}
```

O método `setState` pode receber como segundo parâmetro uma função de callback para acessar os dados do `state` logo após a alteração.

- **nota:** sempre que o `state` altera, o método `render()` é recarregado.

#### Métodos de ciclo de vida

A classe `Component` conta com métodos que controlam o ciclo de vida de um componente. Abaixo há o exemplo de alguns desses métodos (para ver todos, basta buscar por "lifecycle methods"):

- `componentDidMount()`: o método é executado quando o componente é montado;
- `componentDidUpdate()`: o método é executado quando o componente atualiza;
- `componentWillUnmount()`: o método é executado quando o componente é desmontado.