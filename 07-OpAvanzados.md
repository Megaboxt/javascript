# Operadores Avanzados (`Operadores de Expansión` y `Destructuring`)

Los Operadores Avanzados son herramientas que te permiten hacer operaciones más complejas o expresivas en JavaScript.  
Digamos que son como la evolución de los Operadores Básicos como `+`, `-`, `*`, `/`, etc.  

## Operadores de Expansión - (`...`)  

El operador `...` tiene dos usos diferentes:

- `Spread`: propaga o expande un array u objeto, es decir, puede copiar o combinarlos.

- `Rest`: agrupa o recoge un array u objeto.


<pre>
  /* Spread Operator */

  // en arrays
  const arr1 = [1, 2, 3];
  const arrOP = [...arr1, 4, 5, 6];

  // en objetos
  const base = { nombre: "Megaboxt", edad: 33 };
  const copiaBase = { ...base, ciudad: "Córdoba" };

  // en argumentos de funciones
  function saludar(nombre, edad) {
    console.log(`Hola, ${nombre}, tenés ${edad} años.`);
  }
  const datos = ["Lucia", 29];
  saludar(...datos); // Desarma el array y pasa sus elementos como parámetros.

  
  console.log(arrOP); // [1, 2, 3, 4, 5, 6]
  console.log(copiaBase); // { nombre: "Megaboxt", edad: 33, ciudad: "Tierra del Fuego" }


  /* Rest Operator */

  // en funciones, junta todos los números que son pasados como argumentos
  function sumar(...numeros) {
    return numeros.reduce( (a,b) => a + b, 0 );
  }

  // En destructuring de objetos
  const { nombre, ...resto } = { nombre: "Megaboxt", edad: 33, ciudad: "Tierra del Fuego" };

  // En destructuring de arrays 
  const [primero, ...resto] = [10, 20, 30];
  

  console.log(sumar(1,2,3,4)); // 10

  console.log(nombre); // Megaboxt
  console.log(resto); // { edad: 33, ciudad: "Tierra del Fuego" }

  console.log(primero); // 10
  console.log(otros);   // [20, 30]  
</pre>  



  
## Destructuring  

La desestructuración (destructuring) permite extrar valores de `arrays` u `objetos` y asignarlos a variables individuales de una forma más clara y concisa. Esto evita la necesidad de acceder a los valores mediante índices o claves repetidamente.  


<pre>
  const persona = {
    nombre: "Ana",
    edad: 30,
    pais: Argentina
  }

  const { nombre, edad } = persona;

  // Renombrar Propiedad
  const { nombre: nombreCompleto } = Persona;

  // Declarar valor por defecto
  const { ciudad = "Desconocido" } = Persona;
  
  console.log(nombre); // Ana
  console.log(edad); // 30

  console.log(nombreCompleto); // Ana

  console.log(ciudad); // Desconocido
</pre>  

  
Cómo funciona este bloque ?  

- Se crea un Objeto llamado `Persona` con 3 propiedades declaradas dentro `nombre`, `edad`, `pais`.

- Se declaran entre llaves `{ ... }` las variables `nombre` y `edad`, que se crean refiriendose a las propiedades del objeto creado.

- Se puede renombrar la propiedad de un Objeto como se puede ver en el ejemplo, sin que pierda la referencia del dato.

- Tambien se puede declarar una nueva propiedad con un valor por defecto en el Objeto.  


### Desctructuring en Arrays  

<pre>
  const numeros = [10, 20, 30, 40];

  // Basado en las posiciones del array
  const [a, b] = numeros;

  // Saltar posiciones (Array directo)
  const [ , segundo, tercero] = [1, 2, 3, 4];

  // Usar `rest` en arrays
  const [primero, ...resto] = [4, 5, 6, 7];

  console.log(a); // 10
  console.log(b); // 20

  console.log(tercero); // 3
  console.log(segundo); // 2 

  console.log(primero); // 4
  console.log(resto); // [5, 6, 7]
</pre>  
