## Pioneros

### La primer computadora

+ Charles Babbage 26/12/1791 - 18/10/1871 
+ Fue una máquina analítica
+ No se logró implementar en su momento

### Máquina de Turing

+ Logró generar un marco formal para trabajar ciencias de la computación
+ Modelo matemático implementable mediante autómata, que tiene la capacidad de implementar cualquier problema matemático, expresado a traves de un algoritmo


#### Componentes
+ Cinta de longitud infinita (Furfi hace chiste de que ya desde ese entonces la memoria era un problema)
+ Cabezal que puede
	+ Avanzar o retroceder
	+ Leer o escribir en cinta
+ Registro de estado: describe el estado en que se encuentra la máquina
+ Tabla de instrucciones:  permite en función del valor leído y eventualmente de alguna acción ingresada por el usuario: 
	+ escribir un resultado; 
	+ avanzar la cinta;
	+ retroceder la cinta;
	+ dejar la cinta en su mismo lugar, y; 
	+ actualizar el nuevo estado en el registro de estados.


### Completitud  de Turing

Medida de capacidad de simular una máquina de Turing de una máquina
## Evolución


Cuenta como pasamos de máquinas enormes a lograr compactar la maquinaria.

Menciona *"First Draft of a Report on the EDVAC. John Von Newmann"* como el primer paper sobre la organización y arquitectura de una computadora. Basado en postulados de Turing

+ *“publish or perish”*, esta arquitectura por ser la primera bien documentada


### Modelo de Von Mewmann

![[VonMewmannArchitecture.png]]

+ **Central Arithmetic (CA)**: Una Unidad de Procesamiento Aritmético Lógica y Registros
+ **Central Control (CC)**: Implementación de la máquina de estados, con registro de instrucciones y registro Contador de Programa.
+ **Memory (M)**: almacena el código y los Datos. Dos cuestiones:
	+ Ya estaba en diseños anteriores (ENIAC)
	+ Genera el **Von Newmann bottleneck**
+ **Entrada (I)**: Se trata de mecanismos para que se puedan ingresar al computador comandos y datos desde el exterior.
+ **Salida (O)**: Se trata de mecanismos para que el computador pueda enviar resultados hacia el mundo exterior.
+ **Memoria Externa (R)**:  Se trata de un medio de almacenamiento de mayor capacidad que la Unidad de Memoria (en donde solo están el código y los datos del programa en ejecución). En la Memoria externa podemos tener una colección de programas y datos para copiar de a una vez en la Unidad de Memoria y lanzar a ejecutar. Es lo que hoy conocemos como Storage. Por entonces se trataba de Cintas perforadas por ejemplo.


#### Se basaba en 

+ Modelo de programa almacenado
+ Datos y programa en el mismo (único) banco de memoria.
+ Máquina de estados perpétua: 
	+ **Fetch** - **Decode** - **Execute**


### Modelo Hardvard

**Problema**: “una única Unidad de Memoria para datos y código”, definitivamente no encaja en este nuevo paradigma

Solución:
 + Las instrucciones y los datos ingresan por data paths diferentes. 

![[hardvardAchitecture.png]]
### Distinción entre Hardvard y Von Mewmann

+ Instrucciones y datos se leen desde memorias físicamente diferentes, y por caminos de señal físicamente diferentes.
+ caminos de señal (buses) independientes
+ podemos tener dos direcciones 0x00000000 de memoria: una para instrucciones y otra para datos. 

### Procesadores actuales

+ Usan una organización acorde al modelo de *Von Newmann*
+ Dividen niveles de memoria usando **split cache**: *hardvard*
+ Niveles de memoria más externos almacenan **instrucciones y datos juntos**. *Von Newmann*

### 2do Generación

+ computadores transistorizados.
+ Transistor implementada en 1947 en Laboratorios Bell
+ Menor consumo, menor espacio y mayor desempeño
+ Años 50

### 3ra Generación

+ Basados en **circuitos integrados**
+ Nace programación estructurada. 
+ Ocurre el primer sistema operativo portatable de la historia. 
+ Años 60

**Compatibilidad** es demandada

Diseño de computador en 2 aspectos
+ **Datapath**: Conjunto de recursos para que los números se almacenen en registros y las operaciones entre ellos se puedan ejecutar 
+ **Control**: lógica necesaria para que operaciones se envíen en la secuencia correcta por el Datapath

Para solucionar el **Control** en los 60 se diseño el **micro-código**. Problema a la época por ser la ROM más barata que la RAM


### Ley de Moore

>“el número de transistores por unidad de superficie en circuitos integrados se duplica cada 2 años tendencia que continuará durante las siguientes décadas.” 

Ya no se cumple desde 2018, es imposible hacerlos más pequeños

### x86

Salió en 56 semanas para competir contra el Z80
+ Compromete mantener **compatibilidad** para satisfacer una demanda
+ Se asocian con IBM por esa razón (además de que Z80 estaba financiado por Exxon, competidor de IBM)


#### Consolidación de 32 bits
+ En 1984, se extiende la arquitectura a 32 bit
+ Industria habla de procesadores x86 (standard)
+ Habilita terceros producción de procesadores IA-32
+ Nace AMD

#### EPIC

+ Intel a fines de los 90 desarrolla arquitectura de 64 bit
+ Explicitly Parallell Instruction Compute (compilador se encarga de paralelizar las instrucciones)
+ No fue explotado comercialmente
+ **Itanium**
+ EPIC Failure

