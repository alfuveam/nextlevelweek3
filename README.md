- Day 1 -
Array
```json
[
    { "name": "Lar amor e paz", "address": "fon", "instructions": "...."},
    { "name": "Lar amor e paz", "address": "fon", "instructions": "...."},
    { "name": "Lar amor e paz", "address": "fon", "instructions": "...."},
    { "name": "Lar amor e paz", "address": "fon", "instructions": "...."},            
]
```

typescript Adiciona a tipagem 
JSX - JavaScript XML; Uma forma de adicionar HYML dentro do JavaScript
```typescript
interface User {
    name: string;
    email: string;
    address: {
        city: string;
        state: string;
    }
}

function mostraDadosUsuario(user: User) {
    return `${user.name} ${user.email}`
}
/*
//  Com erro
const usuario = {
    nome: 'Diego',
    email: 'll@gg.com'
}
*/

//  Sem erro
const usuario = {
    nome: 'Diego',
    email: 'll@gg.com',
    address: {
        city: 'Rio do Norte'
        state: 'Acre'
    }
}

mostraDadosUsuario(usuario)
```

- Day 2 -

ROTA = conjunto
Recurso = usuario

Metodos HTTP = GET, POST, PUT, DELETE
Parametros

GET = Buscar uma informação (lista, item)
POST = Criar uma informação
PUT = Editando uma informação
DELETE = Deletando uma informação

Parametros

Query:

    http://localhost:3333/users/?search=diego&page=2&queryIdentify=queryValue
Route: 

    http://localhost:3333/users/1 (Identificar um recurso)
Body: 

    http://localhost:3333/users/1 (Identificar um recurso)
```typescript    
    console.log(request.query);
    console.log(request.params);
    console.log(request.body);
```
Com o Query builder ou ORM é mais simples para trocar de banco de dados*

Driver nativo, Query builder, ORM

Drive Nativo

    sqlite3.query("select * from users");

Query builder

    knex('users').select('*').where('name', 'jubileu')

    -- converte para 
    SELECT * FROM USERS where name = 'jubileu'

ORM - Object Relational Mapping
    Tem um relacionamento com uma classe
    Ex: 3 users, vão ser 3 Objectos de usuario

Migrations
```typescript
    public async up(queryRunner: QueryRunner): Promise<void> {
        //  REALIZAR ALTERAÇÕES
        //  CRIAR TABELA, CRIAR UM NOVO CAMPO,
        //DELETAR ALGUM CAMPO
    }

    public async down(queryRunner: QueryRunner): Promise<void> {
        //  DESFAZER O QUE FOI FEITO NO UP
    }

```
MVC

    Model
    Views
    Controllers

