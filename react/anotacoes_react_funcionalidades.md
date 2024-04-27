- [Voltar ao início](../README.md)

### Paginação

A paginação consiste em apresnetar as informações para o usuário de maneira gradual, para que não seja necessário carregar todas as informações de uma vez, podendo, de acordo com a quantidade de dados, prejudicar a performance da aplicação. Para o entendimento será utilizado um exemplo de aplicação para apresentar usuários do sistema.

#### 1. Variáveis no estado

O primeiro passo para a implementação da funcionalidade é a inserção de algumas variáveis no estado da aplicação para o controle. Veja: 

```javascript
state = {
    users: [],        //usuários exibidos na página
    allUsers: [],     //todos os usuários
    usersPerPage: 6,  //quantidade de usuários por página
    usersOnPage: 6    //quantidade de usuários na página
};
```

Importante pontuar que os componentes devem carregar as informações presente do array `user`.

#### 2. Função para carregar novos dados

Para a função que carrega novos dados, a variável que mostra a quantidade de dados na página deve aumentar de acordo com a quantidade de dados por página, além de carregar nos novos dados que serão apresentados e inseri-los no estado. Veja o exemplo:

```javascript
loadMoreUsers = () => {
    const { usersOnPage, usersPerPage, allUsers } = this.state;

    let newUsersOnPage = usersOnPage + usersPerPage;
    const newUsers = allUsers.slice(0, newUsersOnPage);

    this.setState({ 
        usersOnPage: newUsersOnPage,
        users: newUsers
    });
};
```

#### 3. Chamando a função através de um botão

Por fim, basta chamar a função que carrega novos dados com o clique de um botão. Certifique-se de que, ao carregar todos os dados, este botão fique inativo, para não correr riscos de erro.