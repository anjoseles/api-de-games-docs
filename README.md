# API DE Games  
Esta API é utilizada para tal e tal 
## Endpoints
### GET /games
Essse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
### Paramentros
nenhum
### Respostas 
#### OK! 200 
Caso essa resposta aconteca você vai receber a listagem de todos os games.
Exemplo de resposta: 
```
[
      {
          id: 23,
          title: 'Call of duty MW',
          year: 2019,
          price: 60
      },
      {
          id: 65,
          title: 'Sea of thieves',
          year: 2018,
          price: 40
      },
      {
          id: 2,
          title: 'Minecraft',
          year: 2012,
          price: 20
      }
]
```
#### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição, Motivos: TOKEN inválidos, TOKEN expirado.
Exemplo de resposta.
```
{
    "err": "Token inválido!"
}
```

### POST /auth
Essse endpoint é responsável pelo processo de login.
### Paramentros
email: Email do usuário cadastrado no sistema.
password: Senha do usuário cadastrado no sistema, conforme e-mail.
Exemplo:
```
{
    "email": "guilherme@gmail.com",
    "password": "java"
},
```
### Respostas 
#### OK! 200 
Caso essa resposta aconteca você vai receber o TOKEN JWT para conseguir acessar endpoints protegidos na API.
Exemplo de resposta: 
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MjAsImVtYWlsIjoiZmFiaW9AZ21haWwuY29tIiwiaWF0IjoxNjIwMTU1NzM4LCJleHAiOjE2MjAzMjg1Mzh9.pRm2NLyCLhQ1WhbZej916eR5txLUoQMOJ8DnzQuO1jM"
}

```
#### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição, Motivos: Senha ou email incorretos.
```
{
      {token: "Credencias inválidas!"}
}

```
