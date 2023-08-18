---
description: Aprenda a manusear o arquivo .isadb2
---

# 🧠 Arquivo .isadb2

O uso e manuseio do `.isadb2` é bem simples e provavelmente você deve aprender apenas lendo essa documentação.

## Criando linhas

Para criar um novo conteúdo dentro do `.isadb2`, apenas coloque um `$` ao lado do nome e `[]` no conteúdo.

Lembrando que esse nome **NÃO** pode ter espaços. Pode haver conflito caso tenha, mas no conteúdo, os espaços são permitidos.

```tsconfig
$nome[conteúdo número 1]
```

## Adicionando comentários

Para melhor comunicação interna. Você pode adicionar comentários no `.isadb2`, apenas adicione a `#` em vez do `$` e o seu comentário.

```tsconfig
$nome[conteúdo]
# comentário 1
$outroValor[outro conteúdo]
```

## Adicionando linhas especiais

Linhas especiais são necessárias para leitura do arquivo. Elas são separadas entre `JSON`, `Array` e `Number`, você PRECISARÁ colocar elas para uma melhor leitura do arquivo.

* JSON -> Cria uma variável JSON dentro do `.isadb2`, usa JSON padrão
* Array -> Cria um array dentro do `.isadb2`, não usa colchetes, use apenas a `,`. Dentro desse Array, você pode colocar Objetos, Números e mais outro Array.
* Number -> Cria um número dentro do `.isadb2`, pode ser Inteiro ou o Inverso (Float)

```tsconfig
$nome[conteúdo]
# comentário 1
$outroValor[outro conteúdo]
$object[JSON({"nome": "Facundo", "sobrenome": "Rufino"})]
$array[Array(nome1, nome2, nome3, JSON({"objeto": "dentro do array"}), Number(10), Array(uno, dos))]
$number[Number(5)]
```
