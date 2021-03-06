## 🎯 Sobre

Cadastre usuários, alugue  e devolva filmes nessa api de locadora.


## 🚀 Tecnologias

- Sequelize
- Node js
- Express
- Jest
- PostgreSQL

## ✅ Requisitos

Antes de iniciar, você precisa ter [Git](https://git-scm.com), [Node](https://nodejs.org/en/) e [PostgreSQL](https://www.postgresql.org/) instalados.

## Iniciando o projeto
```bash
$ git clone https://github.com/Lukenoutte/locadora-api.git
```

### 

```bash
$ cd locadora-api
$ npm install
```
* Entre no diretorio **_locadora-api/src/config_** no arquivo __"database.js"__ altere os campos __username e password__, colocando os dados usados na instalação do PostgreSQL.

## Banco de dados

```bash
$ npm sequelize db:create     # Crie o banco de dados.
$ npm sequelize db:migrate    # Crie as tabelas.
$ npm sequelize db:seed:all   # Alimente banco de dados com dados falsos.
```

```bash
$ npm start
# The server will initialize in the <http://localhost:3333
```
## 📃 Como usar?

❗ Para rotas que necessitam de login, use o __token__ gerado ao autenticar na rota "/users/login"  em um campo no header chamado __"autorization"__ com o a palavra __Bearer__ antecedendo.
```bash
Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxjE0OTYxMjA1LCJleHAiOjE2MTUwNDc2MDV9
```
##  Criar novo usuário

Rota: /users <br />
Método: POST <br />
Requisitos: name, email, password

```bash
{
	"name": "Maria Santos",
	"email": "maria6@hotmail.com",
	"password": "1234"
}
```

##  Login


Rota: /users/login <br />
Método: POST <br />
Requisitos: email, password

```bash
{
	"email": "maria6@hotmail.com",
	"password": "1234"
}
```


## Visualizar filmes disponiveis


Rota: /movies <br />
Método: GET <br />

##  Pesquisar filme pelo nome


Rota: /movies/search <br />
Método: POST <br />
Requisitos: title

```bash
{
"title": "Matrix"
}
```

##  Cadastrar um filme


Rota: /movies <br />
Método: POST <br />
Requisitos: title, director, quantity <br />
❗ __Login Obrigatório__ 

```bash
{
	"title": "Matrix",
	"director": "The Wachowski Brothers",
	"quantity": "2"
}
```

##  Alugar um filme


Rota: /rents <br />
Método: POST <br />
Requisitos: user_id, movie_id <br />
❗ __Login Obrigatório__ 

```bash
{
	"user_id": 1,
	"movie_id": 1
}
```

##  Devolver  filme


Rota: /rents/give-back <br />
Método: POST <br />
Requisitos: rent_id <br />
❗ __Login Obrigatório__ 

```bash
{
	"rent_id": 4
}
```

## 🔧 Tests

```bash
$ npm test
```
