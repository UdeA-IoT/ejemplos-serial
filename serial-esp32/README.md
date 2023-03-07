# Ejemplo de control de una ESP32 usando serial

El objetivo de esta sesión es explicar paso a paso como se construye una aplicación sencilla en la ESP que se comunique de manera serial con una aplicación que se esta ejecutando en un PC o RPi.

## Enuciado de la aplicación

Desarrolle una aplicación que permita encender y apagar un Led para el siguiente hardware:

![hardware_serial](../hardware_bb.png)

La aplicación se conectara mediante el serial enviando dos comandos basicos para modificar el estado del led:

* **```H```**: Comando empleado para encender el Led.
* **```L```**: Comando empleado para apagar el Led.

El resultado final (si todo sale bien) de la aplicación de control es el siguiente:

![interfaz_grafica](../ui_python.png)

## Implementación paso a paso

El proceso de construcción de la aplicación se lleva a cabo mediante los siguientes pasos:

1. Prueba del programa del ESP32 empleando el monitor serial del Arduino ([link](paso1/README.md)).

![serial_output](paso1/serial_output.png)

2. Desarrollo de la aplicación de consola en python ([link](paso2/README.md)).

![app-consola_python](paso2/app_python.png)

3. Desarrollo de la aplicación con interfaz grafica usando python ([link](paso3/README.md)).

![app-ui_output](paso3/ui_python.png)

4. Desarrollo de una aplicación Web para el control targeta.

