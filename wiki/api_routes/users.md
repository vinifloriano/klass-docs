[Voltar](menu.md)

# Rotas do Usuário

## Criar um usuário

Criando um usuário com determinadas propriedades.

    POST /users

### Parâmetros

| Nome       | Tipo   | Descrição        |
| ---------- | ------ | ---------------- |
| user       | string | Nome do usuário  |
| email      | string | Email do usuário |
| password   | string | Senha do usuário |

### Exemplo

```json
rote: /users
json: {
    "username": "Vinicius",
    "email": "vinicius@gmail.com",
    "password": "123456",
}
```

### Resposta

```json
Status: 201 CREATED
_______________________________________________________________

{
    "token": "s4ad6854asd56a74w1d"
}
```

## Selecionar um Usuário <a name="get_user"></a>

Selecionando um usuário com e recebendo suas informações.

    GET /users 
    REQUIRED authentication

### Exemplo

```json
rote: /users
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
    "username": "Vinicius",
    "email": "vinicius@gmail.com",
    "password": "123456",
    "birth_date": "05/12/2002",
    "icon": "foto.jpg"
}
```

## Editar um Usuário <a name="edit_user"></a>

Editando um usuário com determinadas propriedades.

    PUT /users
    REQUIRED authentication
    

### Parâmetros

| Nome       | Tipo   | Descrição          |
| ---------- | ------ | ------------------ |
| name       | string | Nome do usuário    |
| email      | string | Email do usuário   |
| password   | string | Senha do usuário   |
| birth_date | date   | Data de nascimento FORMATO DD/MM/YYYY |
| icon       | image  | Foto de perfil do usuário |

### Exemplo

```json
rote: /users
json: {
    "username": "Vinicius",
    "email": "vinicius@gmail.com",
    "password": "123456",
    "birth_date": "05/12/2002",
    "icon": "foto.jpg"
}
```

### Resposta

    Status: 204 No Content

## Deletar um Usuário <a name="delete_user"></a>

Removendo um determinado usuário

    DELETE /users
    REQUIRED authentication

### Exemplo

```json
    rote: /users
```

### Resposta

    Status: 204 No Content

## Criar uma Sessão <a name="create_session"></a>

Criando uma sessão que autoriza um usuário.

    POST /sessions

### Parâmetros

| Nome     | Tipo   | Descrição        |
| -------- | ------ | ---------------- |
| email    | string | Email do usuário |
| password | string | Senha do usuário |

### Exemplo

```json
rote: /sessions
json: {
    "email": "vinicius@gmail.com",
    "password": "123456",
}
```

### Resposta

```json
Status: 200 OK
______________________________________________________________

{
    "token": "s4ad6854asd56a74w1d"
}
```