# Promesas en JavaScript

Las promesas son la forma moderna de manejar el asincronismo en JavaScript. *Una promesa es un Objeto que representa el resultado eventual de una tarea asíncrona*.  
El resultado eventual puede ser un valor o un error. Es por eso que las promesas cuentan con dos estados finales: `Resolved` y `Rejected`.  

Cualquiera de los 2 estados que vaya a tomar la función, se va a definir al momento de crear la *Promesa* para indicar si el proceso fue *exitoso* o *erróneo*.

### Cómo se crea una Promesa ?  

Para poder crear una promesa tenemos que utilizar el constructor `new Promise(...)`. Y para poder recuperar el resultado de una *Promesa* se utilizan los métodos `.then()`, `.catch()` y `.finally()`.  
También existen atajos para obtener solamente el valor o el error del resultado eventual `Promise.resolve(...)` y `Promise.reject(...)`.  



    function tareaAsincrona() {
      console.log("Ejecutando tarea asincrona...");
  
      return new Promise((resolve, reject) => {
          setTimeout(function () {
              if (Math.random() < 0.5) {
                  resolve('Tarea asíncrona realizada')
          } else {
              reject(new Error('Tarea asíncrona fallida.'))
          }
          }, 3000);
      });
    }


### Explicación del código  

En el ejemplo, creamos una función llamada `tareaAsincrona()` y devuelve una promesa que se resuelve después de 3 segundos.

- `new Promise(...)`: recibe como argumento una *Función Ejecutora* que se ejecuta inmediatamente al crear la Promesa. Esa función recibe 2 funciones callback:
  - `resolve(valor)`: se ejecuta en caso de obtener un valor correcto.
  - `reject(error)`: indica que la promesa falló.

- `setTimeout( () => {...}, ms )`: función para simular un tiempo de espera.

- Se declara un condicional `if` en el cual se declara un `Math.random()` para que, en caso de que salga un número menor a 5, la promesa pueda fallar.



### Ejecutar la Promesa  

Al momento de ejecutar la función que contiene la Promesa, *tenemos que recuperar de alguna manera el resultado*, si lo asignamos a una variable el programa va a leer la línea de código y le va a asignar un estado de `Promise { <pending> }` ya que la ejecución del código asíncrono sigue corriendo y por lo tanto no ha finalizado.


    const result = tareaAsincrona();

    console.log(result); // Promise { <pending> }

Es por eso que se deben utilizar los métodos anteriormente mencionados para poder recuperar los valores o los errores de la Promesa

    console.log("Ejecutando tarea asincrona...");

    tareaAsincrona()
      .then( resultado => console.log(resultado) )
      .catch( error => console.log(error) )
      .finally( () => console.log("Tarea asíncrona terminada.") )


  - `.then()`: establece qué debe suceder una vez que la promesa se resuelve con éxito.

  - `.catch()`: determina que sucederá si la promesa falla.

  - `.finally()`: este método es opcional y se llama al finalizar cualquiera de los dos anteriores, independientemente de si la promesa se resuelve o se rechaza.

>NOTA: El método `.catch()` también es opcional, pero en caso de que la función falle no obtendremos un resultado válido o esperado.
>Por eso es recomendable utilizarlo siempre para poder obtener un valor de error y saber donde reside y decidir qué hacer con él.

