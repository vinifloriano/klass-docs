[Voltar](menu.md)

# Rotas do Relatório

## Criar um Relatório escolar <a name="create_school_report"></a>

Criando um relatório escolar com determinadas propriedades.
POST /schools/:id_school/reports

### Parâmetros

| Nome           | Tipo   | Descrição                                       |
| -------------- | ------ | ----------------------------------------------- |
| report_type    | string | Tipo de relatório                               |
| report_content | string | conteudo do relatório                           |
| report_date    | date   | data da emissão do relatório FORMATO DD/MM/YYYY |

### Exemplo

```json
rote: /schools/1/reports
json: {
	"report_type": "admin",
	"report_content": "*Inserir relatorio aqui*",
	"report_date": "04/07/2020"
}
```

### Resposta

```json
Status: 201 CREATED
_______________________________________________________________

{
    "id_report": 1
}
```

## Criar um Relatório de sala <a name="create_class_report"></a>

Criando um relatório de sala com determinadas propriedades.
POST /schools/:id_school/classes/:id_class/reports

### Parâmetros

| Nome           | Tipo   | Descrição                                       |
| -------------- | ------ | ----------------------------------------------- |
| report_type    | string | Tipo de relatório                               |
| report_content | string | conteudo do relatório                           |
| report_date    | date   | data da emissão do relatório FORMATO DD/MM/YYYY |

### Exemplo

```json
rote: /schools/1/classes/1/reports
json: {
	"report_type": "admin",
	"report_content": "*Inserir relatorio aqui*",
	"report_date": "04/07/2020"
}
```

### Resposta

```json
Status: 201 CREATED
_______________________________________________________________

{
    "id_report": 1
}
```

## Selecionar todos os relatórios escolares <a name="select_school_reports"></a>

Selecionar todos relatórios escolares que o indivíduo tem acesso
GET /schools/:id_school/reports

### Exemplo

```
	rote: /schools/1/reports
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
 "reports": [
	 {
		 "id_report": 1,
		 "report_type": "admin",
		 "report_content": "*Inserir relatorio aqui*","report_date": "04/07/2020"
	 },
	 {
		 "id_report":2,
		 "report_type": "admin",
		 "report_content": "*Inserir relatorio aqui*","report_date": "04/07/2020"
	}
 ]
}
```

## Selecionar todos os relatórios de sala <a name="select_class_reports"></a>

Selecionar todos relatórios de sala que o indivíduo tem acesso
GET /schools/:id_school/classes/:id_class/reports

### Exemplo

```
	rote: /schools/1/classes/1/reports
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
 "reports": [{"id_report": 1,"report_type": "admin","report_content": "*Inserir relatorio aqui*","report_date": "04/07/2020"},{"id_report":2,"report_type": "admin","report_content": "*Inserir relatorio aqui*","report_date": "04/07/2020"}]
}
```

## Selecionar um relatório escolar especifico <a name="select_school_report"></a>

Seleciona um relatório escolar em especifico que o individuo tem acesso
GET /schools/:id_school/reports/:id_report

### Exemplo

```
	rote: /schools/1/reports/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
	"report_type": "admin",
	"report_content": "*Inserir relatorio aqui*",
	"report_date": "04/07/2020"
}
```

## Selecionar um relatório de sala especifico <a name="select_class_report"></a>

Seleciona um relatório de sala em especifico que o individuo tem acesso

    GET /schools/:id_school/classes/:id_class/reports/:id_report

### Exemplo

```
	rote: /schools/1/classes/1/reports/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
	"report_type": "admin",
	"report_content": "*Inserir relatorio aqui*",
	"report_date": "04/07/2020"
}
```

## Deletar um relatório escolar <a name="delete_school_report"></a>

Removendo um determinado relatório escolar

    DELETE /schools/:id_school/reports/:id_report

### Exemplo

```json
    rote: /schools/1/reports/1
```

### Resposta

    Status: 204 No Content

## Deletar um relatório de sala <a name="delete_class_report"></a>

Removendo um determinado relatório escolar
DELETE /schools/:id_school/classes/:id_class/reports/:id_report

### Exemplo

```json
    rote: /schools/1/classes/1/reports/1
```

### Resposta

    Status: 204 No Content






## Criar um relatório de professor<a name="create_professor_report"></a>

Criando um relatório de professor com determinadas propriedades.
POST /schools/:id_school/professors/reports/

### Parâmetros

| Nome                 | Tipo   | Descrição             |
| -------------------- | ------ | --------------------- |
| id_professor         | int | ID do professor       |
| subject_abbreviation | string | Abreviação da matéria |
| report_date | date | Data da criação desse relaório |
| report | object | Contém todos os dias, horário de início e fim, sala de aula |

### Exemplo

```json
rote: /schools/1/professors/reports/
json: {
	"id_professor": 1,
	"subject_abbreviation": "PORT",
	"report_date": "08/07/2020",
	"report": {
		"monday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	   "tuesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "wednesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "thursday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "friday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ]
	}
}
```

