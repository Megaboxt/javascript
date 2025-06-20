# Promesas en JavaScript

Las promesas son la forma moderna de manejar el asincronismo en JavaScript. *Una promesa es un Objeto que representa el resultado eventual de una tarea asíncrona*.  
El resultado eventual puede ser un valor o un error. Es por eso que las promesas cuentan con dos estados finales: `Resolved` y `Rejected`.  

Cualquiera de los 2 estados que vaya a tomar la función, se va a definir al momento de crear la *Promesa* para indicar si el proceso fue *exitoso* o *erróneo*.

Para poder recuperar el resultado de una *Promesa* se utilizan los métodos `.then()`, `.catch()` y `.finally()`.
