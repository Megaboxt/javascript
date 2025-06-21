# Arrays

Los arrays, arreglos o vectores, son estructuras de datos utilizadas en la mayoría de los lenguajes de programación como una herramienta ideal para agrupar varios valores (datos, elementos) dentro de una variable.

En JavaScript, un `array` es una `colección de variables o datos` que pueden ser todas del mismo tipo o cada una de un tipo de dato diferente. Los valores están ordenados y se acceden por índices numéricos empezando desde 0 (cero).

## ¿Cómo crear un Array?

Hay dos maneras de poder crear un array:

1. Usando corchetes [ ] (Forma literal):

<pre>
  // Creación de arrays con corchetes []
  const frutas = ["manzana", "Banana", "Cereza"];
</pre>

2. Usando el constructor de arrays

<pre>
  // Creación de arrays utilizando el constructor
  const colores = new Array("Rojo", "Verde", "Amarillo");
</pre>

La diferencia entre estas dos maneras de declarar un array, reside en que:

- new Array(); Tiene problemas de legibilidad en el propio constructor. Por ej, si el primer parámetro que le pasas es un número, va a crear ese número de espacios vacíos, en vez almacenarlo en la posición 0.

- [/] (literal): Declara el dato literalmente que estes almacenando

---------------------------------------

## Acceder a los elementos de un Array

Si observamos los ejemplos anteriores, ya sea por corchetes o por el constructor de arrays, podemos intuir cual es la posición de cada elemento. Muchas veces es necesario consultar el estado de los datos que contiene un array, ya sea porque no los conocemos o porque fueron modificados. 
Para ello hay dos maneras en las cuales podemos acceder a los elementos de un array:

1. La primera es a través de la `posición o índice (index)`, colocando entre corchetes el número de la posición que representa un elemento dentro del array.

>**IMPORTANTE**: Todos los arrays comienzan desde la posición `0` (cero).

2. La segunda forma sirve más bien para saber cúantos elementos contiene un array, la manera en la cual vamos a saberlo es utilizando el método `length`.

<pre>
  //                0         1         2         3
  const frutas = ["Pera", "manzana", "Banana", "Cereza"];

  // Obtener la cantidad de elementos que posee un array
  console.log(frutas.length); // Devuelve como resultado 4

  // Acceder a un elemento del array por índice o posición
  console.log(frutas[2]); // Devuelve en consola "Banana"
</pre>

---------------------------------------

## Métodos de Array

Son funciones que poseen los array de forma nativa, con ellas seremos capaces de agregar, quitar, buscar, filtrar, modificar, cortar y muchas cosas más sobre los elementos de un array.

### Lista de Métodos más utilizados 

- .at() : Accede a un elemento del array por posición
- .unshift() : Agrega un elemento al principio de un array 
- .push() : Agrega un elemento al final del array
- .shift() : Quita un elemento al principio del array
- .pop() : Quita un elemento al final del array
- .map() : Crea un nuevo array aplicando una función
- .filter() : Crea un nuevo array con los que cumplen una condición
- .find() : Devuelve el primer elemento que cumple una condición
- .includes() : Verifica si un valor existe en el array
- .indexOf() : Devuelve el índice de un elemento (o -1 si no existe)
- .join() : Une todos los elementos en un string
- .sort() : Ordena el array (alfabéticamente o numéricamente)
- .reverse() : Invierte el orden del array
- .reduce() : Acumula los valores de un array
- .slice(start, end) : Devuelve los elementos desde la posición `start` hasta `end`. **Inmutable**
- .splice(start, size) : Altera el array, eliminando `size` (cantidad de elementos) desde posición `start`. **Mutable**
- .copyWithin(pos, start, end) : Altera el array, modificando desde `pos` copiando los ítems desde `start` hasta `end`. **Mutable**
  
<br>

---------------------------------------

### Método .at()

Permite acceder a un elemento del array de igual manera que usando corchetes.

<pre>
  //                0         1         2         3
  const frutas = ["Pera", "manzana", "Banana", "Cereza"];

  // Acceder a un elemento del array con corchetes
  console.log(frutas[2]); // Devuelve en consola "Banana"

  // Acceder a un elemento del array con el método .at()
  console.log(frutas.at(2)); // Devuelve en consola "Banana"
</pre>

---------------------------------------

### Recorrer los elementos de un array

