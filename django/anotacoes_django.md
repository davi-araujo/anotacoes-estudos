- [Voltar ao início](../README.md)

### Iniciando o projeto

#### Ambiente virtual

- Para criar um ambiente virtual, basta digitar o seguinte código no terminal:

    ```console
    python -m venv venv
    ```

- Para ativar o ambiente virtual, basta digitar o seguinte código no terminal (para Windows):

    ```console
    venv\Scripts\activate
    ```

#### Instalando e rodando o projeto

- Para instalar o Django, basta digitar o seguinte código no terminal:

    ```console
    pip install django
    ```

- Para iniciar o projeto, basta digitar o seguinte código no terminal: 

    ```console
    django=admin startproject <nome_do_projeto> .
    ```

- Para rodar o projeto em um servidor de desenvolvimento, basta digitar o seguinte código no terminal:

    ```console
    python manage.py runserver
    ```

#### Estrutura inicial

- **.mypy_cache**: cache do plugin que analisa o código;
- **db.sqlite**: arquivo de base de dados utilizado no projeto (geralmente utilizado apenas para desenvolvimento);
- **manage.py**: tem a mesma funcionalidade do `django-admin` para dar comandos ao projeto;
- **settings.py**: arquivo de configuração do Django;
- **urls.py**: configura as URLs do projeto.

### URLs

Para criar uma URL, é necessário adicionar a chamada `path`, passando como parâmetro uma string que indica a rota de acesso e uma função view, que geralmente está organizada em pastas. Veja:

```python
urlpatterns = [
    path('admin/', admin.site.urls),
    path('<caminho_desejado>', função)
]
```

**obs**: A função passada deve receber como parâmetro uma *HTTP request* e retornar uma *HTTP response*.