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

- { ... } (Llaves de la clase): Todo lo que definimos dentro de la clase (como variables y funciones) va dentro de las llaves `{}`.  

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
 
- `this`: Es una palabra especial en JS. Que se utiliza para hacer referencia al **Objeto Actual** que se esta construyendo o usando.

- saludar() { ... } (Es un método): Esto es una función dentro de la clase, también llamada método. Se comporta como una función normal, pero pertenece a la clase.  

## Cómo utilizamos esta Class ?

Creamos una variable que genere una nueva instancia para crear el objeto, utilizando la palabra reservada `new` y almacenamos los datos que toma como parámetros dentro de los paréntesis `()`.  
Luego con esa variable podemos acceder a los métodos que contiene la Class.  

<pre>
  const persona1 = new Persona("Megaboxt", 33);
  persona1.saludar(); // Hola! mi nombre es Megaboxt y tengo 33 años.
</pre>  

---  

## Herencia - (`extends` y `super`)  

La herencia permite que una Clase herede propiedades y métodos de otra Clase.  

Supongamos que de la Clase `Persona` queremos crear una Clase `Estudiante` que sea como una persona, pero con propiedades adicionales.  

<pre>
  class Estudiante extends Persona {
    constructor(nombre, edad, curso) {
      super(nombre, edad); // Invoca el constructor de la clase Persona
      this.curso = curso;
    }

    estudiar() {
      console.log(`${this.nombre} está estudiando ${this.curso} ...`);
    }
  }
</pre>  

Cómo funciona este bloque ?  

- `extends`: Palabra reservada que indica que una clase `hereda de otra`.

- `super(...)`: Es una `función especial` que es necesaria para llamar al constructor de la clase padre (en este caso, `Persona`).  

---  

## Métodos Estáticos - (`static`)

Los métodos estáticos permiten invocarse directamente desde la clase en sí, sin necesidad de crear una nueva instancia dado que justamente son "estáticos", no se pueden modificar.  

<pre>
  class ConversorDeTemperatura {
    
    static celsiusAFarenheit(celsius) {
      return (celsius * 9/5) + 32;
    }

    static FarenheitACelsius(fahrenheit) {
      return (fahrenheit - 32) * 5/9;
    }
  
  }

  console.log(ConversorDeTemperatura.celsiusAFahrenheit(0));  // 32
  console.log(ConversorDeTemperatura.fahrenheitACelsius(212)); // 100
</pre>  

Cómo funciona este bloque ?  

* Creamos una clase llamada `ConversorDeTemperatura`.

* Dentro de la clase creamos los métodos estáticos `celsiusAFarenheit` y `FarenheitACelsius`.  


---  


## Getters y Setters - (`get` y `set`)  

Son métodos especiales que se usan para leer o cambiar valores de una forma más controlada.  

- Getter (`get`): Lee un valor de forma controlada. Como si fuera una propiedad, pero puede ejecutar código internamente.

- Setter (`set`): Escribe un valor convalidación o procesamiento antes de modificarlo.

Estos métodos son útiles porque te permiten modificar o acceder a las propiedades de una manera más controlada.  


<pre>
  class CuentaBancaria {
    constructor (titular, saldoInicial) {
      this.titular = titular;
      this.saldoInicial = saldoInicial;
    }

    // GETTER - leer el saldo
    get saldo() {
      return this._saldo.toFixed(2) + " USD";
    }

    // SETTER - modificar saldo
    set saldo(nuevoSaldo) {
      if (nuevoSaldo < 0) {
        console.log("No se puede establecer un saldo negativo");
      } else {
        this._saldo = nuevoSaldo;
      }
    }
  }

  const cuenta = new CuentaBancaria("Juan", 500);

  console.log(cuenta.saldo); // "500.00 USD"

  cuenta.saldo = 1000;       // Cambiamos el saldo
  console.log(cuenta.saldo); // "1000.00 USD"

  cuenta.saldo = -200;       // Intentamos un valor inválido
  // No se puede establecer un saldo negativo.

  console.log(cuenta._saldo); // Se puede acceder, pero no deberías hacerlo directamente...
</pre>  

Cómo funciona este bloque ?  

- `this._saldo`: Usamos `_saldo` como una convención, significa que no deberíamos accederlo directamente desde fuera. No es realmente privado, pero indica que NO debe ser modificado.

- `get_saldo()`: Permite que se lea el saldo como si fuera una propiedad.

- `set saldo(nuevoSaldo)`: Permite que se modifique el saldo, pero con una validación (no puede ser menor a cero).  


---  

## Propiedades Privadas - (`#` Encapsulamiento)

Sirve para ocultar datos que contienen información "sensible o interna" (contraseñas, tokens, configuraciones internas, etc.) y que no puedan ser accedidos o modificados directamente desde afuera de la clase.  

A partir de ES2022, se puede utilizar `#` para definir variables privadas.  

<pre>
  class Usuario {
    #contraseña;

    constructor (nombre, contraseña) {
      this.nombre = nombre;
      this.#contraseña = contraseña;
    }

    verificarContraseña(intento) {
      return intento === this.#contraseña;
    }
  }

  const user = new Usuario("admin", "secreta");

    
  console.log(user.nombre); // admin
  console.log(user.#contraseña); // Error: no se puede acceder
  console.log(user.verificarContraseña("secr")); // false
  console.log(user.verificarContraseña("secreta")); // true
</pre>
