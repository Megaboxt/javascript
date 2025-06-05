# Fetch API de JS - `fetch()`

La Fetch API es una interfaz moderna de JavaScript que permite realizar solicitudes HTTP (y otras) de forma asíncrona, reemplazando en muchos casos a XMLHttpRequest.  

Es nativa en los navegadores modernos y usa promesas, lo que facilita el manejo de operaciones asincrónicas.  

## Sintáxis básica de `fetch()`  

<pre>
  fetch(url, opciones) 
    .then( respuesta => respuesta.json() ) 
    .then( data => { 
      // código para trabajar con datos
    }) 
    .catch( error => { 
      // código para manejar errores
    })
</pre>

- Desglose del código ilustrado

| Parte                      | Significado                                                                                    |
| -------------------------- | ---------------------------------------------------------------------------------------------- |
| `url`                      | La URL del recurso que queremos solicitar.                                                     |
| `opciones`                 | (Opcional) Un objeto que contiene configuración para el método HTTP, encabezados, cuerpo, etc. |
| `.then(res => res.json())` | Convierte la respuesta a JSON.                                                                 |
| `.catch()`                 | Manejo de errores de red o ejecución.                                                          |
