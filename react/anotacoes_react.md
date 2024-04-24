- [Voltar ao início](../README.md)

### Criando um projeto

Para iniciar um projeto react é necessário ter o `Node` instalado e rodar o seguinte código no terminal: 

```terminal
npx create-react-app <pasta>
```

- **obs**: `<pasta>` diz respeito ao caminho até que chegue na pasta.

### Executando um projeto

Para executar o projeto é necessário rodar o seguinte código no terminal dentro da pasta do projeto: 

```terminal
npm start
```

### Prevenção de evento padrão do componente

Alguns componentes do JSX possuem eventos padrão (como por exemplo o `<a></a>`, que redireciona para outra página). Para prevenir tais eventos, é possível utilizar a função `.preventDefault()` no evento. O código abaixo exemplifica tal prevenção: 

```javascript
const addCounter = (event) => {
    event.preventDefault();
    // restante do código
}
```