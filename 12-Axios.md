# Qué es Axios ?

*Es una librería HTTP basada en Promesas construida sobre `XMLHttpRequest`*, que permite hacer más fácilmente peticiones a servidores, API's, etc.  

### Características principales  

- Basado en Promesas - compatible con `Async/Await`.

- Interfaz simple para peticiones HTTP (GET, POST, PUT PATCH, DELETE).

- Automáticamente transforma respuestas JSON.

- Permite manejar headers o errores globales.

- Soporta la cancelación de peticiones, tiempos de espera, etc.

## Instalación  

Ya que es una biblioteca, se debe descargar con el comando `NPM` de Node.js

    npm install axios


--- 

    import axios from 'axios';

    axios.get('https:/api.example.com/data')
      .then( response => console.log(response.data))
      .catch( error => console.error(error.message))
