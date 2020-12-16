[Voltar](menu.md)

# Rotas de Notificação

## Selecionar todas as notificações <a name="select_notifications"></a>

Selecionar todas as notificações que o indivíduo tem acesso

	GET /notifications
	REQUIRED authentication

### Exemplo

```
	rote: /notifications
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
    "notifications":[
    	{
    		"id_notification": 1, 
			"notification_date": "06/07/2020",
			"notification_time": "08:20",
    		"notification_content": "Messias entrou na escola Etec de Taboão da Serra"
    	}
    ]
}
```