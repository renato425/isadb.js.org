---
description: Exemplo do uso da IsaDB2
---

# 📞 Exemplo

```javascript
const isadb = require('isadb2')

async function main() { //função assíncrona para exemplo
    await isadb.create() //criando instância isaDB

    await isadb.set('foo', 'bar') //setando propriedades
    isadb.get('foo').then(value => {
        console.log(value) //retornará -> bar
    })
}

main()
```

```javascript
const isadb2 = require('isadb2')

async function main() {
    await isadb2.create() //criando instância isaDB

    await isadb2.set('object', {name: 'renato', sobrenome: 'gouveia', idade: 42, email: 'emaildorenato@email.com'}) //saving a object
    console.log(await isadb2.get('object')) //retorna o objeto completo / usando await
    console.log(await isadb2.get('object.sobrenome')) //retorna apenas a propriedade `sobrenome` / usando await
    isadb2.get('object.name').then(value => {
        console.log(value) //retorna apenas a propriedade `name` / usando o then
    })
    isadb2.get('object.idade').then(value => {
        console.log(value) //retorna apenas a propriedade `idade` / usando then
    })
}

main()
```

```tsconfig
$objetoQualquer[Object({"nome": "legal"})]
$númeroQualquer[Number(12)]
$arrayQualquer[Array(nome1, nome2, nome3, Number(12), Object({"produto": "xilito"}))]
$stringQualquer[legal]
# comentário qualquer
```
