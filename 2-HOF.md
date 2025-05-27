# High Order Functions (Funciones como argumentos)

### ¿Qué son las Funciones de Orden Superior ?

Tambien conocidas como "Callbacks", representan una función que puede tomar otra función como argumento/parametro, o devolver otra función como resultado, o ambas. Es decir, pasamos una función B como parámetro en una función A, pudiendo definirlas inclusive, desde fuera de dicha función.

<pre>
  function sumar(num1, num2) {
    return a + b;
  }

  function restar(num1, num2) {
    return a - b;
  }

  function calcular(num1, num2, operacion) {
    return operacion(num1, num2);
  }

  console.log(calcular(10, 5, sumar); // 15
  console.log(calcular(10, 5, restar); // 5
</pre>


En el ejemplo, creamos una función llamada calcular(), que espera 3 parámetros, 2 valores y 1 función. De esta manera, esta función se encarga de ejecutar internamente la operación(función) recibida como parámetro.

Por este comportamiento nace el famoso nombre "callback", ya que el anidado de funciones con este tipo de acciones nos permite encadenar la ejecución de una función detras de otra.












