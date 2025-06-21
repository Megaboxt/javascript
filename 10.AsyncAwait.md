# Async & Await  

Esta es una forma aun más moderna de realizar el asincronismo en JavaScript, digamos un *Sugar Syntax* basado en las Promesas. No es un nuevo método, sino una forma más cómoda de escribir código que usa Promesas.

### Para qué sirven ?  

- Para evitar el uso excesivo de `.then()`, `.catch()` y `.finally()`.  

- Siempre es recomendable usarlas dentro de un bloque `try/catch` que nos permite ejecutar cualquier "pieza" de código dentro del `try` y capturar un fallo mediante el `catch`.

- Mejora la claridad, la depuración y la lógica secuencial.

### Cómo se utiliza `async/await` ?  

- `async` Marca una función como asíncrona, cualquier función declarada con async siempre devuelve una Promesa.

- `await` Espera a que una Promesa se resuelva. Solo puede usarse dentro de una función marcada con `async`. Detiene temporalmente la ejecución de esa función hasta que la Promesa se resuelva, retornando el valor resuelto o lanza el error rechazado.  


<pre></pre>
    async function ejecutarTareaAsincrona() {
        console.log("Ejecutando tarea con async");
        
        try {
            const resultado = await tareaAsincrona();
    
            console.log(resultado);
            
        } catch (error) {
            console.log(`Hubo un error: ${error.message}`);
        } finally {
            console.log("Fin de la Tarea con async");
            
        }
    }
    
    ejecutarTareaAsincrona();
