# Robotica_Lab2_EPSON
## Integrantes: 
## -Camilo Andres Apraez Zamora
## -Marcos Alfredo Fierro Sarria

Código_practicaa_Epson.txt, presenta el código que se usó para la implementación en el robot VT6L de Epson. A continuación, presentamos un pequeño informe de lo que se hizo:

# Informe de Práctica: Control de Movimiento con Robot Epson VT6L
**Fecha de Elaboración:** 05-03-2024  
**Responsable de Ingeniería:** Ing. Diego Castro  

---

## Objetivo de la Práctica:

El objetivo de esta práctica fue aprender a programar y controlar un robot Epson VT6L para realizar operaciones de movimiento y paletizado mediante el uso del lenguaje SPEL+ y el software EPSON RC + 7.0. Se realizaron tareas específicas para configurar el robot, crear puntos de referencia, generar movimientos entre estos puntos, desarrollar funciones de paletizado y establecer condiciones lógicas para la ejecución de estas funciones.

---

## Resumen de Actividades Realizadas:
1. **Configuración Inicial del Proyecto:**
   - Se abrió un proyecto nuevo en el software de programación.
   - Se configuró una posición de home utilizando el Robot Manager.
2. **Creación de Puntos de Referencia:**
   - Se crearon tres puntos utilizando las herramientas de JOG&TEACH, con coordenadas aproximadas de tal manera, que el Robot no se estrelle con algún lugar en el espacio proporcionado por CdM.
3. **Programación Básica en SPEL+:**
   - Se desarrolló un programa básico en SPEL+ para hacer que el robot navegue entre los tres puntos creados.
   - Se agregó un retardo en ms entre movimientos utilizando los comandos Go (no pide tantos recursos para operar pero no garantiza un movimiento lineal) y Move (Generalmente para ir en línea recta).
   - Se modificó la altura en el eje Z en 300 mm antes y después de la ejecución de cada punto, con la función :Z(300).
4. **Función de Paletizado (paletizado_z):**
   - Se generó una función llamada "paletizado_z" que configura un pallet de 3x3 posiciones.
   - Se llamó a esta función después de ejecutar los movimientos del punto anterior con la palabra reservada call.
   - Se ejecutó un bucle FOR para navegar por las nueve posiciones del pallet en orden ascendente.
5. **Segunda Función de Paletizado (paletizado_s):**
   - Se programó una segunda función llamada "paletizado_s" para recorrer las nueve posiciones del pallet en forma de "S".
   - Esta función se ejecutó después de "paletizado_z".
6. **Condiciones Lógicas y Salidas Digitales:**
   - Se codificaron condicionales para ejecutar "paletizado_z" solo si la entrada digital número 9 está activada, y "paletizado_s" solo si la entrada digital número 10 está activada.
   - Se asignaron salidas digitales (11 y 12) para indicar cuando se está ejecutando "paletizado_z" y "paletizado_s", respectivamente.
7. **Tercera Función de Paletizado (paletizado_externo):**
   - Se generó una tercera función llamada "paletizado_externo" que utiliza el comando Pallet Outside para configurar un pallet con 4 filas y columnas.
   - Se desarrolló una rutina para que el robot navegue por los 16 puntos del pallet.
   - Esta función se ejecuta solo si la entrada digital número 11 está activada.

A continuación se presenta, en los siguientes links de los videos que corresponden a una simulación en el software EPSON RC + 7.0 y la implementación en el robot proporcionado por CdM, respectivamente.

https://youtu.be/tQKrsi8p6bs  

https://youtu.be/VLmYTwiFMBg
---


## Conclusiones

Esta práctica proporcionó una comprensión fundamental del manejo y programación de robots Epson VT6L para operaciones de movimiento y paletizado. Se adquirieron habilidades para configurar el robot, crear y ejecutar programas en SPEL+, y trabajar con funciones y condiciones lógicas para controlar el flujo de trabajo del robot. Este conocimiento es fundamental para realizar tareas de automatización en entornos industriales y de producción.

