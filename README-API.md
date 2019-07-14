# API Challenge

## Users

### Create

Creates user.

`POST http://challenge.payparty.com.br/v1/users`

```
body: {
  name: Fulano da Silva,
  email: f.silva@domain.com,
  password: 1234
}
```

## Reponse

```
  201 - Criado com sucesso
  400 - Erro na validação do conteúdo do body
  500 - Algum erro desconhecido do servidor
```

### Auth

Authenticates user.

`POST http://challenge.payparty.com.br/v1/users/auth`

```
body: {
  email: f.silva@domain.com,
  password: 1234
}
```

## Reponse

```
  200 - Autenticado com sucesso
  400 - Erro na validação do conteúdo do body
  401 - Usuário/Senha incorretos
  500 - Algum erro desconhecido do servidor
```

## To-Do

### Create

Creates to-do item.

`POST http://challenge.payparty.com.br/v1/users/:user/todo`

```
headers: {
  Authorization: Bearer <JWT Token>
}
params: {
  user: ObjectId
},
body: {
  value: String
}
```

## Reponse

```
  201 - Criado com sucesso
  400 - Erro na validação do conteúdo do body
  401 - Usuário com o token inválido
  500 - Algum erro desconhecido do servidor
```

### Update

Modifies to-do item.

`PUT http://challenge.payparty.com.br/v1/users/:user/todo/:todo`

```
headers: {
  Authorization: Bearer <JWT Token>
}
params: {
  user: ObjectId,
  todo: ObjectId
},
body: {
  value: String
}
```

## Reponse

```
  200 - Modificado com sucesso
  400 - Erro na validação do conteúdo do body
  401 - Usuário com o token inválido
  500 - Algum erro desconhecido do servidor
```

### Delete

Deletes to-do item.

`DELETE http://challenge.payparty.com.br/v1/users/:user/todo/:todo`

```
headers: {
  Authorization: Bearer <JWT Token>
}
params: {
  user: ObjectId,
  todo: ObjectId
}
```

## Reponse

```
  200 - Deletado com sucesso
  400 - Erro na validação do conteúdo do body
  401 - Usuário com o token inválido
  500 - Algum erro desconhecido do servidor
```

### Get by user

Gets all to-do items created by user.

`GET http://challenge.payparty.com.br/v1/users/:user/todo`

```
headers: {
  Authorization: Bearer <JWT Token>
}
params: {
  user: ObjectId
}
```

```
  200 - Dados carregados com sucesso
  400 - Erro na validação do conteúdo do body
  401 - Usuário com o token inválido
  500 - Algum erro desconhecido do servidor
```