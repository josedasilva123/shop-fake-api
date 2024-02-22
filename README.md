Uma fake API para uma aplicação de catálogo de produtos

## ROTAS

### Produtos /products GET

Padrão de resposta:

```json
[
   {
      "id": 1,
      "title": "Notebook",
      "price": 3500,
      "description": "Lorem ipsum.",
      "img": "https://images.pexels.com/photos/2528118/pexels-photo-2528118.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1",
      "userId": 1
   },
   {
      "id": 2,
      "title": "Mouse",
      "price": 3500,
      "description": "Lorem ipsum.",
      "img": "https://images.pexels.com/photos/301448/pexels-photo-301448.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1",
      "userId": 1
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
   "description": "Lorem ipsum.",
   "img": "https://images.pexels.com/photos/301448/pexels-photo-301448.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1",
   "userId": 1
}
```

Padrão de resposta

```json
{
   "id": 1,
   "title": "Computador",
   "price": 2500,
   "description": "Lorem ipsum.",
   "img": "https://images.pexels.com/photos/301448/pexels-photo-301448.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1",
   "userId": 1
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
   "description": "Lorem ipsum.",
   "img": "https://images.pexels.com/photos/301448/pexels-photo-301448.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
}
```

Por se tratar de uma rota de patch nem todos as chaves são obrigatórias.

Padrão de resposta

```json
{
   "id": 1,
   "title": "Computador",
   "price": 2500,
   "description": "Lorem ipsum.",
   "img": "https://images.pexels.com/photos/301448/pexels-photo-301448.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1",
   "userId": 1
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
   "id": 1
}
```
