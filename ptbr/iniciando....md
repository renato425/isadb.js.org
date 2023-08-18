---
description: Primeiros passos na IsaDB2
---

# 🐤 Iniciando...

## Primeiro Passo

Para iniciar na IsaDB2, antes de tudo. Você precisa iniciar (criando uma instância) para começar a utilizar corretamente.&#x20;

A biblioteca `IsaDB2` usa, majoritariamente, funções **assíncronas** para seus projetos. Sempre retornando `<Promises>`.

Usarei também o `CommonJS`, mas é importante lembrar que a `IsaDB2` suporta o `EcmaScript`

```javascript
const IsaDB2 = require('isadb2)
/*
Nesse exemplo, usarei FUNÇÕES para iniciar todos os passos
*/

async function main() { //criando uma função `main`
    await IsaDB2.create() //criando a instância IsaDB2
}

main() //executando a função
```

## Set & Get

Na IsaDB2, o foco principal é o manuseio do banco de dados local. Nesse caso, o `.set` e o `.get` são as principais referências.

```javascript
const IsaDB2 = require('isadb2)

async function main() {
    await IsaDB2.create()
    await IsaDB2.set('foo', 'bar') //retorna -> true
    await IsaDB2.set('object', {nome: "Lucas", sobrenome: "Gomes"}) //retorna -> true
    //forma 1 de receber o get
    console.log(await IsaDB2.get('foo')) //retorna -> bar
    //forma 2 de receber o get
    IsaDB2.get('object').then(data => {
        console.log(data) //retorna -> {nome: "Lucas", sobrenome: "Gomes"}
    })
}

main()
```

## Delete

Caso queira deletar um dado do banco de dados, a função `Delete` pode salvar sua pátria.

```javascript
const IsaDB2 = require('isadb2)

async function main() {
    await IsaDB2.create()
    await IsaDB2.set('foo', 'bar')
    await IsaDB2.set('object', {nome: "Lucas", sobrenome: "Gomes"})
    console.log(await IsaDB2.get('foo'))
    IsaDB2.get('object').then(data => {
        console.log(data)
    })
    await IsaDB2.delete('foo') //retorna -> true
    console.log(await IsaDB2.get('foo')) //retorna -> null
}

main()
```

## Notação

A IsaDB2 também trabalha com notação dentro das suas strings. Para facilitar o manuseio de **Objetos** dentro do banco de dados.

```javascript
const IsaDB2 = require('isadb2)

async function main() {
    await IsaDB2.create()
    await IsaDB2.set('foo', 'bar')
    await IsaDB2.set('object', {nome: "Lucas", sobrenome: "Gomes"})
    console.log(await IsaDB2.get('foo'))
    IsaDB2.get('object').then(data => {
        console.log(data)
    })
    await IsaDB2.delete('foo')
    console.log(await IsaDB2.get('foo'))
    console.log(await IsaDB2.get('object.nome')) //retorna "Lucas"
}

main()
```
