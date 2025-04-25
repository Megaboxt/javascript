# Funciones 

Es un concepto fundamental de la programación, ya que nos permite crear algoritmos que encapsulan determinadas acciones, funcionalidades o lógica que necesitemos reutilizar. Estas se pueden mandar a llamar (invocar) en cualquier momento para que ejecute las tareas.

Esta herramienta no solo pertenece a JavaScript, sino más bien a los lenguajes de programación en general, aunque cada uno tenga distintas maneras de declararlas.

## Declaración de una Función en JS

En JS tenemos varias formas para crear una función, las funciones **Declarativas**, las funciones **Expresadas** y las **Arrow Functions**.


- Funciones Declarativas:

<pre>
function search() {
  // proceso encapsulado
}
</pre>

*Se utiliza la palabra reservada **function** seguido del nombre por el cual se la va a mandar a llamar o invocar, seguido de parentesis en donde se pueden agregar parámetros, seguido de llaves las cuales se encargan de envolver el código que va a ejecutar la función.*

- Funciones Expresadas:

<pre>
  const search = function () {
    // proceso encapsulado
  }
</pre>

*En este caso la función es **anónima** (sin nombre) y se guarda dentro de una variable o una constante tradicional*

> Puedes reemplazar `javascript` con cualquier lenguaje para coloreado: `python`, `bash`, `json`, `html`, etc.
