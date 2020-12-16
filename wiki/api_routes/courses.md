[Voltar](menu.md)

# Rotas do Curso

## Criar um Curso <a name="create_course"></a>

Criando um curso com determinadas propriedades.

	POST schools/:id_school/courses
	REQUIRED authentication

### Parâmetros

| Nome           | Tipo   | Descrição              |
| -------------- | ------ | ---------------------- |
| name      | string | nome do curso          |
| turn_id   | string | id do curso        |
| modules   | array  | vetor de strings, cada string é nome do módulo   |

### Exemplo

```json
rote: schools/1/courses
json: {
	"name": "Ensino Médio",
	"turn_id": 1,
	"modules": ["1 ANO", "2 ANO"]
}
```

### Resposta

```json
Status: 201 CREATED
_______________________________________________________________

{
    "id": 1
}
```

## Selecionar todas os Cursos <a name="select_course"></a>

Selecionar todas os cursos que o indivíduo tem acesso

	GET schools/:id_school/courses
	REQUIRED authentication

### Exemplo

```
	rote: schools/1/courses
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

[
    {
        "id": 5,
	    "name": "Ensino Médio",
	    "turn_id": 1,
	    "modules": ["1 ANO", "2 ANO"]
    },
]
```

## Selecionar um Curso <a name="select_course"></a>

Seleciona um curso em especifico que o individuo tem acesso

    GET schools/:id_school/courses/:id_course
    REQUIRED authentication

### Exemplo

```
	rote: schools/1/courses/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
    "id": 1,
    "name": "Ensino Médio",
    "turn_id": 1,
    "modules": ["1 ANO", "2 ANO"]
}
```

## Editar um Curso <a name="edit_course"></a>

Editando um curso com determinadas propriedades.

    PUT schools/:id_school/courses/:id_course
    REQUIRED authentication

### Parâmetros

| Nome           | Tipo   | Descrição              |
| -------------- | ------ | ---------------------- |
| name      | string | nome do curso          |
| course_id   | string | id do curso        |
| modules   | array  | vetor de strings, cada string é nome do módulo   |

### Exemplo

```json
rote: /courses/1
json: {
    "name": "Ensino Médio",
    "turn_id": 1,
    "modules": ["1 ANO", "2 ANO"]
}
```

### Resposta

    Status: 204 No Content

## Deletar um curso <a name="delete_course"></a>

Removendo um determinado curso

    DELETE schools/:id_school/courses/:id_course
    REQUIRED authentication

### Exemplo

```json
    rote: schools/1/courses/1
```

### Resposta

    Status: 204 No Content
