### DOM

- `document.body.innerHTML = '...'`: Adiciona partes do HTML ao documento.
    
    - Caso queira manter o que já está escrito, deve-se usar **+=**.
    - Pode-se fazer direto dentro de alguma outra tag já importada. Ex: `p.innerHTML`

- `document.querySelector('.nome-da-classe')`: seleciona uma tag a partir do nome da classe para manipulá-la pelo javascript.
- `form.addEventListener('evento', função)`: executa uma função sempre que o evento acontecer. Exemplos:

```javascript
form.addEventListener('submit', (evento) => {
    evento.preventDefault();   //evita que a página fique atualizando ao clicar no botão
    ...
});

button.addEventListener('click', () => {
    ...
});
```

- É possível criar elementos HTML, adicionar classes e jogá-los dentro do documento HTML. No exemplo, será criado uma tag `<p>`:

```javascript
const p = document.createElement('p');   // cria o elemento
p.innerHTML = '...';                     // adiciona texto no elemento
p.classList.add('...');                  // adiciona uma classe ao elemento
form.appendChild(p);                     // adiciona o elemento dentro do 'form'
```

- NodeList
    
    - `form.querySelectorAll('p')`: etorna todas as tags `<p>` dentro do *form* em formato de NodeList, que é iterável como uma array.

- Style

    - É possível manipular o estilo da tag pelo javascript. 
    - `getComputedStyle(form)`: retorna o estilo do *form*
    - `form.style.backgroundColor`: retorna a cor de fundo do *form*. Serve para qualquer atributo do CSS.