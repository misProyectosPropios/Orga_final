## Lenguajes de programación

### Lenguajes

Los microprocesadores solo pueden tratar con valores de 2 estados (1, 0) (es su $\Sigma$).
Por eso, sus lenguajes están en lenguaje binario
### Assembler

+ Lenguaje más humano que el lenguaje binario. 
+ Cada instrucción tiene un nombre alusivo a lo que hace y está abreviado
+ Una sentencia = una instrucción de CPU
+ Ensamblador convierte texto a números binarios
+ Texto original = **código fuente**

### Alto nivel

+ Cada sentencia del programa compuesta por varias instrucciones del procesador
+ Apps **más complejas** con **menos texto**
+ Escrito en texto plano
+ Con el **compilador**, convierte texto a lenguaje binario.
+ Texto original = **código fuente**


## C

+ `stdio.h` no contiene el código de la biblioteca, solo tiene una referencia de donde estaría. Es una declaración de cosas 
+ Todo programa en C empieza con un salto a `main`
+ 

## Herramientas de desarrollo

### Ciclo de desarrollo

Una imagen vale más que mil palabras

### De que se ocupa cada herramienta

#### Compilador

+ analizar sintácticamente un archivo de texto que contiene un programa fuente.
+ Genera un código binario para ser ejecutado que obra como CPU en el sistema
+ Reemplaza nombres lógicos por direcciones de memoria donde se ubican las mismas
+ No resuelve referencias a funciones exteriores. Lo deja a otra herramienta


+ Antes de iniciar, usa el **preprocesador** para eliminar comentarios, incluir archivos por su contenido actual y reemplazas las macros 

#### Linker

+ El compilador genera un programa objeto. Necesitamos enlazarlo con otros programas objeto y otras biblioteca de código y generar un programa ejecutable por el sistema operativo.

##### Enlazar
+ Poner bloques de código juntos, ordenar código y datos en secciones
+ Resolver cada referencia a una variable.
+ Identificar punto de entrada del programa (*main*)