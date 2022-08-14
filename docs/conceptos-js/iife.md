---
slug: "funciones-iife"
title: "Funciones IIFE"
---

`Immediately Invoked Expression` o expresiones de función ejecutadas inmediatamente son funciones que se ejecutan tan pronto como se definen.

```js
(() => {
  console.log('Esta función se ejecuta inmediatamente')
})()
```

Este tipo de funciones es muy útil para:

- Evitar el error de `top-level-await`

```js
(async()=>{
  await fetch('https://api')
})()
```

:::tip Actualización

Con la nueva versión de ECMAScript 6 2022 se permite `top-level-await`

::: 

- Para encapsular variables y aislarlas del entorno global