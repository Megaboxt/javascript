# Matrices

Las matrices son un caso específico de Array, concretamente de dos dimensiones.
Se organizan en filas y columnas, formando una estructura rectangular.
En programación, las matrices se utilizan comúnmente para representar imágenes, tablas o datos organizados en un formato rectangular.

En resumen, una matriz es simplemente un array que contiene otros arrays.

Para declarar una matriz, podemos emplear la siguiente estructura:

<pre>
  const matriz = [
    [1,2,3],
    [4,5,6],
    [7,8,9]
  ]
</pre>


>Esta matriz tiene **3 filas y 3 columnas**.  
>Puedes acceder a los elementos con dos índices: `matriz[fila][columna]`.


### Métodos útiles en Matrices

Se pueden utilizar los siguientes métodos para recorrer o verificar matrices:

- Array.prototype.map() : Recorre los elementos y crea una copia.
- Array.prototype.flat() : Crea un Array unidimensional.
- Array.prototype.reduce() : Crea un Array unidimensional acumulando los arrays internos en uno solo.
- Array.isArray() : Verifica si es un Array.
- .length : Obtiene el número de filas o columnas.
