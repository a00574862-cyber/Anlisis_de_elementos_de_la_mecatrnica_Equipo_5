# Hito 3 – Control e Integración

## Descripción de la lógica de control
Para implementar la logica de control en LOGO se utilizaron relevadores para gestoniar el movimiento de ascenso y descencso de la cortina. La segudad esta en la compuerta OR (B001) que integra las señales del sensor inductivo y optico, lo que permite que cualquier deteccion de obtaculos y metales detenga el motor de bajada mediante una compuerta AND (B012) que actua como un bloqueo. Adémas el sstema emplea los sensores magneticos apra resetear los relevadores y deter la marcha al alcanzar lo esperado, también al llegar al limite superior se activa un temporizador de retardo a la conexi+on (B006) de 10 segundos, lo que nos da una espera antes de que se inicie el descenso automatico. Finalmente, la interfaz de operacion se complementa con indicadores luminosos (Luz Verde y Luz Roja) que nos avisan visualemente sobre el estado de los ciclos y las condiciones de alarma que detectan los sensores.


## Asignación de Entradas y Salidas (I/O)

 ***Entradas (Inputs)***
| Pin | Tipo | Función / Sensor | Identificador |
| :---: | :---: | :--- | :---: |
| **I1** | Digital | Sensor Capacitivo | **S1** |
| **I2** | Digital | Sensor Inductivo | **S2** |
| **I3** | Digital | Sensor Óptico | **S3** |
| **I4** | Digital | Sensor Magnético | **S4** |
| **I5** | Digital | Sensor Magnético | **S5** |
| **I6** | Digital | Sensor Magnético | **S6** |

---

 ***Salidas (Outputs)***
| Pin | Tipo | Función / Actuador | Conexión |
| :---: | :---: | :--- | :--- |
| **Q1** | Digital | Relé a Fuente | Fuente 24V |
| **Q2** | Digital | Relé a Fuente | Fuente 24V |
| **Q3** | Digital | Luz Roja (Lámpara) | Conexión Q4 |
| **Q4** | Digital | Luz Verde (Lámpara) | Conexión C8 |

---
 ***Pruebas***

| Prueba | Resultado esperado | Resultado obtenido |
| :--- | :--- | :--- |
| **Ascenso** | El motor de subir se enciende. | Fue el correcto; logramos hacer que el motor encendiera. |
| **Tiempo de Espera** | El motor se apaga e inmediatamente esperamos 10 segundos para el retroceso. | Fue el correcto; se esperó el tiempo y se volvió a encender con el otro relé (para bajar). |
| **Descenso** | El segundo relé activa el motor para que comience a bajar. | El relé se activa y el motor comienza a bajar. |
| **Luz verde prende** | La luz verde se enciende cuando el motor se apaga. | El resultado fue el esperado; se encendía la luz verde cuando el motor se detenía. |
| **Luz roja enciende** | La luz roja se enciende cuando el motor está encendido. | El resultado fue el esperado; se encendía la luz roja cuando el motor estaba en movimiento. |


## Ajustes realizados
Describe cambios hechos tras las pruebas.
No realizamos muchos ajustes, solo poner en el programa de LOGO las entradas que nosotros teniamos para que todo funcionara correctamente y no estubiera invertido. Además de que en nuestro programa agregamos algunos "NOT" ya que nuestros sensores estaban invertidos.
