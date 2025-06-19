# Asincronismo en JavaScript

Temario: 

- [Fundamentos](#fundamentos-del-asincronismo)

- [Single Thread](#cómo-funciona-el-single-thread-)

- [Call Stack](#call-stack)

- [Event Loop](#event-loop)

- [Callback Queue](#callback-queue)

---  

## Fundamentos del Asincronismo

*Asincronismo significa "no ocurre al mismo tiempo"*. El asincronismo es un paradigma de programación que permite que una tarea pueda
ejecutarse en segundo plano sin bloquear la ejecución del programa principal. En otras palabras, se pueden realizar varias tareas simultáneamente, sin necesidad de esperar a que una tarea se complete antes de comenzar la siguiente.

## Cómo funciona el Single Thread ?  

JavaScript dispone de lo que se llama *"Single Thread* - *Único Hilo"* de ejecución para el código de usuario. Por lo tanto, el asincronismo es la *"Estrategia de Diseño"* que se utiliza para mantener ese *Único Hilo*, ya que, la mayoría de los progamas hoy en día requieren de una respuesta o conexión externa para recibir diferentes tipos de datos o eventos, sin congelar la interfaz o ejecución del programa.  

Este Hilo, utiliza una estructura de datos llamada *"Call Stack"* y técnicas de asincronismo como *"Callbacks"* - *"Promises"* - *"Async / Await"*  junto con el mecanismo no bloqueante de código *"Event Loop"*.  

Cuando una función se manda a llamar, ésta se agrega en la Call Stack y se ejecuta de manera sincrónica, lo que significa que el programa va a tener que esperar hasta que esta función finalice las tareas que tenga asignadas para poder ejecutar la siguiente función. Si la función tarda mucho tiempo, puede hacer que el programa se bloquee y/o deje de funcionar.  
Por eso es necesario el uso de las funciones asincronicas para que estas "esperen" en segundo plano, mientras el programa se sigue ejecutando.  

Utilizando esta técnica, las funciones se colocan en una *"cola de tareas"* o mejor dicho *"Callback Queue"*, haciendo que esperen a las funciones sincrónicas se completen primero, y cuando la Call Stack queda vacía, se ejecuten las que quedaron en segundo plano esperando una respuesta de datos.  

Esto se logra mediante el uso del mecanismo NO bloqueante de código llamado *"Event Loop"* o también conocido como *"Bucle de Eventos"*, que se encarga de monitorear si la Call Stack y la Callback Queue tienen tareas para ejecutar, sin detener el Hilo (código principal).  

## Call Stack  

La *"Call Stack"* o también se le puede decir *"Pila de Llamadas"*, es una *Estructura de Datos* que mantiene un registro de las funciones que están siendo ejecutadas durante la ejecución del programa.  
Cuando una función *se llama a sí misma*, se agrega a la pila de llamadas. Cuando se completa la ejecución de esa función, se elimina de la pila de llamadas.  

![image](https://github.com/user-attachments/assets/6bc5ef4c-94c9-49e0-abb4-0c7430aefbe5)  


## Event Loop  

Básicamente, es un algorítmo que crea un ciclo, un bucle infinito en una función, que constantemente verifica si hay tareas pendientes o eventos en la Call Stack y en la Callback Queue del programa, si las hay, las va ejecutando en la Call Stack, permitiendo que el programa continúe respondiendo a nuevas acciones sin detenerse.

- Si la *"Call Stack"* está vacía, toma la primera función de la Callback Queue y la coloca en la pila para su ejecución.

- Si el *"Call Stack"* tiene tareas pendientes, espera a que se vacie antes de procesar la Callback Queue.  

![image](https://github.com/user-attachments/assets/8d5c805d-75be-4461-a376-4b3c846ee590)  


## Callback Queue

Las *Callback Queue* es una *Estructura de Datos (una cola FIFO: First In, First Out)* en JavaScript que se utiliza para almacenar las funciones callback que ya están listas para ser ejecutadas, pero esperan su turno para pasar por la *Call Stack*.

La Callback Queue no ejecuta código por sí misma, solamente lo almacena temporalmente hasta que el *Event Loop* los pase a la *Call Stack*.  


### Qué funciones van a la Callback Queue ?  


| Origen                                              | Va a la Callback Queue (Macrotask Queue) |
| --------------------------------------------------- | ---------------------------------------- |
| `setTimeout()`                                      | ✅                                        |
| `setInterval()`                                     | ✅                                        |
| `setImmediate()` *(solo Node.js)*                   | ✅                                        |
| Eventos del DOM (`click`, etc.)                     | ✅                                        |
| `fetch().then()` (pero el `.then()` va a otra cola) | ❌ (va a la *microtask queue*)            |
| `requestAnimationFrame()`                           | ❌ (va a una cola especial del navegador) |



Cuando se llama a una función en asincrónica en JavaScript, como por ejemplo una solicitud de datos a una fuente externa o una animación en el navegador, la función no se ejecuta de manera sincrónica.  
En su lugar, se coloca en una *Cola de Tareas* tambien llamada *Callback Queue* que espera a que se completen todas las tareas sincrónicas, una vez el Call Stack está vacío, el Event Loop se encarga de ejecutar las funciones que estan en la Callback Queue en el orden que fueron llegando o ejecutandose cada función.  

Un ejemplo común, es cuando se realiza una consulta a una API externa (Fuente de Datos). Cuando se realiza dicha solicitud, el programa no espera a que esta acción se complete, la agrega a la Callback Queue para que se ejecute en segundo plano con el Event Loop, una vez finalizada la ejecución en segundo plano y obtenida la respuesta lo agrega a la Call Stack.  



