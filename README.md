# SISTEMAS-EMPOTRADOS
Relación de las distintas prácticas realizadas en la asignatura de Sistemas Empotrados del Máster en Ingeniería Informática.

**PRACTICA 1**

   - **Ejercicio 1:** Identificar en la placa los elementos.
   - **Ejercicio 2:** Utilizando la placa FRDM –K64F, con la técnica de semihosting mostrar los siguientes mensajes en la consola de KDS: 
          "Hola 1
           Hola 2
           Hola 3
           …" 
        Los mensajes se mostrarán hasta el infinito.
        
**PRACTICA 2**

 - **Ejercicio 1:** Realizar mediante KDS un proyecto en el que no se utilice Processor Expert. Para ello será necesario crear el proyecto normalmente, pero al llegar a la pantalla en la que se nos solicita la aplicación de desarrollo rápido a utilizar, lo dejaremos en blanco. Una vez creado el proyecto, realizar un programa que al pulsar el switch 2 encienda el led verde y se quede encendido y se apague al pulsar el switch 3.

 - **Ejercicio 2:** Repetir la actividad 1, pero en este caso utilizando Processor Expert.

 - **Ejercicio 3:** Colocar el Shield Basic sobre la placa y hacer un programa que al pulsar el swicth colocado más a la izquierda (S1-A1) se vayan encendiendo consecutivamente los distintos LEDs, el LED superior (D1) en la primera pulsación, el segundo (S2) con la segunda pulsación, el led S3 con la tercera y el S4 con la cuarta, repitiendo el ciclo indefinidamente. La detección de la pulsación se realizará mediante una interrupción

- **Ejercicio 4:** Se desea diseñar un semáforo mediante el sistema empotrado FRDM K64F. Se utilizará el led RGB de la placa FRDM K64F y los pulsadores del Multifuntion Shield. El funcionamiento será el siguiente: Se desea que cuando se presione el pulsador S1 (PTB3) comience el funcionamiento, que consistirá en lo siguiente: Se comenzará encendiendo el led rojo de la placa FRDMK64F (PTB22). La fase roja durará 5s. A continuación, se encenderá la fase amarilla (encender los leds rojo (PTB22) y verde (PTE26) simultáneamente) durante 1 s y finalmente la fase verde (PTE26) durante 4 s. Se debe repetir el ciclo de manera ininterrumpida. Si se presiona el pulsador S2 (PTB10), el semáforo entrará en situación de emergencia y se encenderá de manera intermitente el LED amarillo con una frecuencia de 0.5 s. Para volver a la situación de funcionamiento normal será necesario pulsar D1 de nuevo.
     - Resolver este ejercicio utilizando una interrupción periódica para el caso de la temporización de los LEDs. Tratar de utilizar una única interrupción periódica para todas las fases.
     - Utilizar la función Wait para programar la intermitencia.
- **Ejercicio 5:** Se desea controlar el brillo del led D1 del multifunction Shield. Para ello se utilizarán dos pulsadores. Se desea que mediante la pulsación del switch S1 se incremente el brillo del led y mediante la pulsación del S2 se decremente el brillo. Se necesitarán 4 pulsaciones para pasar del brillo máximo al apagado completo. La modulación del brillo puede hacerse mediante la modulación del ancho de un pulso PWM.

- **Ejercicio 6:** Utilizando el componente FreeCntr16, medir el tiempo transcurrido entre dos pulsaciones del switch S1 y mostrar ese tiempo por la consola utilizando semihosting cuando se produzca la segunda pulsación.