Para recorrer los elementos de un array y ejecutar una acción para cada elemento del array, podemos utilizar el método `.forEach();`. Este método NO crea un nuevo array y NO puede detenerse hasta que termine de recorrer todos los elementos (a diferencia de `for` donde se puede utilizar la palabra reservada `break`.

- Detalles importantes:

  - No retorna un nuevo array (eso lo hace `.map();`).
  - El resultado de `.forEach();` siempre es `undefined`, osea que, no retorna nada.
  - No se puede utilizar `break` o `return` para salir del `.forEach();`. 

- Sintaxis básica 

<pre>
  // forEach con función anónima 
  array.forEach( function(elemento, indice, arrayOriginal) {
    // Código a ejecutar para cada elemento
  });

  // forEach con Arrow Function
  array.forEach( () => {
    // Código a ejecutar para cada elemento
  });
</pre>



1. elemento -> El valor actual que estás recorriendo
2. indice -> La posición del elemento dentro del array (opcional)
3. arrayOriginal -> El array completo que estás recorriendo (opcional)

<pre>
  const frutas = ["Pera", "manzana", "Banana", "Cereza"];

  frutas.forEach( (fruta) => console.log(fruta) );
  // Pera
  // manzana
  // Banana
  // Cereza
</pre>

---------------------------------------

### Agregar elementos en un array

En este caso tenemos los métodos `push(); y unshift();` para agregar elementos al inicio o al final del array

<pre>
  const frutas = ["Pera", "manzana", "Banana", "Cereza"];

  // Agregar elementos al inicio del array
  frutas.unshift("Kiwi");
  console.log(frutas); // ["Kiwi", "Pera", "manzana", "Banana", "Cereza"];

  // Agregar elementos al final del array
  frutas.push("Kiwi");
  console.log(frutas); // ["Pera", "manzana", "Banana", "Cereza", "Kiwi"];
</pre>

---------------------------------------

### Eliminar elementos de un array

Para eliminar los elementos de un array tenemos los métodos `pop(); y shift();`

<pre>
  const frutas = ["Pera", "manzana", "Banana", "Cereza"];

  // Eliminar elementos al inicio del array
  frutas.shift();
  console.log(frutas); // ["manzana", "Banana", "Cereza"];

  // Eliminar elementos al final del array
  frutas.pop();
  console.log(frutas); // ["Pera", "manzana", "Banana"];
</pre>

---------------------------------------

### Unir elementos de un array en una cadena (string)

Se puede lograr utilizando el método `.join();` este método se encarga de unir todos los elementos de un array y los convierte en un solo string, el parámetro que recibe es el carácter que vamos a utilizar para separar los elementos.

<pre>
  const frutas = ["Pera", "manzana", "Banana", "Cereza"];

  frutas.join(" - "); 

  console.log(frutas); // "Pera - manzana - Banana - Cereza"
</pre>

---------------------------------------

### Filtrar elementos de un array

Con el método `.filter();` podemos lograr esta acción, este método recibe un `callback` con la condición que deben cumplir los elementos que van a ser filtrados.

<pre>
  const prices = [125, 237, 58, 1920, 418];

  // Filtrar elementos que sean mayor o igual a 200
  prices.filter( (price) => >= 200;
  // [237, 1920, 418];
</pre>

---------------------------------------

### Modificar o crear arrays a partir de otros 

Hay situaciones en las que tenemos un array y queremos crear nuevos subarrays a partir
del original, o simplemente deseamos modificarlo para hacer ciertos cambios, pero de una
forma más general y no tener que hacerlo elemento a elemento.

- .slice(start, end); : Devuelve los elementos desde la posición `start` hasta `end`. **Inmutable**
- .splice(start, size); : Altera el array, eliminando `size` (cantidad de elementos) desde posición `start`. **Mutable**
- .copyWithin(pos, start, end); : Altera el array, modificando desde `pos` copiando los ítems desde `start` hasta `end`. **Mutable**

---------------------------------------

### Crear nuevos arrays a partir de una condición

El método `.map();` es un método muy potente y útil para trabajar con arrays, puesto que su
objetivo es devolver un nuevo array donde cada uno de sus elementos será lo que devuelva
la función callback por cada uno de los elementos del array original. **No modifica el array original**

<pre>
  const prices = [125, 237, 58, 1920, 418];

  prices.map( (price) => price *= 1.21);
  // Devuelve un array con todos los precios + el 21%
  // [151.25, 286.77, 70.17999999999999, 2323.2, 505.78]
</pre>

---------------------------------------

### Acumular los valores de un array

El método `.reduce();` se encarga de recorrer todos los elementos del array, e ir
acumulando sus valores (o alguna operación diferente) y sumarlo todo, para devolver su
resultado final.

<pre>
  const prices = [125, 237, 58, 1920, 418];

  prices.reduce( (total, price) => total + price, 0);
  // 2758

  /* la variable `total` toma el 0 como "valor inicial" y en cada iteración
  * se leva sumando el `price` actual hasta recorrer todo el array
  */
</pre>
