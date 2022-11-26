---
slug: "validacion-tipado"
title: "Validación de tipado"
---

En React es posible verificar el tipado de las props sin necesidad de librerias como Flow o Typescript. Se puede hacer con la propiedad especial `PropTypes`, importandola desde su libreria prop-types

```js
import React from 'react';
import PropTypes from 'prop-types';

export function App(props) {
  return (
    <div className='App'>
      <h1>Hello {props.name}.</h1>
    </div>
  );
}

App.propTypes = {
  name: PropTypes.string
};
```

De esta manera se obliga al objeto props a presentar una key name de tipo String, de lo contrario se presentará un error en consola

:::danger
Invalid prop `name` of type `boolean` supplied to `App`, expected `string`.
:::

## Verificar estructura

Usando Proptypes.exact(), seguido de .isRequired podemos especificar el estructura que deben tener las props

```js
import React from 'react';
import PropTypes from 'prop-types';

export function App(props) {
  return (
    <div className='App'>
      <h1>Hello {props.person.name}.</h1>
    </div>
  );
}

App.propTypes = {
  person: PropTypes.exact({
    name: PropTypes.string.isRequired,
    age: PropTypes.number.isRequired
  }).isRequired
};
```

Para este caso el objeto props debe presentar un objeto `person` con dos keys: name de tipo String y age de tipo number

:::info
PropTypes solo se verifica en modo desarrollo.
:::

:::info
Información obtenida de: https://es.reactjs.org/docs/typechecking-with-proptypes.html
:::