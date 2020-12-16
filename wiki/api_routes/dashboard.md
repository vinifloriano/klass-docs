[Voltar](menu.md)

# Rotas do Dashboard

## Informações gerais da Dashboard <a name="dashboard"></a>

Exibe as informações do dashboard da escola

	GET /schools/:id_school/
	REQUIRED authentication

### Exemplo
```
	rote: /schools/1/dashboard
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
    "dashboard":{
		"school_name": "ETEC de Taboão da serra",
		"semanal_hours": 40,
		"professors_number": 22,
		"classes_number": 5,
		"students_number":340,
		"subjects_number": 36,
		"turns_number":3,
		"notifications_number": 54,
		"reports_number": 12
    }
}
```