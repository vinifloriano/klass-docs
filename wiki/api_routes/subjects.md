[Voltar](menu.md)

# Rotas da Matéria

## Criar uma Matéria <a name="create_subject"></a>

Criando uma matéria com determinadas propriedades.

	POST schools/:id_school/subjects
	REQUIRED authentication

### Parâmetros

| Nome                 | Tipo   | Descrição             |
| -------------------- | ------ | --------------------- |
| name         | string | Nome da matéria       |
| abbreviation | string | Abreviação da matéria |
| modules | array of object with module_id and quant_classes | Array de objetos indicando os módulos que tem tal matéria e quantas aulas tem em cada um |

### Exemplo

```json
rote: schools/2/subjects
json: {
	"name": "Matemática",
	"abbreviation": "MAT",
	"modules": [
		{
			"module_id": 1,
			"total_classes": 3
		}
	]
}
```

### Resposta

```json
Status: 201 CREATED
_______________________________________________________________

{
    "id_subject": 1
}
```

## Selecionar todas as Matérias <a name="select_subjects"></a>

Selecionar todas as Matérias que o indivíduo tem acesso

	GET schools/:id_school/subjects
	REQUIRED authentication

### Exemplo

```json
	rote: schools/1/subjects
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

[
	{
		"name": "Matemática",
		"abbreviation": "MAT",
		"modules": [
			{
				"module_id": 1,
				"total_classes": 3
			}
		]
	},
]
```

## Selecionar uma Matéria <a name="select_subject"></a>

Seleciona uma matéria em especifico que o individuo tem acesso

	GET schools/:id_school/subjects/:id_subject
	REQUIRED authentication

### Exemplo

```
	rote: schools/1/subjects/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________


{
	"name": "Matemática",
	"abbreviation": "MAT",
	"modules": [
		{
			"module_id": 1,
			"total_classes": 3
		}
	]
}
```

## Editar uma matéria <a name="edit_subject"></a>

Editando uma Matéria com determinadas propriedades.

	PUT schools/:id_school/subjects/:id_subject
	REQUIRED authentication

### Parâmetros

| Nome                 | Tipo   | Descrição             |
| -------------------- | ------ | --------------------- |
| name         | string | Nome da matéria       |
| abbreviation | string | Abreviação da matéria |
| modules | array of object with module_id and quant_classes | Array de objetos indicando os módulos que tem tal matéria e quantas aulas tem em cada um |

### Exemplo

```json
rote: schools/1/subjects/1
json: {
	"name": "Matemática",
	"abbreviation": "MAT",
	"modules": [
		{
			"module_id": 1,
			"total_classes": 3
		}
	]
}
```

### Resposta

    Status: 204 No Content

## Deletar uma matéria <a name="delete_subject"></a>

Removendo uma determinada matéria

	DELETE schools/:id_school/subjects/:id_subject
	REQUIRED authentication

### Exemplo

```json
    rote: schools/1/subjects/1
```

### Resposta

    Status: 204 No Content
