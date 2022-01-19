# Validador de CUIT con operaciones matemáticas en JavaScript

## Descripción

Esta es una función simple para poder válidar el CUIT antes de enviarlo a alguna API, se puede útilizar directamente en el frontend para vádidar algún input en tiempo real o antes de envíar un formulario.

## Errores

En el caso de encontrar un error, crear un issue o pull request en GitHub [seguimiento de errores](https://github.com/jretondo/cuit-validator/issues)

## Documentación

* [Sitio del Proyecto](https://github.com/jretondo/cuit-validator)
* [Instalación](#instalación)
* [Uso](#uso)

## Instalación

```
npm install verificar-cuit-ar
```

## Uso

### Ejemplo 

```
import {verificadorCuit} from 'verificar-cuit-ar';

const cuit = 20999999961
const verificar = verificadorCuit(cuit)

if (verificar.isCuit) {
    //Es un número de CUIT válido
} else {
    //No es un número de CUIT válido
    //Ver los córdigos de error

    //1 Código verificador no corresponde al número (el calculo del último digito).
    //2 El CUIT no tiene los 11 digitos.
    //3 El tipo de CUIT no éxiste. (los primero dos digitos)
}
```

o con ES6

```
const {verificadorCuit} = require('verificar-cuit-ar');

const cuit = 20999999961
const verificar = verificadorCuit(cuit)

if (verificar.isCuit) {
    //Es un número de CUIT válido
} else {
    //No es un número de CUIT válido
    //Ver los córdigos de error

    //1 Código verificador no corresponde al número (el calculo del último digito).
    //2 El CUIT no tiene los 11 digitos.
    //3 El tipo de CUIT no éxiste. (los primero dos digitos)
}
```

Respuestas de la función:
```
return {
        isCuit: false | true,
        message: string (mensage de error),
        code: 0 | 1 | 2 | 3 (mensajes de error, 0 si no hay error en el cuit)
        }
```

