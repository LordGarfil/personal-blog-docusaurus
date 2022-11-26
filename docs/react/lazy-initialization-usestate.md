---
slug: "lazy-initialization-usestate"
title: "useState lazy initialization"
---

Cuando se inicializa un valor inicial dentro del hook useState, se pasa un parametro que es evaluado en cada renderización.

```js
const [state, setState] = useState(0)
```

Esto no es generalmente un problema ya que Javascript es muy rápido para esto. Sin embargo, cuando el valor inicial de un estado es un proceso muy pesado esto puede suponer mayor esfuerzo computacional.

```js
const [state, setState] = useState(window.localStorage.getItem("item"))
```

Para evitar que durante cada renderización el estado sea evaluado y nuevamente evaluado, se puede pasar uná función (no necesariamente un callback) como parámetro en el usaState.

```js
// Función anónima
const [state, setState] = useState(() => window.localStorage.getItem("item"))

//Función definida
const GetLocalStorageItem = () => window.localStorage.getItem("item")
const [state, setState] = useState(GetLocalStorageItem)
```