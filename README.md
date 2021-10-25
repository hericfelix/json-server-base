# BookListAPI

==========================

API que possui uma listagem dos 100 melhores livros clássicos de todos os tempos, e que o usuário pode listar seus livros já lidos.

## Endpoints

==========================

A aplicação possui um total de 4 endpoints:

### Cadastro

==========================

`POST /register`

Endpoint de cadastro de novos usuários. A requisição deverá ser feita com o e-mail e o login no corpo.

```json
{
  "email": "teste@teste.com",
  "password": "teste123"
}
```

Caso tudo dê certo a resposta será assim:

`POST /register - STATUS 201`

```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXJAbWFpbC5jb20iLCJpYXQiOjE2MzUxODUwMjgsImV4cCI6MTYzNTE4ODYyOCwic3ViIjoiMyJ9.OOGgjbYHjAQ1AliVW39IY9_s4HpdxOlt4hEojm_fXYA",
  "user": {
    "email": "teste@teste.com",
    "id": 3
  }
}
```

### Login

==========================

`POST /login`

Endpoint de login de usuários já criados. A requisição deverá ser feita com o e-mail e o login no corpo.

```json
{
  "email": "teste@teste.com",
  "password": "teste123"
}
```

Caso tudo dê certo a resposta será assim:

`POST /login - STATUS 201`

```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXJAbWFpbC5jb20iLCJpYXQiOjE2MzUxODUwMjgsImV4cCI6MTYzNTE4ODYyOCwic3ViIjoiMyJ9.OOGgjbYHjAQ1AliVW39IY9_s4HpdxOlt4hEojm_fXYA",
  "user": {
    "email": "teste@teste.com",
    "id": 3
  }
}
```

### Book List

==========================

`GET /book_list`

Endpoint utilizada para acessar a listagem dos 100 melhores livros clássicos.

`GET /book_list - STATUS 200`

```json
{
  "email": "teste@teste.com",
  "password": "teste123"
}
```

### Read Books

==========================

`POST /read_books`

Conseguimos realizar o cadastro de livros já lidos pelo usuário com esse endpoint. É necessário o envio do id do usuário para que a requisição seja aceita.

```json
{
  "title": "Harry Potter e a Pedra Filosofal",
  "author": "J. K. Rowling",
  "userId": 3
}
```

É necessário o envio do token no cabeçalho da requisição, dessa forma:

> Authorization: Bearer {token}

`get /read_books`

Com esse endpoint podemos verificar todos os livros já lidos pelos usuários.

`get /read_books - STATUS 200`

```json
[
  {
    "title": "Harry Potter e a Pedra Filosofal",
    "author": "J. K. Rowling",
    "userId": 3,
    "id": 1
  }
]
```
