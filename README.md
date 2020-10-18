# Documentação de Api Game
APrendendo a Documentar Api Manualmente 2020
## Endpoints
### GET /game
Esse endpoints é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parametros
Nenhum
#### Respostas
#####  ok 200
Caso essa resposta aconteça você vai receber a listagem de todos os games. 

Exemplo de Resposta:
```
{
    "empresa": "Guia do programador",
    "user": {
        "id": 1,
        "email": "victordevtb@guiadoprogramador.com"
    },
    "games": [
        {
            "id": 23,
            "title": "Call of duty MW",
            "year": 2019,
            "price": 60
        },
        {
            "id": 65,
            "title": "Sea of thieves",
            "year": 2018,
            "price": 40
        },
        {
            "id": 2,
            "title": "Minecraft",
            "year": 2012,
            "price": 20
        }
    ]
}
````


##### Falha na autenticação ! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos :
Token Inválido, Token expirado.

Exemplo de Resposta:

```
{
    "err": "Token inválido!"
}
```

### GET /auth
Esse endpoints é responsável por fazer o procsso de Login
#### Parametros
Email: E-mail do usuário cadastrado no sistema

password: senha do usuário cadastrado no sistema, com aquele determinado e-mail

Exemplo:

```
 email: "victordevtb@guiadoprogramador.com",
  password: "nodejs<3"
```

#### Respostas
#####  ok 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API

Exemplo de Resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ2aWN0b3JkZXZ0YkBndWlhZG9wcm9ncmFtYWRvci5jb20iLCJpYXQiOjE2MDMwNDg3NTMsImV4cCI6MTYwMzIyMTU1M30.TjMjCk2eF06q6qryMK2Z8k2K88uAOk9QDBsCJNuq9l4"
}
````


##### Falha na autenticação ! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos :
senha ou e-mail incorretos.

Exemplo de Resposta:

```
{ err: "Credenciais inválidas!" }
```

