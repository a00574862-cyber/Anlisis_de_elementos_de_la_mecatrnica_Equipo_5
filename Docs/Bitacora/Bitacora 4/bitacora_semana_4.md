# Bitácora – Semana 4

## Tema de la semana
Montaje y funcionamiento del sistema / Human - Machine Interface.

## Actividades realizadas
Implementar la programación lógica final de la cortina en el LOGO Siemens V8.
Diseñar la pantalla Human Machine Interface para el control del sistema.
Montaje y acomodo de todos los elementos del sistema en el espacio final de prototipado.
Ejecutar pruebas del funcionamiento de la cortina y documentación de resultados reales.

## Decisiones de ingeniería
| Decisión | Alternativas | Justificación |
| :--- | :--- | :--- |
| **Acomodo de tabla de componentes** | Acomodo horizontal o vertical. | Se eligió un acomodo vertical con aseguramiento en el centro para evitar el enredo entre cables y un punto de equilibrio. |
| **Menor cantidad de imánes** | Acercamiento de sensor vs colocamiento imánes. | Se quitaron 6 de los imánes ya que el peso impedía el levantamiento de la cortina (falta de torque en el motor) y se colocó el sensor magnético más cerca de los imánes restantes para facilitar su detección. |
| **Cambio de polaridad en el motor** | Cambio  de colocación de cortina. | Al notar que la orientación de rotación no favorecia el acomodo en el que previamente instalamos la cortina cambiamos la polaridad desde los relés para evitar dificultades para la desinstalación de la cortina.

## Problema técnico encontrado
Al activarse el sensor capacitivo no cumplía la función de detener la cortina, esto a pesar de que funcionaba correctamente, por lo tanto se identificó un problema de programación en la relación del sensor con el mecanismo de la cortina.

## Solución aplicada
Revisamos la programación y encontramos que el sensor capacitivo no tenía un NOT y estaba conectado a una compuerta AND con el sensor óptico que asimismo no contaba con un NOT, esto causaba que cuando el sensor capacitivo y el sensor óptico identificaran un objeto la cortina siguiera moviendose mientras que cuando solo uno lo detectará se detuviera, por lo que la compuerta entre los dos se cambió a un OR y se asignaran con un NOT, así al identificar cualquiera un objeto, sus valores de 1 serían negados y la cortina se detendría.

## Conexión con el curso
En está entrega unimos los aprendizajes vistos durante las semanas precedentes, desde el diagrama de conexión del sistema para verificar la efectividad de cada sensor y actuador, igualmente que la programación de las entredas y salidas para resolver los problemas de funcionamiento en referencia a los sensores, hasta el uso de lógica ingenieril para el acomodo de los elementos del sistema para garantizar una ejecución óptima.

## Autoevaluación
- [ ] Muy perdido
- [ ] Con dudas
- [ ] Entendiendo
- [x] Dominando

