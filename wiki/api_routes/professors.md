[Voltar](menu.md)

# Rotas do Professor

## Criar um professor <a name="create_professor"></a>

Criando um professor com determinadas propriedades.

	POST /schools/:id_school/professors
	REQUIRED authentication

### Parâmetros

| Nome       | Tipo   | Descrição                                           |
| ---------- | ------ | --------------------------------------------------- |
| name       | string | nome do professor                                   |
| email      | string | email do professor                                  |
| subjects   | array of int   | matérias que o professor leciona (id)       |
| priority   | int   | Prioridade do professor onde 0 é a maior e +infinito é a menor  |

### Exemplo

```json
rote: /schools/1/professors/
json: {
	"name": "Wallace Andrade",
	"email": "wallace.romantismo@gmail.com",
	"subjects": [1, 2, 5],
	"priority": 0
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

## Selecionar todas os professores <a name="select_professors"></a>

Selecionar todas os professores de uma escola que o indivíduo tem acesso

	GET /schools/:id_school/professors
	REQUIRED authentication

### Exemplo

```
	rote: /schools/1/professors
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
	[
		{
			"name": "Wallace Andrade",
			"email": "wallace.romantismo@gmail.com",
			"subjects": [1, 2, 3],
			"priority": 5,
			"titulation": "Mestrado",
			"days": [
				{
					"day": 1,
					"schedules":[
						{
							"start": "7:30",
							"end": "12:00"
						},
						{
							"start": "21:00",
							"end": "22:00"
						},
					]
				},
				{
					"day": 3,
					"schedules":[
						{
							"start": "12:00",
							"end": "15:30"
						}
					]
				}
			]
		},
		{
			"name": "Manoel Messias",
			"email": "messias.bhaskara@gmail.com",
			"subjects": [4, 5],
			"priority": 3,
			"titulation": "Mestrado",
			"days": [
				{
					"day": 4,
					"schedules":[
						{
							"start": "7:30",
							"end": "12:00"
						}
					]
				},
				{
					"day": 5,
					"schedules":[
						{
							"start": "12:00",
							"end": "15:30"
						}
					]
				}
			]
		}
	]
}
```

## Selecionar um Professor <a name="select_professor"></a>

Seleciona um professor em especifico que o individuo tem acesso

	GET /schools/:id_school/professors/:id_professor
	REQUIRED authentication

### Exemplo

```
	rote: /schools/1/professors/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
	"name": "Wallace Andrade",
	"email": "wallace.romantismo@gmail.com",
	"subjects": [1, 2, 3],
	"priority": 5,
	"titulation": "Mestrado",
	"days": [
		{
			"day": 1,
			"schedules":[
				{
					"start": "7:30",
					"end": "12:00"
				},
				{
					"start": "21:00",
					"end": "22:00"
				},
			]
		},
		{
			"day": 3,
			"schedules":[
				{
					"start": "12:00",
					"end": "15:30"
				}
			]
		},
	]
}
```
## Editar um professor (Edição do usuário) <a name="edit_professor"></a>


	PUT /schools/:id_school/professors/:id_professor
	REQUIRED authentication
	

### Parâmetros

| Nome                 | Tipo   | Descrição                                    |
| -------------------- | ------ | -------------------------------------------- |
| titulation | string | Titulação do professor                                 |
| days  | array of objects | Array de objetos contendo um int day indicando o dia e um array schedules contendo strings start e end, indicando quando começa e termina um horário do professor               |

### Exemplo

```json
rote: /schools/1/professors/1
json: {
	"titulation": "Mestrado",
	"days": [
		{
			"day": 1,
			"schedules":[
				{
					"start": "7:30",
					"end": "12:00"
				},
				{
					"start": "21:00",
					"end": "22:00"
				},
			]
		},
		{
			"day": 3,
			"schedules":[
				{
					"start": "12:00",
					"end": "15:30"
				}
			]
		},
	]
}
```

### Resposta

    Status: 204 No Content

## Editar um professor (Edição da Escola) <a name="edit_professor"></a>

Editando um Turno com determinadas propriedades.

	PUT /schools/:id_school/professors/:id_professor
	REQUIRED authentication

### Parâmetros

| Nome                 | Tipo   | Descrição                                    |
| -------------------- | ------ | -------------------------------------------- |
| name       | string | Nome do professor                                      |
| email      | string | email do professor                                     |
| subjects   | array of int   | matérias que o professor leciona (id)          |
| priority   | int   | Prioridade do professor onde 0 é a maior e +infinito é a menor  |

### Exemplo

```json
rote: /schools/1/professors/1
json: {
	"name": "Wallace Andrade",
	"email": "wallace.romantismo@gmail.com",
	"subjescts": [1, 2, 3],
	"priority": 5
}
```

### Resposta

    Status: 204 No Content

## Deletar um professor <a name="delete_professor"></a>

Removendo um determinado professor

	DELETE /schools/:id_school/professors/:id_professor
	REQUIRED authentication

### Exemplo

```json
    rote: /schools/1/professors/1
```

### Resposta

    Status: 204 No Content
