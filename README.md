Lab2 - Semáforos
================

Las Syscall's
-------------

Creamos el archivo `semaphore.h`. Definimos `MAX_SEMAPHORE` y el tipo de los
semáforos. Agregamos entradas en `Makefile` para que sea compilado.

Agregamos las siguientes funciones en `sysproc.c`:
    - `int sys_sem_init(void)`
    - `int sys_sem_close(void)`
    - `int sys_sem_up(void)`
    - `int sys_sem_down(void)`

Modificamos los siguientes archivos para terminar de crear las syscall's y
que puedan ser usadas en el espacio de usuario:
    - `syscall.c`
    - `syscall.h`
    - `sysproc.c`
    - `user.h`
    - `usys.S`

Barrier's
---------

Copiamos los archivos dados:
    - `barrier_init.c`
    - `barrier_echo.c`
    - `barrier_release.c`
    - `barrier_rise.c`

Agregamos entradas en `Makefile` para que sean compilados.

Pingpong
--------

Creamos el archivo `pingpong.c`

Agregamos entradas en `Makefile` para que sea compilado.

informe
-------

archivos donde estan definidos los siguientes programas

`spinylock.c` 
*acquire
*release

`sysproc.c`
*wakeup
*sleep

`syscall.c`
*sleep

descripción de las funciones

acquire

sólo se puede aplicar a las operaciones que se leen desde la memoria compartida, La operación se considera entonces una adquisición de lectura . La semántica de adquisición evita el reordenamiento de memoria con cualquier operación de lectura o escritura que lo siga en orden de programa hasta que se libere el bloqueo. Sirve para asegurarse de que las referencias de memoria de la sección crítica ocurren después de que se haya adquirido el bloqueo.

release

sólo puede aplicarse a las operaciones que escriben en la memoria compartida, ya sean operaciones de lectura o almacenamiento sencillos. La operación se considera entonces una liberación de escritura . La forma de liberación evita la reordenación de la memoria de escritura con cualquier operación de lectura o escritura que la precede en el orden del programa.

sleep

Es una llamada al sistema que hace que el proceso que lo llama se bloquee o desactive, es decir, que se suspenda hasta que otro proceso lo despierte.

wakeup

Tiene un parámetro, el proceso que se va a despertar o activar. De manera alternativa, Tanto sleep como wakeup tienen  un  parámetro,  una  dirección  de  memoria  que  se utiliza para asociar las llamadas a sleep con las llamadas a wakeup.

argint

Para buscar el argumento como un entero y luego comprueba si el entero está como un puntero de usuario es de hecho en la parte de usuario del espacio de direcciones, tambien lo guarda en la variable enviada como parametro.

zombie

En sistemas operativos Unix, un proceso zombi o "defunct" (difunto) es un proceso que ha completado su ejecución pero aún tiene una entrada en la tabla de procesos, permitiendo al proceso que lo ha creado leer el estado de su salida. El proceso hijo ha muerto pero su "alma" aún no ha sido recogida.

-&

En el kernel te permite llamar a otro proceso en vez de tener que esperar a que el proceso anterior termine.

__sync_synchronize ()

Esta función sincroniza los datos en todos los hilos. Se crea una barrera de memoria completa cuando se invoca esta función.

