[Voltar](menu.md)

# Rotas da Sala

## Criar uma Sala <a name="create_class"></a>

Criando uma Sala com determinadas propriedades.

	POST /schools/:id_school/classes
	REQUIRED authentication

### Parâmetros

| Nome         | Tipo   | Descrição     |
| ------------ | ------ | ------------- |
| name         | string | Nome da Sala  |
| module_id       | int | Módulo da sala (id) |
| students_quant | int  | Quantidade de alunos da sala |

### Exemplo

```json
rote: /schools/1/classes
json: {
	"name": "3 ANO A",
	"module_id": 5,
	"students_quant": 50
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

## Selecionar todas as Salas <a name="select_classes"></a>

Selecionar todas as Salas que o indivíduo tem acesso

	GET /schools/:id_school/classes
	REQUIRED authentication

### Exemplo

```
	rote: /schools/1/classes
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

[
	{
		"id": 5,
		"name": "3 ANO A",
		"module": 5,
		"students_quant": 50
	}
]
```

## Selecionar uma Sala <a name="select_class"></a>

Seleciona uma Sala em especifico que o individuo tem acesso

	GET /schools/:id_school/classes/:id_class
	REQUIRED authentication

### Exemplo

```
	rote: /schools/1/classes/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
	"class_name": "3 Ano",
	"class_level": "A",
	"class_course": "ETIM"

}
```

## Editar uma Sala <a name="edit_class"></a>

Editando uma Sala com determinadas propriedades.

	PUT /schools/:id_school/classes/:id_class
	REQUIRED authentication

### Parâmetros

| Nome         | Tipo   | Descrição     |
| ------------ | ------ | ------------- |
| name         | string | Nome da Sala  |
| module_id       | int | Módulo da sala (id) |
| students_quant | int  | Quantidade de alunos da sala |

### Exemplo

```json
rote: /schools/1/classes/1
json: {
	"name": "3 ANO A",
	"module_id": 1,
	"students_quant": 50
}
```

### Resposta

    Status: 204 No Content

## Deletar uma Sala <a name="delete_class"></a>

Removendo uma determinada Sala

	DELETE /schools/:id_school/classes/:id_class
	REQUIRED authentication

### Exemplo

```json
    rote: /schools/1/classes/1
```

### Resposta

    Status: 204 No Content
