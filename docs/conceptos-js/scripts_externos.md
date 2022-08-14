---
slug: "scripts-externos-asincronos"
title: "Scripts externos"
---

# Scripts Asincronos

## Script Async

Se pueden agregar etiquetas de script dentro de un archivo **HTML** que tenga la propiedad `Async`.

```js
<script src="script.js" async></script>
```

Esto permite hacer un llamado al source requerido de manera asíncrona, sin detener el procesamiento del HTML hasta que no se haya obtenido totalmente la respuesta del source del script.

## Script Defer

Otra manera de llamar un script en **HTML** de manera `asincrona` es usando la propieda `Defer`

```js
<script src="script.js" defer></script>
```

La petición es igual asíncrona como en el `async` pero va a diferir la ejecución del Javascript **hasta que se cargue todo el documento**.