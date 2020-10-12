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