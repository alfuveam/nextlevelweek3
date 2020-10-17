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

Day3

Os 3 principais pirales do react
1 - Componente:
-
    hooks:

```typescript
    useEffect(() => {}, []);
```
-
   2 - Estado:

    ```typescript    
            const orphanages = useState([]);
    ```
3- Propriedade:

Shimmer Effect é uma alternativa muito efetiva em relação ao loading tradicional pois permite que sejam criadas Skeletons Screens.
https://blog.rocketseat.com.br/react-native-shimmer/


Day 4

ReactJS
-    Utilizado na WEB
    -   Com o AppPackage é gerado apenas um arquivo para a aplicação chamado bundle.js

ReactNative
-    Para mobile(ISO/Androisio[Android])

Tipo de build utilizando o modo tradicional, ainda é
que tem mais performace.

-   IOS
    -   Object-C
    -   Swift
        -   Build   (IPA)

-   Android
    -    Java
    -   Kotlin
        -   Build para  (APK)

Multiplataforma (RN)

-   IOS / Android
    -   JavaScript
        -   Com o MetroBundler é gerado um Bundle JavaScript. (bundle.js)
        -   Com isso é utilizado o JS Core para fazer a conexão para a API nativa.
        
    -   A diferença do nativo
        -   Gera a linguage nativa direto
            -   \<Text> ----> UIText

Expo "O matador de (IDE/VM) pesada"

-   As limitações do Expo
    -   Quando utilizar alguma funcionalidade não implementada. Ex: bluetooth
    -   Site para verificar as features solicitadas:
        https://expo.canny.io/feature-requests

ReactNative stylus
    Por padrão já tem
```css
    display: flex
```

Colocar alias no nome da variavel
```typescript
  const [fontsLoaded] = useFonts({     
    nunito700: Nunito_700Bold, 
    Nunito_800ExtraBold
  });
```
```css
  footerText: {
    fontFamily: 'nunito700',
    color: '#8fa7b3',
  }
```

Day 5

Ripple effect
```typescript
    <BorderlessButton onPress={() => {}}>
        <Feather name="arrow-left" size={24} color="#15b6d6"></Feather>
    </BorderlessButton>
```
-   Para algo que nao é um botão
```typescript
<TouchableOpacity style={styles.createOrphanageButton} onPress={handleNavigateToCreateOrphanage}>
    <Feather name="plus" size={20} color="#FFF"/>
</TouchableOpacity>
```
-   Então é um botão
```typescript
<RectButton style={styles.createOrphanageButton} onPress={handleNavigateToCreateOrphanage}>
    <Feather name="plus" size={20} color="#FFF"/>
</RectButton>
```

Deep Linking
    -   Uma forma de conectar um APP ao outro


Opção para verificar se a variavel foi declarada
```typescript
    if(delicinha?){
        console.log("declarada!")
        } else {
        console.log("Não declarada")
    }
```