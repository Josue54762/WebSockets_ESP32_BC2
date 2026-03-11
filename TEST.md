# Cuestionario de Evaluación: Comunicación por Sockets 📝

   **Nombre del Estudiante:** Josue Tatayo
**Fecha:** 11/03/2026

*Instrucciones: Responde a las siguientes preguntas basándote en la teoría de redes y en el análisis del código de nuestro proyecto. Sube este archivo con tus respuestas a tu repositorio como evidencia de trabajo.*

1. ¿Qué es una Dirección IP y para qué sirve en nuestro proyecto?

Una Dirección IP es un número único que identifica a un dispositivo dentro de una red. En nuestro proyecto sirve para que la computadora y la ESP32 puedan encontrarse y comunicarse entre sí a través de la red WiFi.

2. ¿Qué es un Puerto de red? (Menciona qué puerto estamos usando en el código de la ESP32).

Un puerto de red es un número que identifica una aplicación o servicio dentro de un dispositivo conectado a la red. Permite que los datos lleguen al programa correcto. En nuestro proyecto la ESP32 usa un puerto específico (por ejemplo 8080, 80, 5000 o el que esté definido en el código) para comunicarse con la computadora.

3. Define con tus propias palabras qué es un Servidor en informática.

Un servidor es un dispositivo o programa que espera conexiones de otros dispositivos (clientes) y les envía información o servicios cuando lo solicitan.

4. ¿Cuál es la diferencia entre un "Servidor" (Hardware/Software) y un "Servicio" (Service)?

Un servidor es el equipo o programa que ofrece recursos en la red.
Un servicio es la función específica que el servidor proporciona, como enviar datos, alojar una página web o manejar conexiones.

5. Investigación: ¿Cuál es la diferencia técnica entre un "Socket TCP" normal y un "WebSocket"?

Un Socket TCP es una conexión directa entre dos dispositivos para enviar datos continuamente usando el protocolo TCP.
Un WebSocket es una tecnología que funciona sobre HTTP y permite comunicación bidireccional en tiempo real entre un navegador y un servidor, manteniendo una conexión abierta.

6. Analizando nuestro código: ¿Quién actúa como Servidor y quién actúa como Cliente?

La ESP32 actúa como servidor porque abre un puerto y espera conexiones usando funciones como bind() y listen().
La computadora (Python) actúa como cliente porque inicia la conexión hacia la ESP32 usando la función connect().

7. En el código de la computadora (Python), importamos la librería threading. ¿Qué pasaría con la ventana de Tkinter si no usáramos hilos para recibir los datos de la red?

Si no usáramos hilos, la ventana de Tkinter se quedaría congelada o sin responder, porque el programa estaría ocupado esperando datos de la red y no podría actualizar la interfaz gráfica.

8. ¿Por qué es necesario usar bloques try...except cuando trabajamos con conexiones de red e Internet?

Porque las conexiones de red pueden fallar por muchas razones (desconexión, errores de red, servidor apagado). Los bloques try...except permiten manejar esos errores sin que el programa se cierre inesperadamente.

9. En la función de encender el LED en Python, enviamos el comando así: sock.send(b'ON'). ¿Qué significa esa letra b antes de las comillas y por qué no enviamos un texto normal?

La letra b indica que el dato es un byte string (datos en formato binario). Los sockets envían información en bytes, por eso no se envía texto normal sino datos convertidos a bytes.

10. Describe brevemente el flujo de datos: ¿Qué camino recorre la información desde que giras el potenciómetro físicamente hasta que la barra se mueve en la pantalla de la computadora?

Primero el potenciómetro cambia el voltaje que entra a la ESP32.
La ESP32 lee ese valor con el ADC, lo convierte en un número y lo envía por la red usando un socket.
La computadora recibe el dato en Python, lo procesa y el programa actualiza la interfaz de Tkinter, moviendo la barra en la pantalla.
