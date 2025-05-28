# Classes  

JavaScript es un lenguaje multiparadigma, lo que significa que soporta diferentes metodologías de programación, como la `Programación Imperativa` (estados, mutaciones, estructuras de control, etc.), la `Programación Funcional` (uso de funciones) y la `Programación Orientada a Objetos (POO)` (uso de objetos, encapsulamiento, herencia, polimorfismo, etc.)  

La Programación Orientada a Objetos o `POO` se basa en la creación de `Classes` que definen las propiedades y comportamientos (métodos) de subclasses o classes hijas que heredan estas definiciones.  

La manera de crear classes en lenguajes basados enteramente en el uso de `POO`, es a través de la palabra reservada `class`. Con la intención de atraer programadores de estos lenguajes hace algunos años se implementó al estándar de EcmaScript la `Sugar Syntax` necesaria para contar con esta opción. 

>NOTA: La `Sugar Syntax` es una forma más simplificada y legible de escribir código, que enmascara una implementación más compleja sin cambiar su funcionalidad subyacente.

---

## Creando una Class

<pre>
  class User {
    constructor(name, email, password) {
      this.name = name;
      this.email = email;
      this.password = password;
    }

    login(inputEmail, password)
  }
</pre>