**PRACTICA 3**

 - **Ejercicio 1:** Realizar un programa que cada vez que reciba el carácter ‘a’, escriba a través del puerto serie escriba “Hola Mundo” y si se recibe el carácter ‘b’ se escriba “Adios Mundo”. Realizar la lectura de caracteres por el puerto serie en modo polling.
 - **Ejercicio 2:** Modificar el ejercicio anterior de tal forma que los caracteres se reciban mediante el uso de interrupciones.
 
 - **Ejercicio 3:** Modificar el ejercicio anterior para en este caso se reciba un comando y una instrucción. Existen dos posibles comandos, el comando 0x00 y el comando 0x0F. Existen también dos posibles instrucciones “A” y “B”. De esta forma hay cuatro combinaciones: 
     - 0x00 y “A”, debe enviarse por el puerto serie el mensaje: “Dame 5 minutos”.
     - 0x00 y “B”, debe enviarse por el puerto serie el mensaje: “Eso no es asunto mio”.
     - 0x0F y “A”, debe enviarse por el puerto serie el mensaje: “Ahora mismo”.
     - 0x0F y “B”, debe enviarse por el puerto serie el mensaje: “Ya lo he hecho”.

 - **Ejercicio 4:** Se desea realizar un dispositivo de bajo costo que realice medidas del acelerómetro a través de I2C. Realizar un programa que acceda a las medidas del acelerómetro, ejes X, Y o Z, de forma selectiva de manera que si se pulsa el switch 2 (de la placa FRDM K64F) una vez se acceda al valor de X, si se por segunda vez se acceda al valor de la Y y si se pulsa 3 veces se acceda al valor de la Z. Si se pulsa el switch 3 (de la placa FRDM K64F), las tres lecturas se realizarán de manera periódica cada 0.5s. Realizar la detección de las pulsaciones mediante el uso de interrupciones. Los valores leídos del acelerómetro se deben enviar a través del puerto serie (UART) al PC. Los valores, que se leen en bruto en un intervalo de 0 – 65535 se normalizaran a valores entre 0 y 100. Ten en cuenta que deberás convertir el entero que recibes a través de la lectura del acelerómetro a caracteres para poder visualizarlo desde el PC. Para ello puedes utilizar la función UART_Write_Numero_Int, que está contenida en el fichero UART.c proporcionado con la práctica. Esta función recibe un número entero y envía por el puerto serie ese entero ese entero carácter a carácter. La visualización debe ser algo así:
Cuando se presiona el switch 2, se muestran los valores así, por ejemplo, se presiona 3 veces de forma consecutiva:
X: ------
Y: ------
Z: ------ 
Si se presiona el switch 3, se mostrarán los valores cada 0.5 s de la siguiente manera: 
X: ------ Y: ------ Z: ------
X: ------ Y: ------ Z: ------
X: ------ Y: ------ Z: -----

**PRACTICA 4**

 - **Ejercicio 1:**  Utilizando la placa FREM K64F junto con el Shield Basic Conectado, realizar un programa que realice simultáneamente medidas de 2 puertos analógicos. Los resultados se enviarán al terminal por el puerto serie normalizados entre 0-100.
     - Realizar la lectura del potenciómetro 1 cada 0.4 segundos utilizando interrupciones.
     - Realizar la lectura del termómetro cada segundo mediante polling sin utilizar eventos

 - **Ejercicio 2:** Modificar la actividad anterior para que el potenciómetro regule la intensidad del led D1 de la Multifunction Shield. Será necesario utilizar PWM para modular la intensidad del led en función de los anchos de pulso que se envíen


**PRACTICA 5**

 - **Ejercicio 1:** Crear una tarea que haga que el led rojo perteneciente al led RGB de la placa parpadee 0.5 s con una frecuencia de 1 s.
 
 - **Ejercicio 2:** Crear 2 tareas, una de las tareas encenderá el led rojo (RGB de la placa) durante 0.5 s con la prioridad más alta, otra de las tareas encenderá el led verde (RGB de la placa) durante 0.7 s con una prioridad intermedia. El tiempo de retardo durante el cual el led está encendido se hará utilizando la función Waitms, mientras que el tiempo durante el cual el led está apagado se programará mediante la función vTaskDelay. Probar a modificar las prioridades.
 
 - **Ejercicio 3:** Modificar la actividad anterior de tal forma que el tiempo durante el cual los leds están
encendidos se programa también mediante la función vTaskDelay.

 - **Ejercicio 4:** Repetir la actividad anterior, pero utilizar ahora un semáforo, de tal forma que se adquiera cuando se encienden los leds.
 
 - **Ejercicio 5:** Modificar la actividad anterior para que se imprima por el puerto serie el color que se
enciende en cada momento utilizando colas.
