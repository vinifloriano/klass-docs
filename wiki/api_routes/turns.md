[Voltar](menu.md)

# Rotas do Turno

## Criar um Turno <a name="create_turn"></a>

Criando um turno com determinadas propriedades.

	POST schools/:id_school/turns
	REQUIRED authentication

### Parâmetros

| Nome           | Tipo   | Descrição              |
| -------------- | ------ | ---------------------- |
| name      | string | nome do turno          |
| start     | string | inicio do turno (HH:MM) |
| end       | string | fim do turno (HH:MM)   |
| class_duration | string | período de duração de aula |
| intervals | array | intervalos do turno (Objeto com as propriedades start e end) |
| week_days    | array    | vetor de numeros para indicar os dias que o turno possui aula. 0: domingo até 6: sábado |



### Exemplo

```json
rote: schools/1/turns
json: {
	"name": "Integral",
	"days": [
		{
			"start": "07:30",
			"end": "15:30",
			"class_duration": 50,
			"intervals": [
				{
					"start": "10:00",
					"end": "10:20"
				},
				{
					"start": "12:00",
					"end": "13:00"
				}
			],
			"day": 1
		},
		{
			"start": "07:30",
			"end": "15:30",
			"class_duration": 50,
			"intervals": [
				{
					"start": "10:00",
					"end": "10:20"
				},
				{
					"start": "12:00",
					"end": "13:00"
				}
			],
			"day": 2
		},
	]
}
```

### Resposta

```json
Status: 201 CREATED
_______________________________________________________________

{
    "id_turn": 1
}
```

## Selecionar todas os Turnos <a name="select_turns"></a>

Selecionar todas os turnos que o indivíduo tem acesso

	GET schools/:id_school/turns
	REQUIRED authentication

### Exemplo

```
	rote: schools/1/turns
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

[
	{
		"id": 1,
		"name": "Integral",
		"start": "07:30",
		"end": "15:30",
		"class_duration": 50,
		"intervals": [
			{
				"start": "10:00",
				"end": "10:20"
			},
			{
				"start": "12:00",
				"end": "13:00"
			}
		],
		"week_days": [1,2,3,4,5]
	},
]
```

## Selecionar um turno <a name="select_turn"></a>

Seleciona um turno em especifico que o individuo tem acesso

	GET schools/:id_school/turns/:id_turn
	REQUIRED authentication

### Exemplo

```
	rote: schools/1/turns/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
	"id": 4,
	"name": "Integral",
	"start": "07:30",
	"end": "15:30",
	"class_duration": 50,
	"intervals": [
		{
			"start": "10:00",
			"end": "10:20"
		},
		{
			"start": "12:00",
			"end": "13:00"
		}
	],
	"week_days": [1,2,3,4,5]
}
```

## Editar um Turno <a name="edit_turn"></a>

Editando um Turno com determinadas propriedades.

	PUT schools/:id_school/turns/:id_turn
	REQUIRED authentication

### Parâmetros

| Nome           | Tipo   | Descrição              |
| -------------- | ------ | ---------------------- |
| name      | string | nome do turno          |
| start     | string | inicio do turno (HH:MM) |
| end       | string | fim do turno (HH:MM)   |
| class_duration | string | período de duração de aula |
| intervals | array of [interval](#type_interval) | intervalos do turno |
| week_days    | array    | vetor de numeros para indicar os dias que o turno possui aula. 0: domingo até 6: sábado |

### Exemplo

```json
rote: schools/1/turns/1
json: {
	"name": "Noite",
	"start": "07:30",
	"end": "15:30",
	"class_duration": 50,
	"intervals": [
		{
			"start": "10:00",
			"end": "10:20"
		},
		{
			"start": "12:00",
			"end": "13:00"
		}
	],
	"week_days": [1,2,3,4,5]
}
```

### Resposta

    Status: 204 No Content

## Deletar um Turno <a name="delete_turn"></a>

Removendo um determinado Turno

	DELETE schools/:id_school/turns/:id_turn
	REQUIRED authentication

### Exemplo

```json
    rote: schools/1/turns/1
```

### Resposta

    Status: 204 No Content
