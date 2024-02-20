Uma fake API para uma aplicação de e-commerce

## ROTAS

### Notícias /news GET

Padrão de resposta:

```json
[
   {
      "id": 1,
      "title": "Computador",
      "price": 2500,
      "description": "Lorem ipsum."
   },
   {
      "id": 2,
      "title": "Notebook",
      "price": 3500,
      "description": "Lorem ipsum."
   },
   {
      "id": 3,
      "title": "Mouse",
      "price": 3500,
      "description": "Lorem ipsum."
   }
]
```

### Produtos /products POST (Requer autorização)

Headers

```json
{
   "Authorization": "Bearer token"
}
```

Padrão de corpo

```json
{
   "title": "Computador",
   "price": 2500,
   "description": "Lorem ipsum."
}
```

Padrão de resposta

```json
{
   "id": 1,
   "title": "Computador",
   "price": 2500,
   "description": "Lorem ipsum."
}
```

### Produtos /products/:productId PATCH (Requer autorização)

Headers

```json
{
   "Authorization": "Bearer token"
}
```

Padrão de corpo

```json
{
   "title": "Computador",
   "price": 2500,
   "description": "Lorem ipsum."
}
```

Por se tratar de uma rota de patch nem todos as chaves são obrigatórias.

Padrão de resposta

```json
{
   "id": 1,
   "title": "Computador",
   "price": 2500,
   "description": "Lorem ipsum."
}
```

### Produtos /products/:productId DELETE (Requer autorização)

Headers

```json
{
   "Authorization": "Bearer token"
}
```

### Usuário (Cadastrar) /users POST

Padrão de corpo

```json
{
   "name": "John Doe",
   "email": "johndoe@email.com",
   "password": "123456"
}
```

Padrão de resposta

```json
{
   "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImpvaG5kb2VAZW1haWwuY29tIiwiaWF0IjoxNjgxMjI2MzU1LCJleHAiOjE2ODEyMjk5NTUsInN1YiI6IjIifQ.HoHzAjg6luV9k6v8zHyewSTHsUnAKDBIbFiIS0r_joM",
   "user": {
      "email": "johndoe@email.com",
      "name": "John Doe",
      "id": 1
   }
}
```

### Usuário (Login) /login POST

```json
{
   "email": "johndoe@email.com",
   "password": "123456"
}
```

Padrão de resposta

```json
{
   "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImpvaG5kb2VAZW1haWwuY29tIiwiaWF0IjoxNjgxMjI2MzU1LCJleHAiOjE2ODEyMjk5NTUsInN1YiI6IjIifQ.HoHzAjg6luV9k6v8zHyewSTHsUnAKDBIbFiIS0r_joM",
   "user": {
      "email": "johndoe@email.com",
      "name": "John Doe",
      "id": 1
   }
}
```

### Usuário (Autologin) /users/:userId GET (Precisa de autorização)

Headers

```json
{
   "Authorization": "Bearer token"
}
```

Padrão de resposta

```json
{
   "email": "johndoe@email.com",
   "name": "John Doe",
   "job": "Jornalista",
   "id": 1
}
```
