# Operadores Avanzados (`Destructuring` y `Spread Operator`)

Los Operadores Avanzados son herramientas que te permiten hacer operaciones más complejas o expresivas en JavaScript.  
Digamos que son como la evolución de los Operadores Básicos como `+`, `-`, `*`, `/`, etc.  

## Destructuring  

La desestructuración (destructuring) permite extrar valores de `arrays` u `objetos` y asignarlos a variables individuales de una forma más clara y concisa.  


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

### Renombrar propiedades  

Son útiles si ya hay una variable con el mismo nombre y querés usar un nombre más claro.

<pre>
  
</pre>

