---
slug: "closure"
title: "Closure"
---

Los `closure` son funciones que regresan una función o un objeto con funciones que mantienen las variables que fueron declaradas fuera de su scope.

Son útiles para tener algo parecido a variables privadas, característica que no tiene JavaScript por default. Es decir encapsulan variables que no pueden ser modificadas directamente por otros objetos, sólo por funciones pertenecientes al mismo.

Tambien se puede usar para crear librerias o modulos, simulando la funcionalidad de estados sin necesidad de usar clases

```js
function Bot(config){
  let intentos = config

  const masIntentos = () => {
    intentos++
  }

  const getIntentos = () => intentos

  return { masIntentos, getIntentos }
}
```

En el bloque de código anterior no es posible acceder directamente a la variable `intentos`,
para ello se debe hacer uso de la función `getIntentos`.

:::danger Manera incorrecta

```js
const bot = new Bot(2)
bot.intentos()
```
:::

:::tip Manera correcta

```js
const bot = new Bot(2)
bot.getIntentos()
```
:::