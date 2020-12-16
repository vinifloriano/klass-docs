[Voltar](menu.md)

# Rotas da Área

## Criar uma Área <a name="create_area"></a>

Criando uma área com determinadas propriedades.
POST /areas

### Parâmetros

| Nome      | Tipo   | Descrição    |
| --------- | ------ | ------------ |
| area_name | string | Nome da area |

### Exemplo

```json
rote: /areas
json: {
	"area_name":"Exatas"
}
```

### Resposta

```json
Status: 201 CREATED
_______________________________________________________________

{
    "id_area": 1
}
```

## Selecionar todas as areas <a name="select_areas"></a>

Selecionar todas as areas que o indivíduo tem acesso
GET /areas

### Exemplo

```
	rote: /areas
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
    "areas": [{id_area: 1, nome: "Exatas"}, {id_area: 2, nome: "Informática"}]
}
```

## Selecionar uma área <a name="select_area"></a>

Seleciona uma área em especifico que o individuo tem acesso
GET /areas/:id_area

### Exemplo

```
	rote: /areas/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
	"area_name":"Exatas"
}
```

## Editar uma área <a name="edit_area"></a>

Editando uma área com determinadas propriedades.
PUT /areas/:id_area

### Parâmetros

| Nome      | Tipo   | Descrição    |
| --------- | ------ | ------------ |
| area_name | string | Nome da area |

### Exemplo

```json
rote: /areas/1
json: {
	"area_name":"Exatas"
}
```

### Resposta

    Status: 204 No Content

## Deletar uma área <a name="delete_area"></a>

Removendo uma determinada área
DELETE /areas/:id_area

### Exemplo

```json
    rote: /areas/1
```

### Resposta

    Status: 204 No Content


