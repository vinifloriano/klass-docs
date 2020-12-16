[Voltar](menu.md)

# Rotas da Home

## Informações gerais da Home <a name="home"></a>

Exibe as informações do dashboard da escola

	GET /home
	REQUIRED authentication

### Exemplo
```
	rote: /home
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
    "home":{
		"schools": [
		{
			"name": "ETEC de TABOÃO DA SERRA",
			"id": "ads4asd",
			"classes": [
				{
					"name": "1 ANO A",
					"id": 5
				},
				{
					"name": "2 ANO A",
					"id": 6
				},
			]
		},
		]
    }
}
```