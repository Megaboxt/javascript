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

## Event Loop  

Básicamente, es un ciclo infinito (función) que constantemente verifica si hay tareas pendientes (eventos) en la Call Stack y en la Callback Queue, si las hay, las va ejecutando en la Call Stack, permitiendo que el programa continúe respondiendo a nuevas acciones sin detenerse.

- Si la *"Call Stack"* - *"Pila de Llamdas"* está vacía, toma la primera función de la Callback Queue y la coloca en la pila para su ejecución.

- Si el *"Call Stack"* tiene tareas pendientes, espera a que se vacie antes de procesar la Callback Queue.

## Callback Queue
