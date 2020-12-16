[Voltar](menu.md)

# Rotas de Convites

## Cria conexão professor <a name="invite_professor"></a>

Cria uma ligação entre usuário e escola através de um convite

	POST /invites
	REQUIRED authentication

### Exemplo

```
	rote: /invites
	
	json:
	{
		"school_id": "SADas84d7"
	}
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
    "message": "Inserido com sucesso"
}
```

## Cria conexão aluno <a name="invite_student"></a>

Cria uma ligação entre usuário e classe através de um convite

	POST /invites
	REQUIRED authentication

### Exemplo

```
	rote: /invites
	json:
	{
    	"class_id": "SADas84d7"
	}
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
    "message": "Inserido com sucesso"
}
```
