![](/Imagen/logointro.png)

# Capitulo 1

## Características generales de la arquitectura ARM

ARM es una arquitectura RISC (Reduced Instruction Set Computer=Ordenadorcon Conjunto Reducido de Instrucciones) de 32 bits, salvo la versión del core ARMv8-A que es mixta 32/64 bits (bus de 32 bits con registros de 64 bits). Se trata de unaarquitectura licenciable, quiere decir que la empresa desarrolladora ARM Holdingsdiseña la arquitectura, pero son otras compañías las que fabrican y venden los chips,llevándose ARM Holdings un pequeño porcentaje por la licencia.El chip en concreto que lleva la Raspberry Pi es el BCM2835, se trata de un SoC(System on a Chip=Sistema en un sólo chip) que contiene además de la CPU otroselementos como un núcleo GPU (hardware acelerado OpenGL ES/OpenVG/OpenEGL/OpenMAX y decodificación H.264 por hardware) y un núcleo DSP (Digitalsignal processing=Procesamiento digital de señales) que es un procesador más pe-queño y simple que el principal, pero especializado en el procesado y representaciónde señales analógicas. La CPU en cuestión es la ARM1176JZF-S, un chip de lafamilia ARM11 que usa la arquitectura ARMv6k.

## Registros

La arquitectura ARMv6 presenta un conjunto de 17 registros (16 principales más
uno de estado) de 32 bits cada uno.

![](/Imagen/Tabla.png)

Registros Generales. Su función es el almacenamiento temporal de datos. Son los 13 registros que van R0 hasta R12.

Registros Especiales. Son los últimos 3 registros principales: R13, R14 y R15.

Como son de propósito especial, tienen nombres alternativos.
- SP/R13. Stack Pointer ó Puntero de Pila. Sirve como puntero para almacenar variables locales y registros en llamadas a funciones.
- LR/R14. Link Register ó Registro de Enlace. Almacena la dirección de retorno cuando una instrucción BL ó BLX ejecuta una llamada a una rutina.
- PC/R15. Program Counter ó Contador de Programa. Es un registro que indica la posición donde está el procesador en su secuencia de instrucciones. Se incrementa de 4 en 4 cada vez que se ejecuta una instrucción, salvo que ésta provoque un salto.

## El entorno

Los pasos habituales para hacer un programa (en cualquier lenguaje) son los siguientes: lo primero es escribir el programa en el lenguaje fuente mediante un editor de programas. El resultado es un fichero en un lenguaje que puede entender el usuario, pero no la máquina. Para traducirlo a lenguaje máquina hay que utilizar un programa traductor. Éste genera un fichero con la traducción de dicho programa, pero todavía no es un programa ejecutable. Un fichero ejecutable contiene el programa traducido más una serie de códigos que debe tener todo programa que vaya a ser ejecutado en una máquina determinada. Entre estos códigos comunes se encuentran las librerías del lenguaje. El encargado de unir el código del programa con el código de estas librerías es un programa llamado montador (linker) que genera el programa ejecutable

![](/Imagen/Tabla1.png)

## Aspecto de un programa en ensamblador

* __Sección de datos.__ Viene identificada por la directiva .data. En esta zona se definen todas las variables que utiliza el programa con el objeto de reservar memoria para contener los valores asignados.

* __Sección de código.__ Se indica con la directiva .text, y sólo puede contener código o datos no modificables. Como todas las instrucciones son de 32 bits no hay que tener especial cuidado en que estén alineadas. 

### Datos
Los datos se pueden representar de distintas maneras. Para representar números tenemos 4 bases. La más habitual es en su forma decimal, la cual no lleva ningún delimitador especial.

### Símbolos
Como las etiquetas se pueden ubicar tanto en la sección de datos como en la de
código, la versatilidad que nos dan las mismas es enorme. En la zona de datos, las etiquetas pueden representar variables, constantes y cadenas. En la zona de código
podemos usar etiquetas de salto, funciones y punteros en la zona de datos.

### Instrucciones
De estos campos, sólo el nemónico (nombre de la instrucción) es obligatorio. En
la sintaxis del as cada instrucción ocupa una línea terminando preferiblemente con
el ASCII 10 (LF), aunque son aceptadas las 4 combinaciones: CR, LF, CR LF y LF
CR. Los campos se separan entre sí por al menos un carácter espacio (ASCII 32) o
un tabulador y no existe distinción entre mayúsculas y minúsculas.

### Directivas
Las directivas son expresiones que aparecen en el módulo fuente e indican al
compilador que realice determinadas tareas en el proceso de compilación. Son fácilmente distinguibles de las instrucciones porque siempre comienzan con un punto.

* Directivas de asignación
* Directivas de control
* Directivas de operando
* Directivas de Macros

## Ejecución de qemu
![](/Imagen/Ejecución.png)
![](/Imagen/Ejecución1.png)
![](/Imagen/Hola-a.png)
