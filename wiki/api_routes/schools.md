[Voltar](menu.md)

# Rotas da Escola

## Criar uma Escola <a name="create_school"></a>

Criando uma Escola com determinadas propriedades.
POST /schools

### Parâmetros

| Nome        | Tipo   | Descrição                |
| ----------- | ------ | ------------------------ |
| name        | string | Nome da escola           |
| description | string | Descrição da escola      |
| type        | string | Tipo da escola           |
| icon        | image  | Foto de perfil da Escola |

### Exemplo

```json
rote: /schools
json: {
	"name": "ETEC de Taboão da Serra",
	"description": "Uma escola técnica da rede Centro Paula Souza",
	"type": "ensino medio e tecnico",
	"icon": "icon.png"
}
```

### Resposta

```json
Status: 201 CREATED
_______________________________________________________________

{
    "id_school": 1
}
```

## Selecionar todas as Escolas <a name="select_schools"></a>

Selecionar todas as escolas que o indivíduo tem acesso
GET /schools

### Exemplo

	rote: /schools

### Resposta

```json
Status: 200 OK
_______________________________________________________________

[
{
	"id": 5,
	"name": "ETEC de Taboão da Serra",
	"description": "Uma escola técnica da rede Centro Paula Souza",
	"type": "ensino medio e tecnico",
	"icon": "icon.png"
},
]
```

## Selecionar uma Escola <a name="select_school"></a>

Seleciona uma escola em especifico que o individuo tem acesso
GET /schools/:id_school

### Exemplo

	rote: /schools/1

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
	"id": 5,
	"name": "ETEC de Taboão da Serra",
	"description": "Uma escola técnica da rede Centro Paula Souza",
	"type": "ensino medio e tecnico",
	"icon": "icon.png"
}
```

## Editar uma Escola <a name="edit_school"></a>

Editando uma Escola com determinadas propriedades.
PUT /schools/:id_school

### Parâmetros

| Nome        | Tipo   | Descrição                |
| ----------- | ------ | ------------------------ |
| name        | string | Nome da escola           |
| description | string | Descrição da escola      |
| type        | string | Tipo da escola           |
| icon        | image  | Foto de perfil da Escola |

### Exemplo

```json
rote: /schools/1
json: {
	"name": "ETEC de Taboão da Serra",
	"description": "**que que é pra por aqui?**",
	"type": "ensino medio e tecnico",
	"icon": "icon.png"
}
```

### Resposta

    Status: 204 No Content

## Deletar uma Escola <a name="delete_school"></a>

Removendo uma determinada Escola
DELETE /schools/:id_school

### Exemplo

    rote: /schools/1

### Resposta

    Status: 204 No Content