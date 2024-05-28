# Documentação da API

## Endereço da API
`https://ticonsulte.onrender.com`

## Rotas da API

### 1. Login

**Rota:** `/sessions`

**Descrição:** Rota para login da aplicação. O retorno será um objeto contendo um token (Bearer token).

**Método:** POST

**Dados para teste:**
```json
{
  "username": "18919379000142",
  "password": "18919379000142"
}
```

**Resposta:**
```json
{ 
	"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzaWduIjp7InN1YiI6IjUxMDFkNTNhLTJhNTMtNDc0Yy05MWE5LWE1NWIzZTllZTNmOSIsIm9mZmljZSI6Ijk1ODAyYTAzLWI5NWYtNGNmMS1hMzIyLWEwNTQ2OTdhMjU5MSJ9LCJpYXQiOjE3MTY5MjM1OTEsImV4cCI6MTcxNzAwOTk5MX0.6GHCmapDzClX7KPyU12WtyY_1ZMstWVBNvkmlv0c7PI", 
} 

```

### 2. Lançamento de Entrada ou Saída de Visitante
**Rota:** `/visitor/cam`

**Descrição:** Rota para registrar a entrada ou saída de um visitante.

**Método:** POST

**Dados esperados:**
```json
{
	"token": "Token do cliente", 
	"rule_name": "Exit", 
	"event_time": "event_time", 
	"channel_name": "Nome da camera"
}
```

### 3. Pegar Entradas do Dia por Zona
**Rota:** `/visitor/day?year=[ano]&month=[mes]&day=[dia]`

**Descrição:** Rota para obter as entradas do dia por zona.

**Método:** GET

**Parâmetros:**

 - `year`: Ano desejado
 - `month`: Mês desejado
 - `day`: Dia desejado

**Resposta:**
```json
[ 
	{ 
		"name": "Nome da zona", 
		"people_in": 1100, 
		"people_out": 800 
	} 
]
```
**Cabeçalho:**
```http
	Authorization: Bearer {id do token pego no login}
```

### 4. Pegar Entradas por Horário
**Rota:** `/visitor/daily?year=[ano]&month=[mes]&day=[dia]`

**Descrição:** Rota para obter as entradas por horário do dia.

**Método:** GET

**Parâmetros:**

 - `year`: Ano desejado
 - `month`: Mês desejado
 - `day`: Dia desejado

**Resposta:**
```json
[ 
	{ 
		"hora": "08:00", 
		"people_in": 1100, 
		"people_out": 800 
	} 
]
```
**Cabeçalho:**
```http
	Authorization: Bearer {id do token pego no login}
```

### Pegar Entradas do Mês por Data
**Rota:** `/visitor/month?year=[ano]&month=[mes]&day=[dia]`

**Descrição:** Rota para obter as entradas do mês por data.

**Método:** GET

**Parâmetros:**

 - `year`: Ano desejado
 - `month`: Mês desejado
 - `day`: Dia desejado

**Resposta:**
```json
[ 
	{ 
		"date": "2024-05-28", 
		"people_in": 1100, 
		"people_out": 800 
	} 
]
```
**Cabeçalho:**
```http
	Authorization: Bearer {id do token pego no login}
```