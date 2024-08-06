# Criando-uma-Aplica-o-Simples-com-Node.js-e-Express

# 1. Instalação do Node.js e npm:
Certifique-se de ter o Node.js e o npm (Node Package Manager) instalados em seu sistema. Você pode baixá-los em https://nodejs.org/.

# Criação do Projeto:
Abra seu terminal e crie um novo diretório para o seu projeto:

mkdir minha-app-express

cd minha-app-express

# Inicialização do Projeto:
Inicialize um novo projeto npm:
npm init -y

# Instale o Express como dependência do seu projeto:
npm install express

# 2. Criação do Arquivo do Servidor
Crie um arquivo chamado index.js na raiz do seu projeto.

# 3. Código do Servidor

const express = require('express');

const app = express();

const port = 3000;

// Rota raiz
app.get('/', (req, res) => {
  res.send('Bem-vindo à minha aplicação Express!');
});

// Rota para uma página específica
app.get('/sobre', (req, res) => {
  res.send('Esta é a página sobre.');
});

// Rota para um recurso dinâmico (ex: usuário)
app.get('/usuarios/:id', (req, res) => {
  const userId = req.params.id;
  res.send(`Você está buscando o usuário com ID: ${userId}`);
});

// Iniciando o servidor
app.listen(port, () => {
  console.log(`Servidor rodando na porta ${port}`);
});


# 4. Explicação do Código:
Importar o Express: Importamos o módulo Express e criamos uma instância da aplicação.
Definir a Porta: Definimos a porta em que o servidor irá escutar.
Criar Rotas:
app.get('/'): Define uma rota GET para a raiz da aplicação.
app.get('/sobre'): Define uma rota GET para a página "sobre".
app.get('/usuarios/:id'): Define uma rota GET para um recurso dinâmico "usuários", onde :id é um parâmetro de rota.
Enviar Respostas:
res.send(): Envia uma resposta para o cliente.
Iniciar o Servidor: Inicia o servidor e escuta na porta especificada.


# 5. Executar a Aplicação
No seu terminal, execute o seguinte comando:
node index.js

# Agora, você pode acessar sua aplicação no navegador digitando: 
http://localhost:3000 para a página inicial
http://localhost:3000/sobre para a página sobre
http://localhost:3000/usuarios/1 para buscar um usuário com ID 1.
