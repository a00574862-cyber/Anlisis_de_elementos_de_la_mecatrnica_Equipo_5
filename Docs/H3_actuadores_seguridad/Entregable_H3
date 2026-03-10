# Hito 3 – Control e Integración

## Descripción de la lógica de control
Para implementar la logica de control en LOGO se utilizaron relevadores para gestoniar el movimiento de ascenso y descencso de la cortina. La segudad esta en la compuerta OR (B001) que integra las señales del sensor inductivo y optico, lo que permite que cualquier deteccion de obtaculos y metales detenga el motod de bajada mediante una compuerta AND (B012) que actua como un bloqueo. Adémas el sstema emplea los sensores magneticos apra resetear los relevadores y deter la marcha al alcanzar lo esperado, también al llegar al limite superior se activa un temporizador de retardo a la conexi+on (B006) de 10 segundos, lo que nos da una espera antes de que se inicie el descenso automatico. Finalmente, la interfaz de operacion se complementa con indicadores luminosos (Luz Verde y Luz Roja) que nos avisan visualemente sobre el estado de los ciclos y las condiciones de alarma que detectan los sensores.


## Asignación de Entradas y Salidas (I/O)

##Entradas (Inputs)
| Pin | Tipo | Función / Sensor | Identificador |
| :---: | :---: | :--- | :---: |
| **I1** | Digital | Sensor Capacitivo | **S1** |
| **I2** | Digital | Sensor Inductivo | **S2** |
| **I3** | Digital | Sensor Óptico | **S3** |
| **I4** | Digital | Sensor Magnético | **S4** |
| **I5** | Digital | Sensor Magnético | **S5** |
| **I6** | Digital | Sensor Magnético | **S6** |

---

###Salidas (Outputs)
| Pin | Tipo | Función / Actuador | Conexión |
| :---: | :---: | :--- | :--- |
| **Q1** | Digital | Relé a Fuente | Fuente 24V |
| **Q2** | Digital | Relé a Fuente | Fuente 24V |
| **Q3** | Digital | Luz Roja (Lámpara) | Conexión Q4 |
| **Q4** | Digital | Luz Verde (Lámpara) | Conexión C8 |


| Prueba | Resultado esperado | Resultado obtenido |
|------|------------------|------------------|


## Ajustes realizados
Describe cambios hechos tras las pruebas.
