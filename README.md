# Estándares de codificación para TypeScript
Estandares de codificación para el lenguaje typescript para proyectos utlizados en las plataformas.

## Indice
<!-- MarkdownTOC depth=0 autolink=true autoanchor=true -->

- [Declaración de variables](#declaración-de-variables)
    - [Nombres de variables](#nombres-de-variables)
    - [Valores de variables](#valores-de-variables)
    - [Declaración de multiples variables](#declaración-de-multiples-variables)
    - [Variables de tipo array](#variables-de-tipo-colección)
- [Declaración de funciones](#declaración-de-funciones)
    - [Nombres de funciones](#nombres-de-funciones)
    - [Llaves y espaciado de funciones](#llaves-y-espaciado-de-funciones)
    - [Tipos de funciones](#tipos-de-funciones)
    - [Argumentos de una función](#argumentos-de-una-función)
- [Construcción de cadenas](#construcción-de-cadenas)
- [Operaciones](#operaciones)
    - [Operaciones lógicas de igualdad y desigualdad](#operaciones-lógicas-de-igualdad-y-desigualdad)
- [Por considerar](#por-considerar)
- [Referencias](#referencias)

<!-- /MarkdownTOC -->


<a name="declaración-de-variables"></a>
## Declaración de variables
Declarar variables es una de las cosas más importantes a la hora de codificar, por eso es necesario tener en cuenta las siguientes premisas:

<a name="nombres-de-variables"></a>
#### Nombres de variables
Los nombres de variables deben ser escritos con notación camelCase y en ingles, toda variable o funcionalidad generalmente el codigo en ingles.

```typescript
let test;  // Nombre de variable correcto
let i_am_bad; //  Nombre de variable incorrecto
let iAmFine; //  Nombre de variable correcto
const a = 20 // Nombre de constante incorrecto
const myFav = 20 // nombre de constante correcto
```
- Usar el PascalCase para nombrar el tipo.
```typescript
let persona : PersonaModel;
```
- No usar I como prefijo de nombre de interfaz.
```typescript
let persona : IPersona; // incorrecto
```

<a name="valores-de-variables"></a>
#### Valores de variables
Los espacios entre el nombre y el valor de una variable son muy importantes, puesto que mejoran la legibilidad del código y no color el tipo de datos si se le asigno el valor.

```typescript
let test = 1;  // Nombre de variable correcto
let iAmFine = true; //  Nombre de variable correcto
let costValue: number = 0; // incorrecto
let costValue = 0; //correcto
```

<a name="declaración-de-multiples-variables"></a>
#### Declaración de multiples variables
Cuando se declaran multiples variables deben declararse todas con la misma sentencia `let`, una variable por linea y con coma (`,`) al final a menos que sea la ultima variable, en cuyo caso se usará punto y coma (`;`) al final de la linea.
A partir de la segunda linea debe usarse 4 espacios antes del nombre de variable para mejorar la legibilidad del código fuente.
El orden de las variables debe ser alfabetico de ser posible.

- Una declaración erronea es de la siguiente manera:
```typescript
// declaración erronea
let bad1 = 1;
let iAmFine = false;
let sampleVariable = "wrong";

```

- Una declaración correcta es de la siguiente manera:
```typescript
// declaración correcta
let iAmFine = true, // usa coma
    greatDay = 1, // usa coma
	sampleVariable = true; // usa punto y coma por que es la ultima variable

```

<a name="variables-de-tipo-colección"></a>
#### Variables de tipo array
Cuando la variable a declarar contiene un elemento de tipo array (arreglo y objeto).
```typescript
// declaración correcta
let list: number[] = [1, 2, 3];
//o
let list: Array<number> = [1, 2, 3],

    gender: string[] = ["male", "female"], // colección con 2 elementos
    users = {
        "Hugo": "Duck 1",
        "Paco": "Duck 2",
        "Luis": "Duck 3"
    }, // colección con más de 2 elementos
    attributes: string[] = [
        "fuerza",
        "velocidad",
        "inteligencia",
        "carisma",
    ],
    base64_logo_parts: string[] = [
        'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAMAAADXqc3KAAAB+',
        'FBMVEUAAAA/mUPidDHiLi5Cn0XkNTPmeUrkdUg/m0Q0pEfcpSbwaVdKskg+lUP4zA/iLi3m',
        'sSHkOjVAmETdJSjtYFE/lkPnRj3sWUs8kkLeqCVIq0fxvhXqUkbVmSjwa1n1yBLepyX1xxP',
        '0xRXqUkboST9KukpHpUbuvRrzrhF/ljbwaljuZFM4jELaoSdLtElJrUj1xxP6zwzfqSU4i0',
        // ...
        // more lines 
        // ...
        '/0rbNvHVxiJywa8yS2KDfV1dfbu31H8jF1RHiTKtWYeHxUvq3bn0pyjCRaiRU6aDO+gb3aE',
        'fEeVNsDgm8zzLy9egPa7Qt8TSJdwhjplk06HH43ZNJ3s91KKCHQ5x4sw1fRGYDZ0n1L4FKb',
        '9/BP5JLYxToheoFCVxz57PPS8UhhEpLBVeAAAAAElFTkSuQmCC'
    ]; // colección con más de 70 caracteres

```

<a name="declaración-de-funciones"></a>
## Declaración de funciones
Uno de los elementos más importantes de javascript son las funciones, éstas son conocidas como ciudadanos de primer tipo. Para la declaración de funciones es necesario tener en cuenta las siguientes premisas:

<a name="nombres-de-funciones"></a>
#### Nombres de funciones
Los nombres de funciones deben ser escritos con notación camelCase.

```typescript
function testFunction() {
    // code here
}
```

<a name="llaves-y-espaciado-de-funciones"></a>
#### Llaves y espaciado de funciones
Las llaves de las funciones deben empezar en la misma linea que se declara la función y debe haber un espacio entre el parentesis de cierre de argumentos y la llave de inicio de cuerpo de función, así:

```typescript
// A. Declaración de función
// B. Parentesis de argumentos
// C. Espacio
// D. Llave de inicio de cuerpo de función.

// ------- A ------- --- B --- C D
function testFunction(username) { 
    console.log('Hello ' + username + '...');
}
```

<a name="tipos-de-funciones"></a>
#### Tipos de funciones
En javascript las funciones pueden ser funciones como tal o funciones como variables. En caso de que sean funciones como variables es necesario usar punto y coma (`;`) despues del cuerpo de la función para finalizar la sentencia.

```typescript
function testFunction() {
    console.log('Hello Test...');
}

let anotherTestFunction = function() {
    console.log('Hello Test...');
}; // ; para fin de sentencia.
```

<a name="argumentos-de-una-función"></a>
#### Argumentos de una función
Para mejorar la legibilidad del código javascript los argumentos de funciones deben ser nombres con notación camelCase. Si son varios argumentos deben estar separados por coma (`,`) y un espacio, así:

```javascript
function testFunction(arg1, arg2, arg3) {
    console.log('Hello Test...');
}

let testFunction = function(arg1, arg2) {
    console.log('Hello Test...');
}; // ; para fin de sentencia.
```
Si unicamente hay un argumento no hay espacios a ningún lado, así:
```typescript
function testFunction(arg1){
    console.log('Hello Test...');
}
```

<a name="construcción-de-cadenas"></a>
## Construcción de cadenas
Deben ser usadas comilas simples ( ' ) puesto de ésta manera se reducen los problemas a la hora de escapar las comillas dobles ( " ) usadas cuando se genera HTML y mejora la legibilidad.
```typescript
// Incorrecto
let container0 = "<div class=\"another-container\" data-type=\"html\"></div>";
let container1 = "<div class="+'"'+"another-container"+'"'+
    " data-type="+'"'+"html"+'"'+"></div>";
// Correcto
let containerString = '<div class="container" data-type="html"></div>';
```
**Nota**: Para los casos en que no se estan construyendo elementos del DOM también deben ser usadas las comillas simples por uniformidad en el código.

<a name="operaciones"></a>
## Operaciones
Todas las operaciones deben tener espacios entre los operadores y los operandos para mejorar la legibilidad del código. Si se están usando parentesis no es necesario usar espacio entre los parentesis y los operandos.
```typescript

let v1 = b * h / 2,
    v2 = (location.toLowerCase() === 'medellin') ? 'frijoles' : 'lentejas';

```

<a name="operaciones-lógicas-de-igualdad-y-desigualdad"></a>
#### Operaciones lógicas de igualdad y desigualdad
Deben usarse los comparadores estrictos (aquellos que comparan valor y tipo `===`, `!==`) para todas las operaciones lógicas de comparación.
```typescript

function factorial(x) {
    if(x === 0){
        return 1;
    } else if(x !== 0) {
        return factorial(x - 1) * x;
    }
}

factorial(10);

```


<a name="referencias"></a>
## Referencias

* http://javascript.crockford.com/code.html
* [javascript: The good parts](http://www.amazon.com/exec/obidos/ASIN/0596517742/wrrrldwideweb)

