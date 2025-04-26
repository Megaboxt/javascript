# Funciones 

Es un concepto fundamental de la programación, ya que nos permite crear algoritmos que encapsulan determinadas acciones, funcionalidades o lógica que necesitemos reutilizar. Estas se pueden mandar a llamar (invocar) en cualquier momento para que ejecute las tareas.

Esta herramienta no solo pertenece a JavaScript, sino más bien a los lenguajes de programación en general, aunque cada uno tenga distintas maneras de declararlas.

## Declaración de una Función en JS

En JS tenemos varias formas para crear una función, las funciones `Declarativas`, las funciones `Expresadas` y las `Arrow Functions`.

- Funciones Declarativas:

<pre>
  function search() {
    // proceso encapsulado
  };
</pre>

*Se utiliza la palabra reservada **function** seguido del nombre por el cual se la va a mandar a llamar o invocar, seguido de parentesis en donde se pueden agregar parámetros, seguido de llaves las cuales se encargan de envolver el código que va a ejecutar la función.*

---

- Funciones Expresadas:

<pre>
  const search = function () {
    // proceso encapsulado
  };
</pre>

*En este caso la función es **anónima** (sin nombre) y se guarda dentro de una variable o una constante tradicional.*

> La diferencia fundamental entre las funciones `Declarativas` y `Expresadas`, es que las `Expresadas` sólo están disponibles a partir de la inicialización de la variable. Si ejecutamos la variable antes de declararla, nos va a arrojar error.

---

- Arrow Functions:

Introducidas al lenguaje a partir de la especificación `ES6`, son otra forma de declarar funciones y hoy juegan un papel importante a la hora de escribir programas de JavaScript Moderno.

Para declarar un Arrow Function se utiliza la siguiente sintaxis:

<pre>
  const resta = () => { /* Tarea o proceso */ };
</pre>

*Podemos notar que es similar a la función `Expresada` solo que omitimos la palabra reservada `function` y luego de los paréntesis colocamos una "flecha" compuesta por los caracteres `=` y `>` seguido de llaves.*

>**OPCIONAL**: En caso de que la función solamente sea de una sola línea de código, se pueden quitar las llaves y quedaría un `return` implícito.

<pre>
  /* return Implícito */
  const resta = () => 20 - 10;
</pre>

<pre>
  /* return Explícito */
  const resta = () => {
    const resultado = 20 - 10;

    return resultado;
  };
</pre>

---

## Invocar Funciones

Una vez declarada la función, para poder utilizarla debemos `Invocarla`. Para ello, escribiremos el nombre de la función seguido de paréntesis.

<pre>
  function resta() {
    return 20 - 10;
  }
  
  console.log(resta()); // Ejecuta la función y retorna el resultado (en este caso 10)
  console.log(resta); // Devuelve literalmente como está compuesta la Función
</pre>

*Al utilizar la sentencia `resta();` nos permite ejecutar el código interno dentro de la función, **retornando** el resultado el cual podríamos guardarlo dentro de una nueva variable.*

>**IMPORTANTE**: Si utilizamos solamente `resta` sin los paréntesis estaríamos haciendo solamente `Referencia a la función`, lo cual sirve para casos en donde se podria pasar como parámetro en un callback.

<pre>
saludar => Referencia a la función
saludar() => Llamada/ejecución de la función 
</pre>

---

## Palabra reservada RETURN

Existen casos donde nuestras funciones deben ejecutar cierto proceso sin necesidad de
devolver un resultado, como por ejemplo en la WEB al querer borrar un elemento de nuestro
HTML que ya no necesitamos o cuando queremos imprimir un valor en la consola de la
terminal, sin embargo en la mayoría de los casos nuestras funciones abstraen o guardan
comportamientos que finalmente retornan un dato que tendrá que ser utilizado en otra parte
de nuestro código, como por ejemplo el resultado de la resta de 2 valores.

*Para capturar nuevamente ese valor que resulta de la ejecución de la función debemos
utilizar la palabra reservada `return` antes del valor a devolver.*

Ese valor se puede guardar en una variable para ser utilizado más adelante o implementarlo
directamente desde la invocación de la función en otra parte del código que así lo permita.

<pre>
  function resta() {
    return 20 - 10;
  }

  const resultado = resta();

  // Imprimimos en consola el resultado
  console.log(resultado);
</pre>

>**NOTA**: En los casos donde una función no posee la sentencia `return`, se considera que es del
tipo `void` o `vacío`, es decir, que solamente ejecuta el código interno pero no devuelve
ningún resultado.

**En resumen** 
<br>
<br>
La palabra clave return se usa dentro de una función para:

1. Finalizar inmediatamente la ejecución de la función.

2. Devolver un valor al lugar donde se llamó la función.

---

## Parámetros y argumentos

Un parámetro es una variable que se define dentro de los parentesis de la función, para indicarle que al momento de ser invocada se deberá pasar un valor en esa posición para luego ser utilizado dentro de la misma función.

Cuando invocamos la función, el valor literal que le pasamos para que ocupe el lugar del `parámetro` es conocido como `argumento`.

Para poner los términos claros:

- Un `parámetro` es una especie de "lugar reservado" que espera un valor. Al momento de crear la función, debemos saber cuántos parámetros vamos a esperar o necesitar y colocarlos dentro de los paréntesis separando cada uno de ellos por una coma, siendo que no existe una cantidad límite de parámetros permitidos.

- Un `argumento` es el `valor` que pasamos dentro del paréntesis cuando invocamos la función. Tener en cuenta que el valor que queramos pasar, respeta cada posición de los parámetros definidos.

<pre>
  // Creamos una función que toma 2 parámetros
  const suma(num1, num2) {
    const resultado = num1 + num2;
    return resultado;
  };

  // Invocamos la función declarada y le pasamos los valores (argumentos)
  suma(20, 10);
</pre>
