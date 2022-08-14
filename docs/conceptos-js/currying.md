---
slug: "currying"
title: "Currying"
---

Currying es poder llamar una función con menos parámetros de los que espera, esta devuelve una función que espera los parámetros restantes y retorna el resultado.

```js
//ES2015

const divisible = mod => num => num % mod;

//ES5

var divisible = function (mod) {
  return function (num) {
    return num % mod;
  }
}
```

Para llamar esta función hay dos opciones:

- Pasar los argumentos ejecutando las funciones

```js
divisible(10)(2)
```

- Pasar un argumento y recibir una función que recuerde este argumento

```js
const divisibleEn3 = divisible(3);

divisibleEn3(10)
```

## Ventajas de Currying

- Podemos crear funciones nuevas simplemente pasando nuestras funciones de base con algunos parámetros.

- Podemos transformar cualquier función que trabaje con un solo elemento en una que trabaje con una lista envolviéndola en un map.

- Se pueden escribir pequeñas piezas de código que sean más fáciles de reutilizar.

- Escribir funciones currificadas nos permitirá componer funciones.