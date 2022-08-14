---
slug: "objeto-arguments"
title: "Objeto arguments"
---

## Definición

El objeto `arguments` es una variable local disponible en todas las funciones **que no son funciones flecha**.
Retorna un arreglo con cada uno de los parametros pasados a la función invocada.

## Implementación

Al usar spread operator en los argumentos se obtiene un array de cada uno de los argumentos recibidos en la función.

```js
function saludar(...args){
  return args
}

saludar('Hola', {nombre: 'Pepe'}, ['Saludo, Greeting'], ()=>{console.log('Saludos')})
```