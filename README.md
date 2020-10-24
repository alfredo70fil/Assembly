![](/Imagen/logointro.png)
#Capitulo 1
## Características generales de la arquitectura ARM

ARM es una arquitectura RISC (Reduced Instruction Set Computer=Ordenadorcon Conjunto Reducido de Instrucciones) de 32 bits, salvo la versión del core ARMv8-A que es mixta 32/64 bits (bus de 32 bits con registros de 64 bits). Se trata de unaarquitectura licenciable, quiere decir que la empresa desarrolladora ARM Holdingsdiseña la arquitectura, pero son otras compañías las que fabrican y venden los chips,llevándose ARM Holdings un pequeño porcentaje por la licencia.El chip en concreto que lleva la Raspberry Pi es el BCM2835, se trata de un SoC(System on a Chip=Sistema en un sólo chip) que contiene además de la CPU otroselementos como un núcleo GPU (hardware acelerado OpenGL ES/OpenVG/OpenEGL/OpenMAX y decodificación H.264 por hardware) y un núcleo DSP (Digitalsignal processing=Procesamiento digital de señales) que es un procesador más pe-queño y simple que el principal, pero especializado en el procesado y representaciónde señales analógicas. La CPU en cuestión es la ARM1176JZF-S, un chip de lafamilia ARM11 que usa la arquitectura ARMv6k.

##Registros
La arquitectura ARMv6 presenta un conjunto de 17 registros (16 principales más
uno de estado) de 32 bits cada uno.

![](/Imagen/Tabla.png)
