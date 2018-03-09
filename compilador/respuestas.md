1. Escriban qué esperan de cada uno de los pasos
Rta. En el primer paso (make preprocessing), el pre-procesador 
genera un archivo en lenguaje C en el cual declara todas las 
funciones que se utilizan. 
El segundo paso (make assembler) "traduce" el archivo generado
por el pre-procesador a lenguaje Assembler. El archivo de salida 
*.asm ya no está en lenguaje C.
El tercer paso (make object) genera un archivo que tiene todo
pasado a lenguaje de máquina.
El último paso (make executable) construye el archivo ejecutable
que realiza la tarea requerida.

2. ¿Qué agregó el preprocesador?
Rta. El pre-procesador agrega una extensa cantidad de líneas arriba del
código del programa propiamente dicho, en las cuales incluye todas las
librerías que requiere el programa. 

3. Identificar en la rutina de assembler las funciones
Rta. Las funciones son 'main', 'add_numbers' y printf. En el archivo de 
Assembler las dos primeras tienen la etiqueta @function. A printf directamente
la llama con 'call'

4. Explicar qué quieren decir los símbolos que se crean en el objeto
Rta. Los símbolos que aparecen son 'T main', 'T add_numbers' y 'U printf'. El
descriptor T significa 'texto', que es una manera de decir
'código ejecutable'. La mayúscula significa que un objeto puede acceder a
esa función aunque pertenezca a otro objeto. Es decir, la mayúscula marca
que la función es global. La minúscula, por el contrario, establece que es 
local, es decir, sólo el objeto dentro del cual está definida la función 
puede acceder a ella y utilizarla.
El descriptor U significa 'indefinido', es decir, la función no está definida.
En este caso particular, la función printf está declarada en la librería
<stdio.h> pero no está definida. Para saber lo que hace printf hay que
linkearlo a la librería GLIBC que lo tiene definido.
 
5. ¿En qué se diferencian los símbolos del objeto y del ejecutable?
Rta. En el ejecutable aparecen muchos más símbolos. Además, el símbolo
'U printf' cambió a U printf@@GLIBC_2.0, que simplemente tiene agregado el
linkeo a la librería donde está definida la función printf.
