

# Simple To-Do App

Este é um aplicativo simples de gerenciamento de tarefas (to-do list) criado com Node.js e HTML/CSS. O objetivo deste projeto é praticar conceitos básicos de desenvolvimento web.

## Como iniciar o projeto

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu_usuario/simple-todo-app.git
   cd simple-todo-app
Instale as dependências:

bash
Copiar código
npm install
Inicie o servidor:

bash
node server/index.js
Acesse o aplicativo em http://localhost:3000.

java


#### 2.2. **package.json**
Crie um arquivo `package.json` na raiz do projeto:

```json
{
  "name": "simple-todo-app",
  "version": "1.0.0",
  "description": "A simple to-do list application",
  "main": "server/index.js",
  "scripts": {
    "start": "node server/index.js"
  },
  "dependencies": {
    "express": "^4.18.2"
  }
}
````
2.3. .gitignore
Crie um arquivo .gitignore e adicione o seguinte conteúdo:

node_modules/
2.4. client/index.html
Crie o arquivo index.html dentro da pasta client/:

html
```<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <input type="text" id="taskInput" placeholder="Adicione uma nova tarefa">
        <button id="addTaskButton">Adicionar Tarefa</button>
        <ul id="taskList"></ul>
    </div>
    <script>
        document.getElementById('addTaskButton').onclick = function() {
            const taskInput = document.getElementById('taskInput');
            const taskText = taskInput.value;
            if (taskText) {
                const li = document.createElement('li');
                li.textContent = taskText;
                document.getElementById('taskList').appendChild(li);
                taskInput.value = '';
            }
        };
    </script>
</body>
</html>
```
```2.5. client/styles.css
Crie o arquivo styles.css na pasta client/:``````

```css```
```body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    color: #333;
}

.container {
    width: 400px;
    margin: 50px auto;
    padding: 20px;
    background: white;
    border-radius: 5px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

h1 {
    text-align: center;
}

input[type="text"] {
    width: 75%;
    padding: 10px;
    margin-right: 5px;
}

button {
    padding: 10px;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    padding: 10px;
    border-bottom: 1px solid #eee;
}

``````
``````2.6. server/index.js

`````` Crie o arquivo index.js dentro da pasta server/:

javascript``````
const express = require('express');
const path = require('path');
const app = express();
const PORT = 3000;

app.use(express.static(path.join(__dirname, '../client')));
app.use(express.json());

app.listen(PORT, () => {
    console.log(`Servidor rodando em http://localhost:${PORT}`);
});
3. Instalação de Dependências
Abra o terminal na raiz do projeto.
Execute o seguinte comando para instalar o Express:
bash
``````
npm install
4. Subir o Projeto para o GitHub
Após a configuração do projeto, você pode subir as alterações para o GitHub:

bash
git add .
git commit -m "Initial commit"
git push origin main
5. Executar o Projeto
Para iniciar o servidor, use o comando:
bash
npm start
Abra seu navegador e acesse http://localhost:3000 para ver o aplicativo em funcionamento.