### Resposta

```json
Status: 201 CREATED
_______________________________________________________________

{
    "id_professor_report": 1
}
```
## Selecionar vários relatórios de professores<a name="select_professor_reports"></a>

Selecionando todos os relatórios de professores
GET /schools/:id_school/professors/reports/


### Exemplo

```
	rote: /schools/1/professors/reports/
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
    "reports":[{
    	"id_report":1,
	    "id_professor": 1,
		"subject_abbreviation": "PORT",
		"report_date": "08/07/2020",
		"report": 
		"monday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	   "tuesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "wednesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "thursday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "friday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ]
    },
    "id_report":2,
    "id_professor": 2,
		"subject_abbreviation": "MAT"
		"report_date": "08/07/2020",
		"report": 
		"monday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 3,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 3,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 2
	      }
	     ],
	   "tuesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "wednesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "thursday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "friday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ]
    }
    
    ]
}
```

## Selecionar um relatório de professor<a name="select_professor_report"></a>

Selecionando um relatório de professor
GET /schools/:id_school/professors/reports/:id_report

### Exemplo

```
	rote: /schools/1/professors/reports/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
	"id_professor": 1,
	"subject_abbreviation": "PORT",
	"report_date": "08/07/2020",
	"report": 
		"monday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	   "tuesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "wednesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "thursday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "friday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ]
}
```


## Editar um relatório de professor<a name="edit_professor_report"></a>

Editando um relatório de professor
PUT /schools/:id_school/professors/reports/:id_professor_report

### Exemplo

```
	rote: /schools/1/professors/reports/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________

{
	"id_professor": 1,
	"subject_abbreviation": "FIS",
	"report_date": "08/07/2020",
	"report": 
		"monday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	   "tuesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "wednesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "thursday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ],
	    "friday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_class": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_class": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_class": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_class": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_class": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_class": 3
	      }
	     ]
}
```

## Criar um relatório de Estudante<a name="create_student_report"></a>

Criando um relatório de professor com determinadas propriedades.
POST /schools/:id_school/classes/reports/

### Parâmetros

| Nome                 | Tipo   | Descrição             |
| -------------------- | ------ | --------------------- |
| id_class       | int | ID da sala       |
| report_date | date | Data da criação desse relaório |
| report | object | Contém todos os dias, horário de início e fim, sala de aula |

### Exemplo

```json
rote: /schools/1/classes/reports/
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________
{
	"id_class": 1,
	"report_date": "08/07/2020",
	"report":
		"monday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	   "tuesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "wednesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "thursday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject":1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "friday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ]
}
```

## Selecionar todos os relatório de estudantes<a name="select_student_reports"></a>

Selecionando todos os relatórios do estudantes que o usuário tem acesso
GET /schools/:id_school/classes/reports/

### Exemplo

```
rote: /schools/1/classes/reports/
```

### Resposta

```json
	reports: [{
	"id_class": 1,
	"id_class_report": 1,
	"report_date": "08/07/2020",
	"report":
		"monday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	   "tuesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "wednesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "thursday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject":1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "friday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ]},
	    {
	"id_class": 2,
	"id_class_report": 2,
	"report_date": "08/07/2020",
	"report":
		"monday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	   "tuesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "wednesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "thursday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject":1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "friday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ]}
	]
```

## Selecionar um  relatório de estudante<a name="select_student_report"></a>

Selecionando um  relatório de estudante que o usuário tem acesso
GET /schools/:id_school/classes/reports/:id_report

```json
rote: /schools/1/classes/reports/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________
{
	"id_class": 1,
	"report_date": "08/07/2020",
	"report":
		"monday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	   "tuesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "wednesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "thursday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject":1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "friday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ]
}
```


## Editar um  relatório de estudante<a name="edit_student_report"></a>

editando um  relatório de estudante que o usuário tem acesso
PUT /schools/:id_school/classes/reports/:id_report

### Exemplo

```json
rote: /schools/1/classes/reports/1
```

### Resposta

```json
Status: 200 OK
_______________________________________________________________
{
	"id_class": 1,
	"report_date": "08/07/2020",
	"report":
		"monday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	   "tuesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "wednesday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "thursday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject":1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ],
	    "friday": [
	      {
	          "hour_start": "07:30",
	          "hour_end": "08:20",
	          "id_subject": 1,
	      },
	      {
	          "hour_start": "08:20",
	          "hour_end": "09:10",
	          "id_subject": 1,
	      },
	      {  "hour_start": "09:10",
	          "hour_end": "10:00",
	          "id_subject": 2,
	      },
	      {
	          "hour_start": "10:20",
	          "hour_end": "11:10",
	          "id_subject": 2
	      },
	      {
	          "hour_start": "11:10",
	          "hour_end": "12:00",
	          "id_subject": 3
	      },
	      {
	          "hour_start": "12:50",
	          "hour_end": "13:40",
	          "id_subject": 3
	      }
	     ]
}
```