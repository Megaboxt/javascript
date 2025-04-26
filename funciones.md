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
  
  resta(); // 10
</pre>

*Al utilizar la sentencia `resta();` nos permite ejecutar el código interno dentro de la función, **retornando** el resultado el cual podríamos guardarlo dentro de una nueva variable.*

>**IMPORTANTE**: Si utilizamos solamente `resta` sin los paréntesis estaríamos haciendo solamente `Referencia a la función`, lo cual sirve para casos en donde se podria pasar como parámetro en un callback.

<pre>
saludar => Referencia a la función
saludar() => Llamada/ejecución de la función 
</pre>

---

## Palabra reservada RETURN

