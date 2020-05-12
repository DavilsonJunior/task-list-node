<h1 align="center">
    <img alt="image" src="https://user-images.githubusercontent.com/6686410/31217465-6adbbd18-a98d-11e7-9371-26d578182e9d.png" width="150px" />
    <img alt="image" src="https://upload.wikimedia.org/wikipedia/commons/d/d9/Node.js_logo.svg" width="150px" />
</h1>

<h3 align="center">
  Criando uma lista de tarefas com node
</h3>

### Primeiro vamos instalar os pacotes para uso da aplicação

- Iniciaremos um package.json
```package
yarn init -y
```

- instalando express
```package
yarn add express
```

- instalando nodemon para atualizar as alterações automaticamente
```package
yarn add nodemon
```

### Configuracões
- abra o arquivo package.json e adicione essa linha, assim podera iniciar o servidor com `yarn dev`
```json
"scripts": {
    "dev": "nodemon index.js"
  }
```

### Rotas

- `POST /projects`: A rota deve receber `id` e `title` dentro do corpo e cadastrar um novo projeto dentro de um array no seguinte formato: `{ id: "1", title: 'Novo projeto', tasks: [] }`; Certifique-se de enviar tanto o ID quanto o título do projeto no formato string com aspas duplas.

- `GET /projects`: Rota que lista todos projetos e suas tarefas;

- `PUT /projects/:id`: A rota deve alterar apenas o título do projeto com o `id` presente nos parâmetros da rota;

- `DELETE /projects/:id`: A rota deve deletar o projeto com o `id` presente nos parâmetros da rota;

- `POST /projects/:id/tasks`: A rota deve receber um campo `title` e armazenar uma nova tarefa no array de tarefas de um projeto específico escolhido através do `id` presente nos parâmetros da rota;

### Exemplo

Se eu chamar a rota `POST /projects` repassando `{ id: 1, title: 'Novo projeto' }` e a rota `POST /projects/1/tasks` com `{ title: 'Nova tarefa' }`, meu array de projetos deve ficar assim:

```js
[
  {
    id: "1",
    title: "Novo projeto",
    tasks: ["Nova tarefa"]
  }
];
```
