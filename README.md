# json-server-base

## Endpoints

Existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login, 1 endpoint onde pode adicionar um Animal.

A base url é:

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

EXEMPLO:
POST /register
{
"email": "olivier@mail.com",
"password": "bestPassw0rd",
"firstname": "Olivier",
"lastname": "Monge",
"age": 32
}

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

EXEMPLO:
POST /login
{
"email": "olivier@mail.com",
"password": "bestPassw0rd"
}

EXEMPLO de resposta:
200 OK
{
"accessToken": "xxx.xxx.xxx"
}

#### Caso queira ver todos usuarios cadastrados

GET /users <br/>

Lembrando que precisa estar autenticado

### Animal

POST /animals <br/>

Existem 1 endpoint que pode ser utilizado para cadastrar um animal

POST /animals

{
"name": "Cachorro",
"family": "Canidae",
"Genre": "Canis",
"userId": 1,
}

Lembrando que precisa do token para fazer o POST

É possivel editar algum animal ja criado. EXEMPLO:
PATCH /animals/:idDoAnimal

{
"name": "Pitbull",
"userId": 1
}

Para acessar todos animais pode ser feito um GET

GET /animals <br/>
