# Fetch - Consumiendo Datos Externos  

Fetch es una API nativa de JavaScript presente tanto del lado del *browser (navegador)* como del lado del servidor con Node.js, que se utiliza para hacer *Solicitudes HTTP* a servidores web de manera asíncrona.  
Se considera como una alternativa a la API *XMLHttpRequest* que se utilizaba anteriormente para interactuar con los servidores, es decir, es el reemplazo a la manera tradicional de realizar peticiones `AJAX`.  

Utiliza Promesas para manejar las *solicitudes* y las *respuestas*.  

Una solicitud Fetch se realiza utilizando la función global `fetch()`. Esta función devuelve una promesa que se resuelve con una respuesta *HTTP* cuando se recibe una respuesta del servidor.  

### Sintáxis básica de `fetch()`  


    fetch(url, opciones) 
      .then( respuesta => respuesta.json() ) 
      .then( data => { 
        // código para trabajar con datos
      }) 
      .catch( error => { 
        // código para manejar errores
      })

- Desglose del código ilustrado

| Parte                      | Significado                                                                                    |
| -------------------------- | ---------------------------------------------------------------------------------------------- |
| `url`                      | La URL del recurso que queremos solicitar.                                                     |
| `opciones`                 | (Opcional) Un objeto que contiene configuración para el método HTTP, encabezados, cuerpo, etc. |
| `.then(res => res.json())` | Convierte la respuesta a JSON.                                                                 |
| `.catch()`                 | Manejo de errores de red o ejecución.                                                          |



## Cargando Datos de un Servidor  

Un ejemplo común de Fetch es la carga de datos de un servidor para mostrar en una página web. El siguiente ejemplo es una solicitud básica que obtiene los datos de un servidor y los convierte en formato `JSON`  

    fetch('https:/example.com/data.json')
      .then( response => response.json())
      .then( data => console.log(data))

El uso del método `.json()` en el primer *then* conviete la respuesta del servidor en datos con formato JSON válido.  

### Otras funcionalidades de Fetch

- Configuración avanzada: Se pueden personalizar las solicitudes agregando un Objeto de configuración. Por ejemplo, configurar los encabezados HTTP, enviar datos en el cuerpo de una solicitud POST o definir el método HTTP.

- Soporte para cookies y autenticación: Usando la opción `credentials`, Fetch te permite manejar cookies o enviar credenciales entre dominios.  

<pre></pre>
    const opciones = {
        method: "POST",
        headers: {
            "Content-Type": "application/json",
            "Authorization": "Bearer token",
        },
        body: JSON.stringify( {key: "value"} )
    }
    
    
    fetch('https:/example.com/data.json', opciones)
        .then( response => response.json())
        .then( data => console.log(data))
        .catch( error => console.log(`Hubo un error: ${error.message}`) )


Aunque Fetch es una herramienta nativa, existen bibliotecas de terceros como `Axios` que ofrecen una experiencia más completa y sencilla para realizar solicitudes HTTP.