#### IA-64

+ AMD toma el IA-32 y lo extiende a 64 bit

### RISC (Reduced Instruction Set Computer)

+ Se dispone de un juego de registros numeroso, todos de prop ´osito general. 
+ Las instrucciones se ejecutan en un solo ciclo de clock. 
+ Las instrucciones derivan en códigos de operación de igual formato y tamaño. 
+ Las instrucciones deben ser sencillas de decodificar. Los números de registros se deben tener la misma ubicación en los códigos de la instrucción y deben requerir la misma cantidad de bits para su decodificación. 
+ No se utiliza micro-código para decodificar instrucciones (no hay instrucciones complejas, como DIV o MUL). 
+ Los datos en memoria se acceden mediante instrucciones simples de transferencia: LOAD y STORE.
## Arquitectura y Organización

### Arquitectura:

conjunto de recursos accesibles para el programador, que por lo general se mantienen a lo largo de los diferentes modelos de procesadores de esa arquitectura (puede evolucionar pero la tendencia es mantener compatibilidad hacia modelos anteriores).
+ Registros
+ Set de instrucciones
+ Estructuras de memoria relacionadas (descriptores de página ej.)

### Micro Arquitectura = Organización + Hardware

 **implementación de la arquitectura**. El diseño lógico detrás del set de registros y del modelo de programación. Puede ser muy simple o sumamente robusta y poderosa. Cambia de un modelo a otro dentro de una misma familia.

### Datapath 

El **datapath** es el conjunto de **componentes hardware** que permiten:

- guardar valores
- trasladarlos entre registros
- aplicar operaciones aritméticas y lógicas

**No toma decisiones**: solo ejecuta acciones cuando el control se lo indica.


Todas instrucciones deben:
+ Apuntar al PC 
+ Leer uno o dos registros contenidos en la palabra de instrucción
+ El resto varía de instrucción a instrucción

### Arquitectura de un computador

definir los aspectos más relevantes en la arquitectura de un computador procurando maximizar el rendimiento del procesador, pero sin dejar de satisfacer otras limitaciones impuestas por los usuarios, como un costo accesible, o un consumo de energía moderado, entre otros


Diseñar el **set de instrucciones**, el modo en que se **manejará la memoria** y sus **modos de direccionamiento**, los restantes bloques funcionales que componen el CPU, como el **File Register**, el Datapath y el diseño de la lógica de control.

el diseño del circuito integrado, su encapsulado, montaje, alimentación y refrigeración

### ISA (Instruction Set Architecture)

+ **Clases de ISA**:  ISAs con Registros de Propósito general vs. Registros dedicados. ISAs registro-memoria vs. ISAs Load Store. 
+ **Direccionamiento de Memoria**. Alineación obligatoria de datos vs. administración de a bytes. 
+ **Modos de Direccionamiento**. Como se especifican los operandos. 
+ **Tipos y tama ˜nos de operandos**. Enteros, Punto Flotante, Punto Fijo.Diferentes tamaños y precisiones. 
+ **Operaciones**. Pocas Simples (RISC) o Muchas Complejas (CISC). 
+ **Instrucciones de control de flujo** Saltos condicionales, calls.


### Organización

Se refiere a los detalles de implementación de la ISA. Es decir: 
+ Organización e interconexión de la memoria. 
+ Diseño de los diferentes bloques de la CPU y para implementar el set de instrucciones. 
+ Implementación de paralelismo a nivel de Instrucciones, y/o de datos. 
+ Podemos así encontrar procesadores que poseen la misma ISA pero una organización muy diferente

### Hardware

+ Se refiere a los detalles de diseño lógico y tecnología de fabricación. 
+ Existirán por lo tanto, procesadores con la misma ISA y la misma organización, pero absolutamente distintos a nivel de hardware y diseño lógico detallado.
## Implementado arquitectura

### Register file

+ consiste en un **arreglo** de n **registros**, numerados de 0 a n-1, que se pueden leer y escribir proporcionando tan solo el número de registro al que se accede.
+ **Lectura**: necesitamos proporcionar un número de registro como entrada y la única salida serán datos contenidos en el registro
+ **Escritura**: 3 entradas: número de registro dentro del arreglo, datos a escribir y **clock** que controla la escritura en un registro
+ 2 puertos de lectura y uno de escritura

### Pipeline

+ Superponer en el tiempo ejecución de varias instrucciones a la vez
+ ILP
+ Todos los bloques funcionales en paralelo, pero cada uno con instrucción diferente
+ Cada parte: **stage**

![[PipelineTheoricModel.png]]
#### Obstáculos **pipeline stall**

+ Estructurales
	+ Una etapa no está suficientemente atomizada
	+ Conflicto por uso de recursos
	+ Solución agregar hardware
+ Datos: 
	+ efecto del pipeline, una instrucción requiere de un dato antes de que este esté disponible por efecto de la secuencia lógica prevista en el programa.
	+ Una solución: forwarding
+ Control
	+ Un branch es la peor situaci ´on en p ´erdida de performance del Pipeline. 
	+ todo lo que estaba pre procesado deba descartarse, ya que son las instrucciones sucesoras secuenciales al branch en el programa.
	+ **Branch penalty**



> La memoria creció mucho más lento que la CPU