# Classes  

JavaScript es un lenguaje multiparadigma, lo que significa que soporta diferentes metodologías de programación, como la `Programación Imperativa` (estados, mutaciones, estructuras de control, etc.), la `Programación Funcional` (uso de funciones) y la `Programación Orientada a Objetos (POO)` (uso de objetos, encapsulamiento, herencia, polimorfismo, etc.)  

La Programación Orientada a Objetos o `POO` se basa en la creación de `Classes` que definen las propiedades y comportamientos (métodos) de subclasses o classes hijas que heredan estas definiciones.  

La manera de crear classes en lenguajes basados enteramente en el uso de `POO`, es a través de la palabra reservada `class`. Con la intención de atraer programadores de estos lenguajes hace algunos años se implementó al estándar de EcmaScript la `Sugar Syntax` necesaria para contar con esta opción. 

>NOTA: La `Sugar Syntax` es una forma más simplificada y legible de escribir código, que enmascara una implementación más compleja sin cambiar su funcionalidad subyacente.

---

## Estructura básica de una Class

<pre>
  class Persona {
    constructor(nombre, edad) {
      this.nombre = nombre;
      this.edad = edad;
    }

    saludar() {
      console.log(`Hola! mi nombre es ${this.nombre} y tengo ${this.edad} años.`);
    }
  }
</pre>


### Desglose de la estructura de la Clase:

- Persona (el nombre de la clase): Puedes ponerle cualquier nombre, pero por convención, se escribe la primera letra en mayúsculas, para distinguirlo de funciones normales.  

- {...} (Llaves de la clase): Todo lo que definimos dentro de la clase (como variables y funciones) va dentro de las llaves `{}`.  

- constructor(...): Esta es una función especial que se ejecuta automáticamente cuando creamos un nuevo objeto con esta clase. Por ejemplo:

<pre>
  constructor(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
  }
</pre>

Cómo funciona este bloque ?  

* constructor: Palabra reservada.  

* (nombre, edad): Son parámetros, es decir, los valores que se le pasan cuando se crea una nueva "Persona".  

* `this.nombre = nombre` significa:
    * `this.nombre` se refiere a la propiedad del objeto que estamos creando.
    * `nombre` (sin `this`) es el parámetro que recibimos.
    * De esa manera guardamos ese valor dentro del objeto.
 
* `this`: Es una palabra especial en JS. Que se utiliza para hacer referencia al **Objeto Actual** que se esta construyendo o usando.
